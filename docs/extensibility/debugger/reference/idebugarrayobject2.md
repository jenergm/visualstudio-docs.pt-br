---
title: IDebugArrayObject2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugArrayObject2 interface
ms.assetid: be6e504d-4ab3-4141-a61b-0953ee0e038e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 89130c43e38bc53e0efeb93325df94e7076d9ef1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56691950"
---
# <a name="idebugarrayobject2"></a>IDebugArrayObject2
> [!IMPORTANT]
>  No Visual Studio 2015, essa forma de implementar os avaliadores de expressão foi preterida. Para obter informações sobre como implementar os avaliadores de expressão de CLR, consulte [avaliadores de expressão de CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) e [amostra do avaliador de expressão gerenciado](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Representa um objeto de matriz gerenciada e permite que um avaliador de expressão (EE) para determinar o índice de base (limites inferiores) para a matriz.

## <a name="syntax"></a>Sintaxe

```
IDebugArrayObject2 : IDebugArrayObject
```

## <a name="notes-for-implementers"></a>Observações para implementadores
 Isso é implementado pelo mecanismo de depuração gerenciados (DES).

## <a name="methods"></a>Métodos
 Além dos métodos na [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) interface, essa interface implementa os seguintes métodos:

|Método|Descrição|
|------------|-----------------|
|[GetBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-getbaseindices.md)|Recupera o índice de base (limites inferiores) para cada índice devido ao número de dimensões na matriz.|
|[HasBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-hasbaseindices.md)|Determina se a matriz tem base índices (limites inferiores) definidos.|

## <a name="remarks"></a>Comentários
 Um avaliador de expressão usa essa interface para representar matrizes gerenciadas em uma árvore de análise.

## <a name="requirements"></a>Requisitos
 Cabeçalho: EE.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll