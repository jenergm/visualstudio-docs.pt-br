---
title: Classe VsgDbg | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6722263c-ccef-40c7-a0ae-87a863fbab00
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 053647d48324f056148375bae9268b997ba8721f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58929506"
---
# <a name="vsgdbg-class"></a>Classe VsgDbg
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Representa uma interface para o controle programático do componente no aplicativo do diagnóstico de gráficos.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
class VsgDbg;  
```  
  
## <a name="members"></a>Membros  
 O `VsgDbg` classe oferece suporte aos seguintes membros.  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[VsgDbg::VsgDbg (Construtor)](../debugger/vsgdbg-vsgdbg-constructor.md)|Constrói uma instância do `VsgDbg` de classe e, opcionalmente, prepara o componente no aplicativo de diagnóstico de gráficos para capturar ativamente e registrar informações de gráficos.|  
|[VsgDbg::~VsgDbg (Destruidor)](../debugger/vsgdbg-tilde-vsgdbg-destructor.md)|Destrói uma instância da `VsgDbg` classe.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[AddMessage](../debugger/addmessage.md)|Adiciona uma mensagem personalizada para o diagnóstico de gráficos HUD (Head-Up Display).|  
|[BeginCapture](../debugger/begincapture.md)|Inicia um intervalo de captura que terminará com `EndCapture`.|  
|[CaptureCurrentFrame](../debugger/capturecurrentframe.md)|Captura o restante do quadro atual para o arquivo de log de gráficos.|  
|[Copiar (captura programática)](../debugger/copy-programmatic-capture.md)|Copia o conteúdo do arquivo de log (. vsglog) de elementos gráficos ativos em um novo arquivo.|  
|[EndCapture](../debugger/endcapture.md)|Termina um intervalo de captura foi iniciado com `BeginCapture`.|  
|[Init](../debugger/init.md)|Prepara o componente no aplicativo de diagnóstico de gráficos para capturar ativamente e registrar informações de gráficos.|  
|[ToggleHUD](../debugger/togglehud.md)|Alterna a sobreposição HUD do diagnóstico de gráficos ativada ou desativada.|  
|[UnInit](../debugger/uninit.md)|Finaliza o arquivo de log de gráficos, fecha e libera os recursos que foram usados enquanto o aplicativo ativamente estava gravando informações de gráficos.|  
  
## <a name="remarks"></a>Comentários  
 O `VsgDbg` classe representa uma interface que você pode usar para controlar recursos de diagnóstico de gráficos programaticamente. Você pode usar alguns recursos mesmo quando você estiver ativamente capturar e registrar informações de gráficos; Isso inclui o `AddMessage` função de membro e `ToggleHUD` função de membro. As outras funções de membro ou preparar o componente no aplicativo de diagnóstico de gráficos para iniciar ou parar a captura de ativa de informações de gráficos ou devem ser chamadas enquanto o aplicativo está ativamente capturando e gravar informações de gráficos em um arquivo de log de gráficos.
