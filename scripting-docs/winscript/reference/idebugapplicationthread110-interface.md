---
title: IDebugApplicationThread110 Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110 Interface
ms.assetid: 25bc351f-3451-4387-9302-078f6292ddff
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a40b1a6f194ef0f335d8c6516b101250b0d980fe
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58158403"
---
# <a name="idebugapplicationthread110-interface"></a>Interface IDebugApplicationThread110
Fornece mais funcionalidade para o [IDebugApplicationThread Interface](../../winscript/reference/idebugapplicationthread-interface.md) interface.  
  
> [!IMPORTANT]
>  Esta interface é implementada pelo PDM v11.0 e superiores. Localizado em. activdbg100.h.  
  
## <a name="methods"></a>Métodos  
 A interface `IDebugApplicationThread110` expõe os métodos a seguir.  
  
|Método|Descrição|  
|------------|-----------------|  
|[IDebugApplicationThread110::AsynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread110-asynchronouscallintothread.md)|Faz uma chamada assíncrona no thread principal.|  
|[IDebugApplicationThread110::GetActiveThreadRequestCount](../../winscript/reference/idebugapplicationthread110-getactivethreadrequestcount.md)|Uma contagem de quantas solicitações de segmento de thread do PDM alternância mecanismos de processamento no momento. Normalmente, 0 ou 1, mas ele 's possível para isso será maior se uma chamada thread inicia o processamento, mas dispara uma chamada síncrona fora do thread ou caso contrário, suspende o thread (por exemplo, ao acionar um evento IDebugApplicationEvents emitida no depurador thread)|  
|[IDebugApplicationThread110::IsSuspendedForBreakPoint](../../winscript/reference/idebugapplicationthread110-issuspendedforbreakpoint.md)|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md) foi chamado nesse thread e ainda não foi concluída.|  
|[IDebugApplicationThread110::IsThreadCallable](../../winscript/reference/idebugapplicationthread110-isthreadcallable.md)|Esse thread está em um estado que possa processar chamadas feitas com o uso de alternância de threads do PDM mecanismos (como SynchronousCallInThread).|