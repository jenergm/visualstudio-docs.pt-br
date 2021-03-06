---
title: 'CA1051: Não declarar campos de instância visíveis'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b7a2165b9b921865ce1fd45017c996e48917d12
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57872810"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: Não declarar campos de instância visíveis

|||
|-|-|
|NomeDoTipo|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Categoria|Microsoft.Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa

Um tipo tem um campo de instância não privado.

Por padrão, essa regra olha apenas tipos visíveis externamente, mas isso é [configurável](#configurability).

## <a name="rule-description"></a>Descrição da regra

O principal uso de um campo deve ser um como um detalhe da implementação. Os campos devem ser `private` ou `internal` e devem ser expostos por meio de propriedades. Ele é tão fácil acessar uma propriedade que ela acessar um campo, e o código nos acessadores de uma propriedade pode alterar como os recursos do tipo expandem sem introduzir alterações significativas. Propriedades que retornam apenas o valor de um campo privado ou interno são otimizadas para executar no mesmo nível de acesso a um campo; muito pouco ganho de desempenho está associado com o uso de campos visíveis externamente em Propriedades.

Refere-se visível externamente ao `public`, `protected`, e `protected internal` (`Public`, `Protected`, e `Protected Friend` no Visual Basic) níveis de acessibilidade.

## <a name="how-to-fix-violations"></a>Como corrigir violações

Para corrigir uma violação dessa regra, tornar o campo `private` ou `internal` e expô-lo por meio de uma propriedade visível externamente.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos

Não suprima um aviso nessa regra. Campos visíveis externamente não fornecem todos os benefícios que não estão disponíveis para as propriedades. Além disso, os campos públicos não podem ser protegidos por [demandas de Link](/dotnet/framework/misc/link-demands). Consulte [CA2112: Tipos seguros não devem expor campos](../code-quality/ca2112-secured-types-should-not-expose-fields.md).

## <a name="configurability"></a>Capacidade de configuração

Se você estiver executando essa regra de [analisadores FxCop](install-fxcop-analyzers.md) (e não por meio de análise de código estático), você pode configurar quais partes da sua base de código para executar essa regra, com base na sua acessibilidade. Por exemplo, para especificar que a regra deve ser executado apenas em relação a superfície de API não público, adicione o seguinte par de chave-valor para um arquivo. editorconfig em seu projeto:

```
dotnet_code_quality.ca1051.api_surface = private, internal
```

Você pode configurar essa opção para apenas essa regra, para todas as regras ou para todas as regras nessa categoria (Design). Para obter mais informações, consulte [analisadores FxCop configurar](configure-fxcop-analyzers.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um tipo (`BadPublicInstanceFields`) que viola essa regra. `GoodPublicInstanceFields` mostra o código corrigido.

[!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>Regras relacionadas

- [CA2112: Tipos seguros não devem expor campos](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>Consulte também

- [Demandas de link](/dotnet/framework/misc/link-demands)