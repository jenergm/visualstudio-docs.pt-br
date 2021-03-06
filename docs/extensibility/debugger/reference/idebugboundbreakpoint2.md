---
title: IDebugBoundBreakpoint2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBoundBreakpoint2
helpviewer_keywords:
- IDebugBoundBreakpoint2 interface
ms.assetid: df33c52e-ded2-48a0-951d-1f36c8fc922e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: da29303059558a4cf43eddb1d6e03e8848df4f4c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689792"
---
# <a name="idebugboundbreakpoint2"></a>IDebugBoundBreakpoint2
Essa interface representa um ponto de interrupção que está associado a um local de código.

## <a name="syntax"></a>Sintaxe

```
IDebugBoundBreakpoint2 : IUnknown
```

## <a name="notes-for-implementers"></a>Observações para implementadores
 O mecanismo de depuração (DES) implementa essa interface como parte de seu suporte para pontos de interrupção.

## <a name="notes-for-callers"></a>Observações para chamadores
 Uma chamada para [associar](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) cria essa interface. Chamadas para [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md) e [próxima](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md) também pode obter essa interface.

## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable
 A tabela a seguir mostra os métodos de `IDebugBoundBreakpoint2`.

|Método|Descrição|
|------------|-----------------|
|[GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|Obtém o ponto de interrupção pendente da qual o ponto de interrupção associado especificado foi criado.|
|[GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|Obtém o estado deste ponto de interrupção associada.|
|[GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md)|Obtém a contagem de ocorrências atual para este ponto de interrupção associado.|
|[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|Obtém a resolução de ponto de interrupção que descreve este ponto de interrupção.|
|[Habilitar](../../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|Habilita ou desabilita o ponto de interrupção.|
|[SetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-sethitcount.md)|Define a contagem de ocorrências para esse ponto de interrupção associada.|
|[SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)|Define ou altera a condição associada a este ponto de interrupção associado.|
|[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)|Define ou alterar a contagem de passagem associada a este ponto de interrupção associado.|
|[Excluir](../../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|Exclui o ponto de interrupção.|

## <a name="requirements"></a>Requisitos
 Header: msdbg.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)
- [Avançar](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)
- [Associar](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)