---
title: IDebugModule3 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule3
helpviewer_keywords:
- IDebugModule3 interface
ms.assetid: 44f8e96e-9c59-4ffc-9a08-9c908a0e4de7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 98b506c11ef126d0179b198336e8d969c4eec267
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56721284"
---
# <a name="idebugmodule3"></a>IDebugModule3
Essa interface representa um módulo que dá suporte a locais alternativos de símbolos e estados de JustMyCode.

## <a name="syntax"></a>Sintaxe

```
IDebugModule3 : IDebugModule2
```

## <a name="notes-for-implementers"></a>Observações para implementadores
 O mecanismo de depuração (DES) implementa essa interface para oferecer suporte a locais alternativos de símbolos e para trabalhar com os estados de JustMyCode (consulte a [Glossário do depurador do Visual Studio](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md) para obter uma definição de "JustMyCode").

## <a name="notes-for-callers"></a>Observações para chamadores
 Uma chamada para [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md) retorna essa interface. O envia do [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) interface com o Gerenciador de depuração de sessão (SDM) usando o [evento](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) método. Além disso, uma chamada para [QueryInterface](/cpp/atl/queryinterface) em um [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) interface retorna essa interface.

## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable
 Além dos métodos na [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) interface, essa interface implementa os seguintes métodos:

|Método|Descrição|
|------------|-----------------|
|[GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)|Retorna uma lista de caminhos pesquisados para símbolos e os resultados da pesquisa de cada caminho.|
|[LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)|Carrega e inicializa os símbolos do módulo atual.|
|[IsUserCode](../../../extensibility/debugger/reference/idebugmodule3-isusercode.md)|Sinalizador de retorna Especifica se o módulo representa o código do usuário.|
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugmodule3-setjustmycodestate.md)|Especifica se o módulo deve ser considerado o código do usuário ou não.|

## <a name="remarks"></a>Comentários
 O Visual Studio é o consumidor comum dessa interface.

## <a name="requirements"></a>Requisitos
 Header: msdbg.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [Principais interfaces](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)
- [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)