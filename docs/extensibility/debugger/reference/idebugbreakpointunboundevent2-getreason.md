---
title: IDebugBreakpointUnboundEvent2::GetReason | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointUnboundEvent2::GetReason
helpviewer_keywords:
- IDebugBreakpointUnboundEvent2::GetReason
ms.assetid: 0f8a4fec-d3eb-417d-8516-4f7b51904033
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe963923494d5dc68eb2ab3b6fd768036d1c5400
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719087"
---
# <a name="idebugbreakpointunboundevent2getreason"></a>IDebugBreakpointUnboundEvent2::GetReason
Obtém o motivo pelo qual que o ponto de interrupção foi desassociado.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT GetReason(
    BP_UNBOUND_REASON* pdwUnboundReason
);
```

```csharp
int GetReason(
    out enum_ BP_UNBOUND_REASON pdwUnboundReason
);
```

#### <a name="parameters"></a>Parâmetros
`pdwUnboundReason`

 [out] Retorna um valor da [BP_UNBOUND_REASON](../../../extensibility/debugger/reference/bp-unbound-reason.md) enumeração que especifica o motivo pelo qual o ponto de interrupção foi desassociado.

## <a name="return-value"></a>Valor de retorno
Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
Os motivos incluem um ponto de interrupção que está sendo religado para um local diferente após uma operação de editar e continuar, ou a uma determinação de que um ponto de interrupção foi vinculado em erro.

## <a name="example"></a>Exemplo
O exemplo a seguir mostra como implementar esse método para um **CBreakpointUnboundDebugEventBase** objeto que expõe a [IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md) interface.

```cpp
STDMETHODIMP CBreakpointUnboundDebugEventBase::GetReason(
    BP_UNBOUND_REASON* pdwUnboundReason)
{
    HRESULT hRes = E_FAIL;

    if ( EVAL(pdwUnboundReason) )
    {
        *pdwUnboundReason = m_dwReason;

        hRes = S_OK;
    }
    else
        hRes = E_INVALIDARG;

    return ( hRes );
}
```

## <a name="see-also"></a>Consulte também
- [IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)
