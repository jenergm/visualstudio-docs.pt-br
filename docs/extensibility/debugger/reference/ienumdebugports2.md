---
title: IEnumDebugPorts2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPorts2
helpviewer_keywords:
- IEnumDebugPorts2
ms.assetid: 1754eef3-cf62-42e0-b218-1911acba77d4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b39eff84e1933c6181b3e6ae03bd6055b33570e2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716071"
---
# <a name="ienumdebugports2"></a>IEnumDebugPorts2
Essa interface enumera as portas de um fornecedor de porta ou da máquina.

## <a name="syntax"></a>Sintaxe

```
IEnumDebugPorts2 : IUnknown
```

## <a name="notes-for-implementers"></a>Observações para implementadores
 Um fornecedor de porta personalizada implementa essa interface para representar uma lista de portas criado pelo fornecedor. Visual Studio implementa essa interface para dar suporte a seu próprio fornecedor de porta.

## <a name="notes-for-callers"></a>Observações para chamadores
 Chame [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) para obter essa interface que representa uma lista de portas criado pelo fornecedor de porta. Chame [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md) para obter essa interface que representa uma lista de portas que foram salvos em disco.

## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable
 A tabela a seguir mostra os métodos de `IEnumDebugPorts2`.

|Método|Descrição|
|------------|-----------------|
|[Avançar](../../../extensibility/debugger/reference/ienumdebugports2-next.md)|Recupera um número especificado de portas em uma sequência de enumeração.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugports2-skip.md)|Ignora um número especificado de portas em uma sequência de enumeração.|
|[Reiniciar](../../../extensibility/debugger/reference/ienumdebugports2-reset.md)|Redefine uma sequência de enumeração para o início.|
|[Clonar](../../../extensibility/debugger/reference/ienumdebugports2-clone.md)|Cria um enumerador que contém o mesmo estado de enumeração que o enumerador atual.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugports2-getcount.md)|Obtém o número de portas em um enumerador.|

## <a name="remarks"></a>Comentários
 Visual Studio usa essa interface para ajudar a preencher uma lista de portas usadas para anexar a processos.

 Um mecanismo de depuração normalmente não usa essa interface.

## <a name="requirements"></a>Requisitos
 Header: msdbg.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [Principais interfaces](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)
- [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)