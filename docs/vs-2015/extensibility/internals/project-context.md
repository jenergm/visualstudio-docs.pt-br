---
title: Contexto do projeto | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], opening items
ms.assetid: d1803f4a-24eb-44b0-b5d2-cb40c15534be
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d4ee4da5fdea63cf1bdd33554c72f6dac30d0334
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58927040"
---
# <a name="project-context"></a>Contexto do projeto
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Quando o usuário adiciona ou funciona com projetos e itens de projeto, o IDE usa a noção de contexto do projeto para determinar como as várias operações devem ser executadas.  
  
 Normalmente, os arquivos são os objetos de projeto padrão que o usuário cria explicitamente, selecionando o **novo projeto** comando ou disponibiliza selecionando o **Abrir projeto** comando o  **Arquivo** menu. Nesses casos, os arquivos são criados e abertos no contexto de um projeto e o tipo de projeto define o contexto de edição do documento.  
  
 Alguns projetos fornecem um contexto muito avançado. Por exemplo, o projeto gerencia um namespace no escopo do projeto e programática ou uma conexão de banco de dados no escopo do projeto para vinculação de dados. O usuário com frequência pode abrir arquivos ou conexões de banco de dados diretamente por meio de um objeto de projeto específico, como um item de projeto exibido no Gerenciador de soluções.  
  
 Em outras ocasiões, o contexto do projeto de um item não for especificado explicitamente. Por exemplo, o contexto de um item não está disponível quando o usuário abre um arquivo, selecionando o **abrir arquivo existente** comando as **arquivo** menu, quando o depurador opera em um arquivo, ou quando o usuário clica o **Localizar nos arquivos** comando as **localizar e substituir** caixa de diálogo. Para lidar com essas situações, as chamadas IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument> para gerenciar o processo de localizar o projeto melhor para abrir um documento.  
  
## <a name="see-also"></a>Consulte também  
 [Prioridade do projeto](../../extensibility/internals/project-priority.md)   
 [Adicionar modelos projeto e de item de projeto](../../extensibility/internals/adding-project-and-project-item-templates.md)
