---
title: IDebugPort2::GetPortSupplier | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPort2::GetPortSupplier
helpviewer_keywords:
- IDebugPort2::GetPortSupplier
ms.assetid: 7a7b0615-df6b-4726-ab35-39dfa1ebed8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5bbbbf620d9a5b78c098ec593dd20c57a18d79ee
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719118"
---
# <a name="idebugport2getportsupplier"></a>IDebugPort2::GetPortSupplier
Obtém o fornecedor de porta para essa porta.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT GetPortSupplier( 
   IDebugPortSupplier2** ppSupplier
);
```

```csharp
int GetPortSupplier( 
   out IDebugPortSupplier2 ppSupplier
);
```

#### <a name="parameters"></a>Parâmetros
 `ppSupplier`

 [out] Retorna um [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) objeto representa o fornecedor de porta para uma porta.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="see-also"></a>Consulte também
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)