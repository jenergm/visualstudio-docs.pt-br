---
title: IDebugThread2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2
helpviewer_keywords:
- IDebugThread2 interface
ms.assetid: 221b4b1b-4a26-466e-bc29-5eff800fab13
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9dcb50f732d4c7aae94cf32036cd17340d636dd9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56693692"
---
# <a name="idebugthread2"></a>IDebugThread2
Essa interface representa um thread em execução em um programa.

## <a name="syntax"></a>Sintaxe

```
IDebugThread2 : IUnknown
```

## <a name="notes-for-implementers"></a>Observações para implementadores
 O mecanismo de depuração (DES) implementa essa interface para representar um thread de execução em um único programa.

## <a name="notes-for-callers"></a>Observações para chamadores
 Chame [GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md) para obter essa interface que representa o thread ativo no momento.

 Essa interface também é usada na criação de uma solicitação de ponto de interrupção (consulte [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)).

 Essa interface também é retornada durante a resolução de um ponto de interrupção de limite ou erro (consulte [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) e [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)).

## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable
 A tabela a seguir mostra os métodos de `IDebugThread2`.

|Método|Descrição|
|------------|-----------------|
|[EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)|Recupera uma lista dos quadros de pilhas para este thread.|
|[GetName](../../../extensibility/debugger/reference/idebugthread2-getname.md)|Obtém o nome do thread.|
|[SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)|Define o nome do thread.|
|[GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)|Obtém o programa no qual um thread está em execução.|
|[CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)|Determina se a próxima instrução pode ser definida para o contexto de quadro e o código de ativação.|
|[SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)|Define a próxima instrução para o contexto de quadro e o código de ativação.|
|[GetThreadId](../../../extensibility/debugger/reference/idebugthread2-getthreadid.md)|Obtém o identificador de thread do sistema.|
|[Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md)|Suspende um thread.|
|[Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)|Retoma um thread.|
|[GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)|Obtém as propriedades que descrevem um thread.|
|[GetLogicalThread](../../../extensibility/debugger/reference/idebugthread2-getlogicalthread.md)|Obtém o thread lógico associado a esse thread físico.|

## <a name="remarks"></a>Comentários
 Como um único segmento físico pode ser executado em vários programas, mais de um `IDebugThread2` de mais de um programa pode representar o mesmo thread físico.

 Quando um ponto de interrupção ou exceção ocorre, um evento é enviado ao chamar [evento](../../../extensibility/debugger/reference/idebugeventcallback2-event.md). Um dos argumentos para esse método é um `IDebugThread2` interface que representa o thread atual. [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) é usado para obter o [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) interface para o quadro de pilha atual.

## <a name="requirements"></a>Requisitos
 Header: msdbg.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [Principais interfaces](../../../extensibility/debugger/reference/core-interfaces.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
- [GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)
- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
- [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)