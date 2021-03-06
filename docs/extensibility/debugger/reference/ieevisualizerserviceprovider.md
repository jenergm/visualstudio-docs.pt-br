---
title: IEEVisualizerServiceProvider | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerServiceProvider
helpviewer_keywords:
- IEEVisualizerServiceProvider interface
ms.assetid: 859d1a51-1c65-4c8b-ae74-3b74b181ebcd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 63e6893d407ebcb26a62aeb038b0cf670659f536
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718349"
---
# <a name="ieevisualizerserviceprovider"></a>IEEVisualizerServiceProvider
> [!IMPORTANT]
>  No Visual Studio 2015, essa forma de implementar os avaliadores de expressão foi preterida. Para obter informações sobre como implementar os avaliadores de expressão de CLR, consulte [avaliadores de expressão de CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) e [amostra do avaliador de expressão gerenciado](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Essa interface fornece acesso a um método que pode criar um serviço de visualização simultânea, o que é usado para lidar com tarefas de Visualizador de tipo para o IDE.

## <a name="syntax"></a>Sintaxe

```
IEEVisualizerServiceProvider : IUnknown
```

## <a name="notes-for-implementers"></a>Observações para implementadores
 Visual Studio implementa essa interface para criar um objeto de serviço do visualizador, que por sua vez é usado para fornecer IDs de classe (`CLSID`s) de visualizadores de tipo para o IDE do Visual Studio.

## <a name="notes-for-callers"></a>Observações para chamadores
 O avaliador de expressão (EE) chama [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md) para obter essa interface.

## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable

|Método|Descrição|
|------------|-----------------|
|[CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)|Cria o serviço Visualizador|

## <a name="remarks"></a>Comentários
 O `IEEVisualizerServiceProvider` interface é obtido durante a implementação [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). O serviço de visualização simultânea cria essa interface é usado para fornecer funcionalidade para um [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) interface, que o EE é responsável pela implementação. O EE também é responsável por implementar uma [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) interface que permite que os visualizadores de tipo exibir e modificar o valor da propriedade.

 Ver [visualização e exibindo os dados](../../../extensibility/debugger/visualizing-and-viewing-data.md) para obter detalhes sobre como essas interfaces interagem.

## <a name="requirements"></a>Requisitos
 Cabeçalho: ee.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [Interfaces de Avaliação de Expressões](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)
- [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
- [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [Visualizar e exibir dados](../../../extensibility/debugger/visualizing-and-viewing-data.md)