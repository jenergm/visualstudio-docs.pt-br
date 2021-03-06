---
title: Coloração de sintaxe em editores personalizados | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - syntax coloring
ms.assetid: 74900b9a-baef-432a-8231-4568fb5e19ad
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e5e627d758a1249a1e9b5e877255a67cfb255cf9
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60060664"
---
# <a name="syntax-coloring-in-custom-editors"></a>Coloração de sintaxe em editores personalizados
Editores de SDK de ambiente do Studio Visual, incluindo o editor de núcleo, usam serviços de linguagem para identificar itens específicos de sintáticos e exibi-las com as cores especificadas para uma exibição de documento fornecido.

## <a name="colorization-requirements"></a>Requisitos de colorização
 Todos os editores de implementação colorizador de um serviço de linguagem devem:

1. Usar um objeto que implementa <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> para gerenciar o texto a ser coloridos e um objeto que implementa <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> para fornecer uma exibição de documento do texto.

2. Obter uma interface para um serviço de linguagem específica ao consultar o provedor de serviços do VSPackage usando o GUID de identificação do serviço de idiomas.

3. Chame o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> método de implementação de objeto <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>. Esse método associa o serviço de linguagem com o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> implementação o VSPackage usa para gerenciar o texto que deve ser colorido.

## <a name="core-editor-usage-of-a-language-services-colorizer"></a>Editor principal do uso de colorizador de um serviço de linguagem
 Quando um serviço de linguagem com um colorizador é obtido por uma instância do editor de núcleo, a análise e renderização de texto por colorizador de um serviço de linguagem ocorre automaticamente sem a necessidade de intervenção adicional de sua parte.

 O IDE transparente:

- Chama o colorizador conforme necessário para examinar e analisar o texto como ele é adicionado ou modificado na implementação de <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>.

- Garante que a exibição fornecida pelo modo de exibição de documento fornecido pelo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> implementação é atualizada e redesenhada usando as informações retornadas pelo colorizador.

## <a name="non-core-editor-usage-of-a-language-services-colorizer"></a>Uso do Editor não essenciais de colorizador de um serviço de linguagem
 Instâncias do editor de núcleo não também podem usar o serviço de colorização de sintaxe de um serviço de linguagem, mas explicitamente deve recuperar e aplicar colorizador do serviço e redesenhar seus modos de exibição de documento em si.

 Para fazer isso, um editor de núcleo não deve:

1. Obter o objeto de colorizador de um serviço de linguagem (que implementa <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> e <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2>). O VSPackage faz isso chamando o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> método na interface do serviço de linguagem.

2. Chamar o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> método solicitar coloridos de um determinado intervalo de texto.

     O <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> método retorna uma matriz de valores, uma para cada letra no texto do span sendo colorido. Ele também identifica o intervalo de texto como um tipo específico de item que pode ser colorido, como um comentário, a palavra-chave ou o tipo de dados.

3. Use as informações de colorização retornadas por <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> para redesenhar e exibir seu texto.

> [!NOTE]
> Além de usar colorizador de um serviço de linguagem, um VSPackage pode optar por usar o mecanismo de cores de texto para fins gerais do SDK do ambiente do Visual Studio. Para obter mais informações sobre esse mecanismo, consulte [usando fontes e cores](../extensibility/using-fonts-and-colors.md).

## <a name="see-also"></a>Consulte também

- [Coloração de sintaxe em um serviço de linguagem herdado](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)
- [Implementar a coloração de sintaxe](../extensibility/internals/implementing-syntax-coloring.md)
- [Como: Usar itens de coloração internos](../extensibility/internals/how-to-use-built-in-colorable-items.md)
- [Itens de coloração personalizados](../extensibility/internals/custom-colorable-items.md)