---
title: IDebugFunctionPosition2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionPosition2
helpviewer_keywords:
- IDebugFunctionPosition2 interface
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: faed38853aa7d0d925a3b1e598627cf1a55166d1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689909"
---
# <a name="idebugfunctionposition2"></a>IDebugFunctionPosition2
Essa interface representa uma posição abstrata de uma função em um documento de origem.

## <a name="syntax"></a>Sintaxe

```
IDebugFunctionPosition2 : IUnknown
```

## <a name="notes-for-implementers"></a>Observações para implementadores
 O mecanismo de depuração (DES) implementa essa interface para representar a posição de uma função dentro de um documento de origem.

## <a name="notes-for-callers"></a>Observações para chamadores
 Essa interface é fornecida como parte de um [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) união (especificamente, um [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) estrutura) que por sua vez faz parte dos [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) estrutura, usada na criação de um ponto de interrupção pendente.

## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable
 A tabela a seguir mostra os métodos de `IDebugFunctionPosition2`.

|Método|Descrição|
|------------|-----------------|
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|Obtém o nome da função que esta posição é relativo.|
|[GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|Obtém o deslocamento do início da função.|

## <a name="remarks"></a>Comentários
 A posição representada por esta interface é baseado em texto, especificamente, uma [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) estrutura.

## <a name="requirements"></a>Requisitos
 Header: msdbg.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [Principais interfaces](../../../extensibility/debugger/reference/core-interfaces.md)
- [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)
- [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)
- [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)