---
title: 'CA1004: Métodos genéricos devem fornecer um parâmetro de tipo'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1004
- GenericMethodsShouldProvideTypeParameter
helpviewer_keywords:
- GenericMethodsShouldProvideTypeParameter
- CA1004
ms.assetid: 38755f6a-fb45-4bf2-932e-0354ad826499
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 94c21a81a7473e1697609ff3e46eb054ad304540
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955356"
---
# <a name="ca1004-generic-methods-should-provide-type-parameter"></a>CA1004: Métodos genéricos devem fornecer um parâmetro de tipo

|||
|-|-|
|NomeDoTipo|GenericMethodsShouldProvideTypeParameter|
|CheckId|CA1004|
|Categoria|Microsoft.Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 A assinatura do parâmetro de um método genérico visível externamente não contém tipos que correspondem a todos os parâmetros de tipo do método.

## <a name="rule-description"></a>Descrição da regra
 Inferência é como o argumento de tipo de um método genérico é determinado pelo tipo de argumento passado para o método, em vez da especificação explícita do argumento de tipo. Para habilitar a inferência, a assinatura do parâmetro de um método genérico deve incluir um parâmetro que seja do mesmo tipo do parâmetro de tipo para o método. Nesse caso, o argumento de tipo não precisa ser especificado. Quando você usa a inferência de tipos para todos os parâmetros de tipo, a sintaxe para chamar métodos de instância genéricas e é idêntica. Isso simplifica a usabilidade de métodos genéricos.

## <a name="how-to-fix-violations"></a>Como corrigir violações
 Para corrigir uma violação dessa regra, altere o design para que a assinatura do parâmetro contém o mesmo tipo para cada parâmetro de tipo do método.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos
 Não suprima um aviso nessa regra. Fornecer genéricos em uma sintaxe fácil de entender e usar reduz o tempo que é necessário para saber mais e aumenta a taxa de adoção de novas bibliotecas.

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra a sintaxe para chamar os dois métodos genéricos. O argumento de tipo para `InferredTypeArgument` é inferido e o argumento de tipo para `NotInferredTypeArgument` deve ser especificado explicitamente.

 [!code-vb[FxCop.Design.Inference#1](../code-quality/codesnippet/VisualBasic/ca1004-generic-methods-should-provide-type-parameter_1.vb)]
 [!code-csharp[FxCop.Design.Inference#1](../code-quality/codesnippet/CSharp/ca1004-generic-methods-should-provide-type-parameter_1.cs)]

## <a name="related-rules"></a>Regras relacionadas
 [CA1005: Evitar parâmetros excessivos em tipos genéricos](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: As coleções devem implementar a interface genérica](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Não declarar membros estáticos em tipos genéricos](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: Não expor listas genéricas](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Não aninhar tipos genéricos em assinaturas de membro](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1003: Usar instâncias do manipulador de eventos genéricos](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Usar genéricos quando apropriado](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Consulte também
 [Genéricos](/dotnet/csharp/programming-guide/generics/index)