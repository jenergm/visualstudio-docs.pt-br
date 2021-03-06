---
title: 'Como: Criar uma biblioteca de atividades de fluxo de trabalho (herdado) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- workflows, activity library projects
- workflow activity libraries
- projects, workflow activity libraries
ms.assetid: fb5aa940-2ae8-4b52-b52c-51c20861a7b4
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 622b4376ef90863697e13ae32005a9ad890ce2a4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58924194"
---
# <a name="how-to-create-a-workflow-activity-library-legacy"></a>Como: Criar uma biblioteca de atividades de fluxo de trabalho (herdado)
Siga estas etapas para criar um projeto de biblioteca de atividade de fluxo de trabalho usando [!INCLUDE[wfd1](../includes/wfd1-md.md)] herdado fornecido por [!INCLUDE[vs2010](../includes/vs2010-md.md)]. Use [!INCLUDE[wfd2](../includes/wfd2-md.md)] herdado quando você precisa definir como alvo [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
### <a name="to-create-a-workflow-activity-library-project"></a>Para criar um projeto de biblioteca de atividade de fluxo de trabalho  
  
1.  Inicie o Visual Studio.  
  
2.  No menu **Arquivo**, aponte para **Novo** e selecione **Projeto**.  
  
     A caixa de diálogo **Novo Projeto** é aberta.  
  
3.  Selecione o **.NET Framework 3.0** opção ou o **.NET Framework 3.5** opção na lista suspensa na parte superior da lista da **novo projeto** janela para acessar o designer herdado.  
  
    > [!NOTE]
    >  A opção padrão na [!INCLUDE[vs2010](../includes/vs2010-md.md)] está **.NET Framework 4**. Essa opção é usada criar aplicativos de [!INCLUDE[wf](../includes/wf-md.md)] que direcionam [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] e usa o designer herdado.  
  
4.  No **tipos de projeto** painel, selecione Visual C# ou Visual Basic (sob **outras linguagens**) e, em seguida, selecione **fluxo de trabalho**.  
  
5.  No **modelos** painel, selecione **biblioteca de atividades de fluxo de trabalho**.  
  
6.  No **nome** , digite um nome descritivo para seu projeto para torná-lo mais fácil identificar.  
  
7.  No **local** , digite o diretório no qual você deseja salvar seu projeto, ou clique em **procurar** para navegar até ele.  
  
     Se você quiser um diretório de solução criado para o projeto, selecione a **criar diretório para solução** caixa de seleção e insira um nome na **nome da solução** caixa.  
  
8.  Clique em **OK**.  
  
## <a name="see-also"></a>Consulte também  
 [Criando projetos herdados de fluxo de trabalho](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Usando o Designer de atividade herdado](../workflow-designer/using-the-legacy-activity-designer.md)   
 [Atividades de fluxo de trabalho herdado](../workflow-designer/legacy-workflow-activities.md)   
 [Desenvolvimento de atividades de fluxo de trabalho](http://msdn.microsoft.com/19876dfc-dfa5-4d52-b1f5-1d087474cc52)   
 [Atividades do Windows Workflow Foundation](http://msdn.microsoft.com/192c4c1e-afb6-4f58-ab11-2b5bbbc2d2c0)