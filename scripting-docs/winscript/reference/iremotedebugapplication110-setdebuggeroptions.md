---
title: IRemoteDebugApplication110::SetDebuggerOptions | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110::SetDebuggerOptions
ms.assetid: 58e9fd18-3e0d-47fa-8893-f316146bde84
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 511d1f8b25aee4637455e3a5b8946f81f7410d65
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150823"
---
# <a name="iremotedebugapplication110setdebuggeroptions"></a>IRemoteDebugApplication110::SetDebuggerOptions
Chamado para atualizar as opções do depurador. Esse método deve ser chamado após [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md). O [IRemoteDebugApplication::DisconnectDebugger](../../winscript/reference/iremotedebugapplication-disconnectdebugger.md) método redefine automaticamente para as opções padrão. O padrão de opções como 0 (SDO_NONE).  
  
> [!IMPORTANT]
>  [IRemoteDebugApplication Interface](../../winscript/reference/iremotedebugapplication-interface.md) é implementada pelo PDM v11.0 e maior. Localizado em. activdbg100.h.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetDebuggerOptions(        [in] enum SCRIPT_DEBUGGER_OPTIONS mask,        [in] enum SCRIPT_DEBUGGER_OPTIONS value    );  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `mask`  
 O [enumeração SCRIPT_DEBUGGER_OPTIONS](../../winscript/reference/script-debugger-options-enumeration.md) máscara.  
  
 `value`  
 O [enumeração SCRIPT_DEBUGGER_OPTIONS](../../winscript/reference/script-debugger-options-enumeration.md) valor.  
  
## <a name="see-also"></a>Consulte também  
 [Interface IRemoteDebugApplication](../../winscript/reference/iremotedebugapplication-interface.md)   
 [Interface IRemoteDebugApplication110](../../winscript/reference/iremotedebugapplication110-interface.md)