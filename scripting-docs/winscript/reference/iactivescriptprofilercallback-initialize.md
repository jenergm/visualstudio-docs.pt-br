---
title: IActiveScriptProfilerCallback::Initialize | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.Initialize
apilocation:
- scrobj.dll
ms.assetid: a257111e-a50b-4962-9dd6-c893d40f6985
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66ef6dc37e1f2f8117e440089ee36958d616dda0
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58158273"
---
# <a name="iactivescriptprofilercallbackinitialize"></a>IActiveScriptProfilerCallback::Initialize
Chamado para inicializar o objeto do criador de perfil sempre que a criação de perfil é iniciada em um mecanismo de script.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT Initialize(  
    [in] DWORD dwContext);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `dwContext`  
 [in] Um valor de 4 bytes que é passado para [IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md).  
  
## <a name="return-value"></a>Valor de retorno  
 Retorna um HRESULT. Os valores possíveis são:  
  
|Valor de retorno|Significado|  
|------------------|-------------|  
|`S_OK`|O método foi bem-sucedido.|  
  
## <a name="remarks"></a>Comentários  
 Se o método não é possível inicializar o objeto do criador de perfil, ele deverá retornar uma falha HRESULT para notificar o mecanismo de script. Nesse caso, o mecanismo de script deve chamar diretamente [IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md), transmitindo o HRESULT no parâmetro e, em seguida, liberar o objeto de criador de perfil.  
  
## <a name="see-also"></a>Consulte também  
 [Interface IActiveScriptProfilerCallback](../../winscript/reference/iactivescriptprofilercallback-interface.md)