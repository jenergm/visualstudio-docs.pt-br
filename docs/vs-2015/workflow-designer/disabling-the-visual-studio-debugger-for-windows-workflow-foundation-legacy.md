---
title: Desabilitando o depurador para o Windows Workflow Foundation (herdado) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- workflows, disabling debugger
- debugging workflows, disabling debugger
- workflow debugger, disabling
ms.assetid: 9da96d0e-f941-4fa9-a1a5-6bab50adfec9
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e5065de4ec0217123f76eb23d32bcb0facd25dcc
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58924764"
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Desativando o depurador do Visual Studio para Windows Workflow Foundation (legados)
Este tópico descreve como desativar o depurador de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] que usa o arquivo de configuração para criar aplicativos de [!INCLUDE[wf](../includes/wf-md.md)] em [!INCLUDE[wfd1](../includes/wfd1-md.md)]herdado. Use [!INCLUDE[wfd2](../includes/wfd2-md.md)] herdado quando você precisa definir como alvo [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].

 Por padrão, o depurador de [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] para [!INCLUDE[wf](../includes/wf-md.md)] é habilitado para um processo host. Para desabilitar a depuração de fluxo de trabalho, você deve explicitamente desativá-lo adicionando uma entrada de "DisableWorkflowDebugging"  **\<switches >** elemento no  **\<System. Diagnostics >** seção do arquivo de configuração de host.

 O exemplo a seguir mostra como modificar o arquivo de configuração do host para desativar a depuração de fluxo de trabalho.

```
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <system.diagnostics>
      <switches>
         <add name="DisableWorkflowDebugging" value="true"/>
      </switches>
   </system.diagnostics>
</configuration>
```

## <a name="see-also"></a>Consulte também
 [Invocar o depurador do Visual Studio para Windows Workflow Foundation (herdado)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md) [depurando fluxos de trabalho herdado](../workflow-designer/debugging-legacy-workflows.md)