---
title: IEnumDebugPortSuppliers2::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPortSuppliers2::Skip
helpviewer_keywords:
- IEnumDebugPortSuppliers2::Skip
ms.assetid: bd95d7e9-274f-485d-8bf6-865306ae1b81
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ab1132ff1b0714a1c916a7a02f84ffed95ac61b8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716812"
---
# <a name="ienumdebugportsuppliers2skip"></a>IEnumDebugPortSuppliers2::Skip
Ignora o número especificado de elementos.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT Skip(
   ULONG celt
);
```

```csharp
int Skip(
   uint celt
);
```

#### <a name="parameters"></a>Parâmetros
 `celt`

 [in] Número de elementos a serem ignorados.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`. Retorna `S_FALSE` se `celt` é maior que o número de elementos restantes; caso contrário, retornará um código de erro.

## <a name="remarks"></a>Comentários
 Se `celt` Especifica um valor maior que o número de elementos restantes, a enumeração é definida como o fim e `S_FALSE` é retornado.

## <a name="see-also"></a>Consulte também
- [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)