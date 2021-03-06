---
title: 'CA2234: Passar objetos System.Uri em vez de cadeias de caracteres'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 97b73793d0c473727960dbde8fe32fc584ff6dd5
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57869200"
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234: Passar objetos System.Uri em vez de cadeias de caracteres

|||
|-|-|
|NomeDoTipo|PassSystemUriObjectsInsteadOfStrings|
|CheckId|CA2234|
|Categoria|Microsoft.Usage|
|Alteração Significativa|Não separável|

## <a name="cause"></a>Causa

É feita uma chamada para um método que tem um parâmetro de cadeia de caracteres cujo nome contém "uri", "Uri", "urn", "Urn", "url" ou "Url" e o tipo de declaração do método contém uma sobrecarga do método correspondente que tenha um <xref:System.Uri?displayProperty=fullName> parâmetro.

Por padrão, essa regra olha apenas para tipos e métodos visíveis externamente, mas isso é [configurável](#configurability).

## <a name="rule-description"></a>Descrição da regra

Um nome de parâmetro é dividido em tokens com base na convenção camel case e, em seguida, cada token é verificado para ver se é igual a "uri", "Uri", "urn", "Urn", "url" ou "Url". Se houver uma correspondência, o parâmetro será assumido para representar um uniform resource identifier (URI). Uma representação de cadeia de caracteres de um URI está propensa a erros de análise e de codificação, e pode resultar em vulnerabilidades de segurança. O <xref:System.Uri> classe fornece esses serviços de maneira segura e protegida. Quando há uma escolha entre duas sobrecargas que diferem apenas em relação a representação de um URI, o usuário deve escolher a sobrecarga que utiliza um <xref:System.Uri> argumento.

## <a name="how-to-fix-violations"></a>Como corrigir violações

Para corrigir uma violação dessa regra, chame a sobrecarga que utiliza o <xref:System.Uri> argumento.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos

É seguro suprimir um aviso nessa regra, se o parâmetro de cadeia de caracteres não representa um URI.

## <a name="configurability"></a>Capacidade de configuração

Se você estiver executando essa regra de [analisadores FxCop](install-fxcop-analyzers.md) (e não por meio de análise de código estático), você pode configurar quais partes da sua base de código para executar essa regra, com base na sua acessibilidade. Por exemplo, para especificar que a regra deve ser executado apenas em relação a superfície de API não público, adicione o seguinte par de chave-valor para um arquivo. editorconfig em seu projeto:

```
dotnet_code_quality.ca2234.api_surface = private, internal
```

Você pode configurar essa opção para apenas essa regra, para todas as regras ou para todas as regras nessa categoria (uso). Para obter mais informações, consulte [analisadores FxCop configurar](configure-fxcop-analyzers.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um método `ErrorProne`, que viola a regra e um método `SaferWay`, que chama corretamente o <xref:System.Uri> de sobrecarga:

[!code-vb[FxCop.Usage.PassUri#1](../code-quality/codesnippet/VisualBasic/ca2234-pass-system-uri-objects-instead-of-strings_1.vb)]
[!code-cpp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CPP/ca2234-pass-system-uri-objects-instead-of-strings_1.cpp)]
[!code-csharp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CSharp/ca2234-pass-system-uri-objects-instead-of-strings_1.cs)]

## <a name="related-rules"></a>Regras relacionadas

- [CA1057: Cadeia de caracteres chamam sobrecargas System. URI](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)
- [CA1056: Propriedades URI não devem ser cadeias de caracteres](../code-quality/ca1056-uri-properties-should-not-be-strings.md)
- [CA1054: Parâmetros de URI não devem ser cadeias de caracteres](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)
- [CA1055: Valores não devem ser cadeias de caracteres de retorno de URI](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)