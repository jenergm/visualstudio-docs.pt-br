---
title: 'CA1011: Considerar a passagem de tipos base como parâmetros'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 644c581757a559311b6660a77c4d9190a7361314
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55916551"
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: Considerar a passagem de tipos base como parâmetros

|||
|-|-|
|NomeDoTipo|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|Categoria|Microsoft.Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa

Uma declaração de método inclui um parâmetro formal que é um tipo derivado e o método chama apenas os membros do tipo base do parâmetro.

## <a name="rule-description"></a>Descrição da regra

Quando um tipo de base é especificado como um parâmetro em uma declaração de método, qualquer tipo derivado do tipo de base pode ser passado como o argumento correspondente ao método. Quando o argumento é usado dentro do corpo do método, o método específico que é executado depende do tipo do argumento. Se a funcionalidade adicional que é fornecida por um tipo derivado não for necessária, o uso do tipo base permite um uso mais amplo do método.

## <a name="how-to-fix-violations"></a>Como corrigir violações

Para corrigir uma violação dessa regra, altere o tipo do parâmetro para seu tipo base.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos

É seguro suprimir um aviso nessa regra

- Se o método requer a funcionalidade específica que é fornecida por um tipo derivado

     \- ou -

- para impor que apenas o tipo derivado, ou um tipo mais derivado, é passado para o método.

Nesses casos, o código será mais robusto devido à forte verificação de tipo que é fornecido pelo compilador e tempo de execução.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um método `ManipulateFileStream`, que pode ser usado apenas com um <xref:System.IO.FileStream> objeto, o que viola essa regra. Um segundo método, `ManipulateAnyStream`, satisfaz a regra, substituindo o <xref:System.IO.FileStream> parâmetro usando um <xref:System.IO.Stream>.

[!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CSharp/ca1011-consider-passing-base-types-as-parameters_1.cs)]
[!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CPP/ca1011-consider-passing-base-types-as-parameters_1.cpp)]
[!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1011-consider-passing-base-types-as-parameters_1.vb)]

## <a name="related-rules"></a>Regras relacionadas

[CA1059: Os membros não devem expor certos tipos concretos](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)