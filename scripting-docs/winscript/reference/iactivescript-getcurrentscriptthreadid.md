---
title: IActiveScript::GetCurrentScriptThreadID | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetCurrentScriptThreadID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetCurrentScriptThreadID
ms.assetid: b09e8b48-4209-480e-8b71-e99ee9ae2e17
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e1b6e7bae7d78c18e11cd1aac8d0844fb9e90a5
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152243"
---
# <a name="iactivescriptgetcurrentscriptthreadid"></a>IActiveScript::GetCurrentScriptThreadID
Recupera um identificador de script-mecanismo-definidas para o thread em execução no momento. O identificador pode ser usado em chamadas subsequentes para métodos de controle de execução do thread de script, como o [IActiveScript:: Interruptscriptthread](../../winscript/reference/iactivescript-interruptscriptthread.md) método.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT GetCurrentScriptThreadID(  
    SCRIPTTHREADID *pstidThread  // receives scripting thread identifier  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pstidThread`  
 [out] Endereço de uma variável que recebe o identificador de thread de script associado ao thread atual. A interpretação desse identificador é deixada para o mecanismo de script, mas ele pode ser apenas uma cópia do identificador de thread do Windows. Se o thread do Win32 for encerrado, esse identificador se torna não atribuído e, posteriormente, pode ser atribuído a outro thread.  
  
## <a name="return-value"></a>Valor de retorno  
 Retorna `S_OK` se for bem-sucedido, ou `E_POINTER` se um ponteiro inválido foi especificado.  
  
## <a name="remarks"></a>Comentários  
 Esse método pode ser chamado de threads não base sem resultando em um balão não base para objetos de host ou o [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) interface.  
  
## <a name="see-also"></a>Consulte também  
 [IActiveScript](../../winscript/reference/iactivescript.md)