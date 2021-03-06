---
title: 'Como: Adicionar comentários a um fluxo de trabalho no Designer de fluxo de trabalho | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.Annotations.Annotation.UI
- Annotation
ms.assetid: 9aa0e8d6-8129-4438-8389-d460611581a7
caps.latest.revision: 7
author: steved0x
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f826168d3b198090ba58f409f096b4b12c760c70
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60059663"
---
# <a name="how-to-add-comments-to-a-workflow-in-the-workflow-designer"></a>Como: Adicionar comentários a um fluxo de trabalho no Designer de Fluxo de Trabalho
Para facilitar a criação maior, os fluxos de trabalho mais complicados, [!INCLUDE[net_v45](../includes/net-v45-md.md)] permitem que o desenvolvedor adiciona anotações aos seguintes tipos de item sobre o designer:  
  
- <xref:System.Activities.Activity>  
  
- <xref:System.Activities.Statements.State>  
  
- <xref:System.Activities.Statements.Transition>  
  
- Classes derivadas de <xref:System.Activities.Statements.FlowNode>  
  
- <xref:System.Activities.Variable>  
  
- <xref:System.Activities.Argument>  
  
> [!IMPORTANT]
>  O conteúdo de uma anotação são salvos como texto sem formatação ao arquivo XAML associado com o fluxo de trabalho, e podem potencialmente ser lidas por outro. Seja cuidadoso ao inserir informações sigilosas em uma anotação.  
  
### <a name="adding-an-annotation-to-an-activity-in-the-designer"></a>Adicionando uma anotação a uma atividade no designer  
  
1. No designer de fluxo de trabalho, clique com botão direito em um item no designer e selecione o fluxo de trabalho **anotações**, **Adicionar anotação**.  
  
2. Adicione o texto de anotação no espaço fornecido.  
  
3. O item mostrará um ícone de anotação. Passa sobre o ícone de anotação exibirá o texto de anotação.  
  
     ![Sequência mostrando anotação de atividade](../workflow-designer/media/annotation.png "anotação")  
  
### <a name="displaying-an-annotation-in-an-activitys-designer"></a>Exibindo uma anotação no designer de uma atividade  
  
1. Com um designer de atividade que tem uma anotação que exibe fora da atividade, clique o **Pin** ícone no adorno de anotação.  
  
2. A anotação será exibida no designer de atividade. Em captura de tela abaixo, a anotação “que inicia a atividade no fluxo de trabalho” é exibida no designer de atividade.  
  
     ![Anotação mostrada no designer de atividade](../workflow-designer/media/annotationindesigner.png "AnnotationInDesigner")  
  
3. Para exibir a anotação fora do designer de atividade, passe o mouse sobre a área de anotação no designer de atividade e clique no **Desafixar** ícone  
  
     ![Anotação exibida fora do Designer de uma atividade](../workflow-designer/media/annotationoutsidedesigner.png "AnnotationOutsideDesigner")  
  
### <a name="showing-or-hiding-all-annotations"></a>Mostrar ou ocultar todas as anotações  
  
1. Clique com o botão direito do mouse uma atividade que tenha uma anotação. Selecione **anotações**, **Mostrar todas as anotações**.  
  
2. Todas as anotações serão exibidas no designer de atividade.  
  
3. Para exibir todas as anotações fora do Designer de atividade, clique com botão direito na atividade e selecione **anotações**, **ocultar todas as anotações**.  
  
### <a name="editing-or-deleting-an-annotation-for-an-activity"></a>Editando ou excluindo uma anotação para uma atividade  
  
1. Clique com o botão direito do mouse em uma atividade que tenha uma anotação.  
  
2. Selecione **anotações**, **editar anotação** ou **excluir anotação**.  
  
3. A anotação será aberta editando ou excluída.  
  
4. Para excluir todas as anotações ao mesmo tempo, clique com botão direito do fluxo de trabalho no designer e selecione **anotação**, **excluir todas as anotações**.  
  
### <a name="adding-editing-and-deleting-an-annotation-for-a-variable-or-argument"></a>Adicionando, editar, e excluir uma anotação para uma variável ou um argumento  
  
1. Clique com o botão direito do mouse em uma variável ou o argumento e selecione adicionar a anotação.  
  
2. Digite o texto de anotação. A variável ou o argumento exibirá um ícone de anotação.  
  
3. Clique com o botão direito do mouse em uma variável ou em um argumento que tenha uma anotação. Selecione a anotação de edição.  
  
4. A anotação será aberta editando.  
  
5. Clique com o botão direito do mouse em uma variável ou em um argumento que tenha uma anotação. Selecione a anotação excluir.  
  
6. A anotação será excluída.