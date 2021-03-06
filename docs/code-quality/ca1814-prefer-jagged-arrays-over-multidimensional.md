---
title: 'CA1814: Preferir matrizes denteadas a matrizes multidimensionais'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
helpviewer_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
ms.assetid: b1ccf563-2ec8-42e5-b89c-731a9de1ea1d
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 6d3dc26964a62c952b9c8d18c710e6163bf8ab08
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955317"
---
# <a name="ca1814-prefer-jagged-arrays-over-multidimensional"></a>CA1814: Preferir matrizes denteadas a matrizes multidimensionais

|||
|-|-|
|NomeDoTipo|PreferJaggedArraysOverMultidimensional|
|CheckId|CA1814|
|Categoria|Microsoft.Performance|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um membro é declarado como uma matriz multidimensional.

## <a name="rule-description"></a>Descrição da regra
 Uma matriz denteada é uma matriz cujos elementos são matrizes. As matrizes que constituem os elementos podem ter tamanhos diferentes, o que leva a menos espaço desperdiçado para alguns conjuntos de dados.

## <a name="how-to-fix-violations"></a>Como corrigir violações
 Para corrigir uma violação dessa regra, altere a matriz multidimensional para uma matriz denteada.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos
 Suprima um aviso nessa regra, se a matriz multidimensional não perde espaço.

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra declarações de matrizes denteadas e multidimensionais.

 [!code-vb[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/VisualBasic/ca1814-prefer-jagged-arrays-over-multidimensional_1.vb)]
 [!code-csharp[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/CSharp/ca1814-prefer-jagged-arrays-over-multidimensional_1.cs)]