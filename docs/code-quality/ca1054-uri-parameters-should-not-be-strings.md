---
title: 'CA1054: Parâmetros de URI não devem ser cadeias de caracteres'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1054
- UriParametersShouldNotBeStrings
helpviewer_keywords:
- CA1054
- UriParametersShouldNotBeStrings
ms.assetid: 8e99d72b-a658-47a7-8dd5-9784ce2c30b8
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 03d850eeb668f6c2b47d663b55e5461cabf9cbbf
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57867455"
---
# <a name="ca1054-uri-parameters-should-not-be-strings"></a>CA1054: Parâmetros de URI não devem ser cadeias de caracteres

|||
|-|-|
|NomeDoTipo|UriParametersShouldNotBeStrings|
|CheckId|CA1054|
|Categoria|Microsoft.Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa

Um tipo declara um método com um parâmetro de cadeia de caracteres cujo nome contém "uri", "Uri", "urn", "Urn", "url" ou "Url" e o tipo não declarar uma sobrecarga correspondente que utiliza um <xref:System.Uri?displayProperty=fullName> parâmetro.

Por padrão, essa regra olha apenas tipos visíveis externamente, mas isso é [configurável](#configurability).

## <a name="rule-description"></a>Descrição da regra

Essa regra é o nome do parâmetro é dividida em tokens com base na convenção camel case e verifica se cada token é igual a "uri", "Uri", "urn", "Urn", "url" ou "Url". Se houver uma correspondência, a regra pressupõe que o parâmetro representa um uniform resource identifier (URI). Uma representação de cadeia de caracteres de um URI está propensa a erros de análise e de codificação, e pode resultar em vulnerabilidades de segurança. Se um método usa uma representação de cadeia de caracteres de um URI, uma sobrecarga correspondente deve ser fornecida utilizando uma instância da <xref:System.Uri> classe, que fornece esses serviços de maneira segura e protegida.

## <a name="how-to-fix-violations"></a>Como corrigir violações

Para corrigir uma violação dessa regra, altere o parâmetro para um <xref:System.Uri> digite; essa é uma alteração significativa. Como alternativa, fornecer uma sobrecarga do método que usa um <xref:System.Uri> parâmetro; essa é uma alteração sem quebra.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos

É seguro suprimir um aviso nessa regra, se o parâmetro não representar um URI.

## <a name="configurability"></a>Capacidade de configuração

Se você estiver executando essa regra de [analisadores FxCop](install-fxcop-analyzers.md) (e não por meio de análise de código estático), você pode configurar quais partes da sua base de código para executar essa regra, com base na sua acessibilidade. Por exemplo, para especificar que a regra deve ser executado apenas em relação a superfície de API não público, adicione o seguinte par de chave-valor para um arquivo. editorconfig em seu projeto:

```
dotnet_code_quality.ca1054.api_surface = private, internal
```

Você pode configurar essa opção para apenas essa regra, para todas as regras ou para todas as regras nessa categoria (Design). Para obter mais informações, consulte [analisadores FxCop configurar](configure-fxcop-analyzers.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um tipo `ErrorProne`, que viola essa regra e um tipo, `SaferWay`, que satisfaz a regra.

[!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1054-uri-parameters-should-not-be-strings_1.cs)]
[!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1054-uri-parameters-should-not-be-strings_1.vb)]
[!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1054-uri-parameters-should-not-be-strings_1.cpp)]

## <a name="related-rules"></a>Regras relacionadas

- [CA1056: Propriedades URI não devem ser cadeias de caracteres](../code-quality/ca1056-uri-properties-should-not-be-strings.md)
- [CA1055: Valores não devem ser cadeias de caracteres de retorno de URI](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)
- [CA2234: Passar objetos System. URI em vez de cadeias de caracteres](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)
- [CA1057: Cadeia de caracteres chamam sobrecargas System. URI](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)