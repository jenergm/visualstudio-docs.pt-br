---
title: 'CA1051: Não declarar campos de instância visíveis | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 874541972df030d55721b78f115b730e625a7b02
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58923939"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: Não declarar campos de instância visíveis
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Categoria|Microsoft.Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um tipo visível externamente tem um campo de instância visíveis externamente.

## <a name="rule-description"></a>Descrição da Regra
 O principal uso de um campo deve ser um como um detalhe da implementação. Os campos devem ser `private` ou `internal` e devem ser expostos por meio de propriedades. Ele é tão fácil acessar uma propriedade que ela acessar um campo, e o código nos acessadores de uma propriedade pode alterar como os recursos do tipo expandem sem introduzir alterações significativas. Propriedades que retornam apenas o valor de um campo privado ou interno são otimizadas para executar no mesmo nível de acesso a um campo; muito pouco ganho de desempenho está associado com o uso de campos visíveis externamente em Propriedades.

 Refere-se visível externamente ao `public`, `protected`, e `protected internal` (`Public`, `Protected`, e `Protected Friend` no Visual Basic) níveis de acessibilidade.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, tornar o campo `private` ou `internal` e expô-lo por meio de uma propriedade visível externamente.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Não suprima um aviso nessa regra. Campos visíveis externamente não fornecem todos os benefícios que não estão disponíveis para as propriedades. Além disso, os campos públicos não podem ser protegidos por [demandas de Link](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d). Consulte [CA2112: Tipos seguros não devem expor campos](../code-quality/ca2112-secured-types-should-not-expose-fields.md).

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra um tipo (`BadPublicInstanceFields`) que viola essa regra. `GoodPublicInstanceFields` mostra o código corrigido.

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TypesPublicInstanceFields/cs/FxCop.Design.TypesPublicInstanceFields.cs#1)]

## <a name="related-rules"></a>Regras relacionadas
 [CA2112: Tipos seguros não devem expor campos](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>Consulte também
 [Demandas de link](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)
