---
title: IDebugProcess2::GetProcessId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetProcessId
helpviewer_keywords:
- IDebugProcess2::GetProcessId
ms.assetid: d5b6f03c-d49d-4b83-b072-016ac3124f5f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b927d5a8da316faa76b5d102ad0cfb14e0cb61e7
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706646"
---
# <a name="idebugprocess2getprocessid"></a>IDebugProcess2::GetProcessId
Obtém o GUID para este processo.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT GetProcessId(
   GUID* pguidProcessId
);
```

```csharp
int GetProcessId(
   out Guid pguidProcessId
);
```

#### <a name="parameters"></a>Parâmetros
 `pguidProcessId`

 [out] Retorna o GUID para este processo.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
 O identificador global exclusivo (GUID) identifica esse processo de todos os outros processos em execução no sistema.

## <a name="see-also"></a>Consulte também
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)