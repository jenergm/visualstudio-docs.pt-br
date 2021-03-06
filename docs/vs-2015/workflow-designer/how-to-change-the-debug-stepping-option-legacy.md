---
title: 'Como: Alterar a opção de passo a passo de depuração (herdado) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 505f876b9c7943c8b039b74459552b77ce539477
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60101113"
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>Como: Alterar a opção de executar a depuração em etapas (herdado)
Este tópico descreve como modificar a opção de avançar de depuração para aplicativos de [!INCLUDE[wf](../includes/wf-md.md)] em novas [!INCLUDE[wfd1](../includes/wfd1-md.md)] que têm ações simultâneas. Use [!INCLUDE[wfd2](../includes/wfd2-md.md)] herdado quando você precisa definir como alvo [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Quando você está depurando as atividades herdados que possuem a execução simultânea, como **ParallelActivity** ou **ConditionedActivityGroup**, você pode usar uma das duas opções para depurar seu código.  
  
 Siga estas etapas para alterar a opção de avançar de depuração no seu projeto herdado de fluxo de trabalho.  
  
## <a name="procedures"></a>Procedimentos  
  
#### <a name="to-change-the-debug-stepping-option"></a>Para alterar a opção de avançar de depuração  
  
1. Inicie o Visual Studio.  
  
2. Abrir um projeto existente herdado de fluxo de trabalho ou criar um novo projeto que empreguem atividades simultâneas e que tem como alvo [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
3. Sobre o **fluxo de trabalho** menu em novas [!INCLUDE[wfd2](../includes/wfd2-md.md)], aponte para **depurar**e, em seguida, aponte para **opções de Avançar**.  
  
4. Selecione a **instância** ou **ramificação**.  
  
## <a name="see-also"></a>Consulte também  
 [Depurando fluxos de trabalho herdado](../workflow-designer/debugging-legacy-workflows.md)   
 [Opções de passo a passo em depuração (herdado)](../workflow-designer/debug-stepping-options-legacy.md)