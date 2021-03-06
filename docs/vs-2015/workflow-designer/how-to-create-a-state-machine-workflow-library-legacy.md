---
title: 'Como: Criar uma biblioteca de fluxo de trabalho de máquina de estado (herdado) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- projects, state machine workflow library
- state machine workflow libraries
- workflows, state machine workflow library
ms.assetid: 5bd68c6e-6a98-47d9-826d-9bb7a4fd72f8
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ca54c1585d683745bb42815921f3982c9c0fd441
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60084889"
---
# <a name="how-to-create-a-state-machine-workflow-library-legacy"></a>Como: Criar uma biblioteca de fluxo de trabalho de máquina de estado (herdado)
Siga estas etapas para criar um projeto de biblioteca de fluxo de trabalho do computador de estado usando [!INCLUDE[wfd1](../includes/wfd1-md.md)] herdado fornecido por [!INCLUDE[vs2010](../includes/vs2010-md.md)]. Use [!INCLUDE[wfd2](../includes/wfd2-md.md)] herdado quando você precisa definir como alvo [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
### <a name="to-create-a-state-machine-workflow-library-project"></a>Para criar um projeto de biblioteca de fluxo de trabalho do computador de estado  
  
1. Inicie o Visual Studio.  
  
2. No menu **Arquivo**, aponte para **Novo** e selecione **Projeto**.  
  
     A caixa de diálogo **Novo Projeto** é aberta.  
  
3. Selecione o **.NET Framework 3.0** opção ou o **.NET Framework 3.5** opção na lista suspensa na parte superior da lista da **novo projeto** janela para acessar o designer herdado.  
  
    > [!NOTE]
    >  A opção padrão na [!INCLUDE[vs2010](../includes/vs2010-md.md)] está **.NET Framework 4**. Essa opção é usada criar aplicativos de [!INCLUDE[wf](../includes/wf-md.md)] que direcionam [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] e usa o designer herdado.  
  
4. No **tipos de projeto** painel, selecione Visual c# ou Visual Basic (sob **outras linguagens**) e, em seguida, selecione **fluxo de trabalho**.  
  
5. No **modelos** painel, selecione **biblioteca de fluxo de trabalho de máquina de estado**.  
  
6. No **nome** , digite um nome descritivo para seu projeto para torná-lo mais fácil identificar.  
  
7. No **local** , digite o diretório no qual você deseja salvar seu projeto, ou clique em **procurar** para navegar até ele.  
  
     Se você quiser um diretório de solução criado para o projeto, selecione a **criar diretório para solução** caixa de seleção e insira um nome na **nome da solução** caixa.  
  
8. Clique em **OK**.  
  
## <a name="see-also"></a>Consulte também  
 [Criando projetos herdados de fluxo de trabalho](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Fluxos de trabalho do computador de estado](http://msdn.microsoft.com/library/344caacd-bf3b-4716-bd5a-eca74fc5a61d)