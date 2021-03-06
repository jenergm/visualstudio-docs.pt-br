---
title: 'CA2231: Sobrecarregar operador equals ao substituir ValueType.Equals'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
- OverrideOperatorEqualsOnOverridingValueTypeEquals
helpviewer_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
ms.assetid: 114c0161-261a-40ad-8b2c-0932d6909d2a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 81c9a94e318638837fb4ab8fe1a822dc0cfec46a
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57872750"
---
# <a name="ca2231-overload-operator-equals-on-overriding-valuetypeequals"></a>CA2231: Sobrecarregar operador equals ao substituir ValueType.Equals

|||
|-|-|
|NomeDoTipo|OverloadOperatorEqualsOnOverridingValueTypeEquals|
|CheckId|CA2231|
|Categoria|Microsoft.Usage|
|Alteração Significativa|Não separável|

## <a name="cause"></a>Causa

Um tipo de valor substitui <xref:System.Object.Equals%2A?displayProperty=fullName> mas não implementa o operador de igualdade.

Por padrão, essa regra olha apenas tipos visíveis externamente, mas isso é [configurável](#configurability).

## <a name="rule-description"></a>Descrição da regra

Na maioria das linguagens de programação, não há nenhuma implementação padrão do operador de igualdade (= =) para tipos de valor. Se sua linguagem de programação der suporte a sobrecargas de operador, você deve considerar implementar o operador de igualdade. Deve ser idêntico de seu comportamento <xref:System.Object.Equals%2A>.

Você não pode usar o operador de igualdade padrão em uma implementação sobrecarregada do operador de igualdade. Isso fará com que um estouro de pilha. Para implementar o operador de igualdade, use o método Object. Equals em sua implementação. Por exemplo:

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>Como corrigir violações

Para corrigir uma violação dessa regra, implemente o operador de igualdade.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos

É seguro suprimir um aviso nessa regra; No entanto, é recomendável que você forneça o operador de igualdade se possível.

## <a name="configurability"></a>Capacidade de configuração

Se você estiver executando essa regra de [analisadores FxCop](install-fxcop-analyzers.md) (e não por meio de análise de código estático), você pode configurar quais partes da sua base de código para executar essa regra, com base na sua acessibilidade. Por exemplo, para especificar que a regra deve ser executado apenas em relação a superfície de API não público, adicione o seguinte par de chave-valor para um arquivo. editorconfig em seu projeto:

```
dotnet_code_quality.ca2231.api_surface = private, internal
```

Você pode configurar essa opção para apenas essa regra, para todas as regras ou para todas as regras nessa categoria (uso). Para obter mais informações, consulte [analisadores FxCop configurar](configure-fxcop-analyzers.md).

## <a name="example"></a>Exemplo

O exemplo a seguir define um tipo que viola essa regra:

[!code-csharp[FxCop.Usage.EqualsGetHashCode#1](../code-quality/codesnippet/CSharp/ca2231-overload-operator-equals-on-overriding-valuetype-equals_1.cs)]

## <a name="related-rules"></a>Regras relacionadas

- [CA1046: Não sobrecarregar operador equals em tipos de referência](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2225: Sobrecargas de operador possuem alternativas nomeadas](../code-quality/ca2225-operator-overloads-have-named-alternates.md)
- [CA2226: Os operadores devem ter sobrecargas simétricas](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224: Substituir equals ao sobrecarregar operador equals](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218: Substituir GetHashCode em igualdades de substituição](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

## <a name="see-also"></a>Consulte também

- <xref:System.Object.Equals%2A?displayProperty=fullName>