---
title: Atraso de carregamento do documento | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: fb07b8e2-a4e3-4cb0-b04f-8eb11c491f35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0a3520b2bf1d6111e945f037502a589feed0d80a
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335318"
---
# <a name="delayed-document-loading"></a>Atraso de carregamento do documento

Quando um usuário é reaberto em uma solução do Visual Studio, a maioria dos documentos associados não é carregada imediatamente. O quadro de janela do documento é criado em um estado pendente de inicialização, e um documento de espaço reservado (chamado de um quadro de stub) é colocado na tabela de documento em execução (RDT).

Sua extensão pode causar a documentos do projeto para ser carregado desnecessariamente consultando elementos nos documentos antes que eles sejam carregados, que podem aumentar o espaço de memória geral para o Visual Studio.

## <a name="document-loading"></a>Carregamento do documento

O quadro de stub e o documento estão totalmente inicializados quando o usuário acessa o documento, por exemplo, selecionando a guia do quadro da janela. O documento também pode ser inicializado por uma extensão que solicita os dados do documento, acessando o RDT diretamente para adquirir os dados do documento ou acessar o RDT indiretamente, fazendo uma das seguintes chamadas:

- O quadro de janela <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> método.

- O quadro de janela <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> método em qualquer uma das seguintes propriedades:

   - [__VSFPROPID.VSFPROPID_DocView](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_DocView>)

   - [__VSFPROPID.VSFPROPID_ViewHelper](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_ViewHelper>)

   - [__VSFPROPID.VSFPROPID_DocData](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_DocData>)

   - [__VSFPROPID.VSFPROPID_AltDocData](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_AltDocData>)

   - [__VSFPROPID.VSFPROPID_RDTDocData](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_RDTDocData>)

   - [__VSFPROPID.VSFPROPID_SPProjContext](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_SPProjContext>)

- Se sua extensão usar código gerenciado, você não deve chamar <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> , a menos que você tiver certeza de que o documento não está no estado pendente de inicialização, ou você deseja que o documento seja totalmente inicializada. O motivo é que o método sempre retorna o documento de objeto de dados, criá-lo se necessário. Em vez disso, você deve chamar um dos métodos no `IVsRunningDocumentTable4` interface.

- Se sua extensão usar C++, você pode passar `null` para os parâmetros que você não deseja.

- Você pode evitar o carregamento chamando um dos métodos a seguir antes de você perguntar para as propriedades relevantes antes que você pergunte para outras propriedades de documento desnecessário:

   - <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> usando [__VSFPROPID6. VSFPROPID_PendingInitialization](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID6.VSFPROPID_PendingInitialization>).

   - <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A>. Esse método retorna um <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> objeto que inclui um valor para [_VSRDTFLAGS4. RDT_PendingInitialization](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4.RDT_PendingInitialization>) se o documento ainda não foi inicializado.

Você pode descobrir quando um documento foi carregado por assinatura do evento RDT que é gerado quando um documento está totalmente inicializado. Há duas possibilidades:

- Se o coletor de eventos implementa <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2>, você pode assinar <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2.OnAfterAttributeChangeEx%2A>,

- Caso contrário, você pode assinar <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterAttributeChange%2A>.

O exemplo a seguir é um cenário de acesso do documento hipotético: Uma extensão que deseja exibir algumas informações sobre como abrir documentos do Visual Studio, por exemplo Editar Bloquear contagem e algo sobre os dados do documento. Enumera os documentos usando o RDT <xref:Microsoft.VisualStudio.Shell.Interop.IEnumRunningDocuments>, em seguida, chama <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> para cada documento para recuperar os dados de documento e de contagem de bloqueio editar. Se o documento estiver no estado pendente de inicialização, solicita os dados de documento faz com que ele seja inicializada desnecessariamente.

Uma maneira mais eficiente de acessar um documento é usar <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentEditLockCount%2A> para obter a contagem de bloqueio de edição e, em seguida, use <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A> para determinar se o documento foi inicializado. Se os sinalizadores de não incluir [_VSRDTFLAGS4. RDT_PendingInitialization](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4.RDT_PendingInitialization>), o documento já foi inicializado e solicita os dados de documento com <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentData%2A> não faz com que qualquer inicialização desnecessária. Se os sinalizadores de incluir [_VSRDTFLAGS4. RDT_PendingInitialization](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4.RDT_PendingInitialization>), a extensão deve evitar solicita os dados de documento até que o documento seja inicializado. Essa inicialização pode ser detectada no `OnAfterAttributeChange(Ex)` manipulador de eventos.

## <a name="test-extensions-to-see-if-they-force-initialization"></a>Extensões para ver se eles forçam a inicialização de teste

Não há nenhuma indicação visível para indicar se um documento foi inicializado, portanto, pode ser difícil descobrir se sua extensão está forçando a inicialização. Você pode definir uma chave do registro que facilita a verificação, porque ele faz com que o título de todos os documentos que não esteja totalmente inicializado para ter o texto *[Stub]* no título.

Na **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0\BackgroundSolutionLoad**, defina **StubTabTitleFormatString** para  *{0} [Stub]*.