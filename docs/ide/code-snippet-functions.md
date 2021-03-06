---
title: Funções de snippet de código
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- code snippets [Visual Studio], functions
- snippets [Visual Studio], functions
- IntelliSense code snippets, functions
ms.assetid: c0a2bf21-8fa5-4457-9281-f599beb53e7d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 60453b6842dd321b7c85c2837e12b1208adb18f9
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939503"
---
# <a name="code-snippet-functions"></a>Funções de snippet de código

Há três funções disponíveis para uso com os snippets de código de C#. As funções são especificadas no elemento [Function](../ide/code-snippets-schema-reference.md#function-element) do snippet de código. Para obter informações sobre como criar snippets de código, consulte [Snippets de código](../ide/code-snippets.md).

## <a name="functions"></a>Funções

A tabela a seguir descreve as funções disponíveis para uso com o elemento `Function` em snippets de código.

|Função|Descrição|Idioma|
|--------------|-----------------|--------------|
|`GenerateSwitchCases(EnumerationLiteral)`|Gera uma instrução de opção e um conjunto de instruções de maiúsculas e minúsculas para os membros da enumeração especificada pelo parâmetro `EnumerationLiteral`. O parâmetro `EnumerationLiteral` deve ser uma referência a uma literal de enumeração ou a um tipo de enumeração.|C#|
|`ClassName()`|Retorna o nome da classe que contém o snippet inserido.|C#|
|`SimpleTypeName(TypeName)`|Reduz o parâmetro *TypeName* para sua forma mais simples no contexto em que o snippet foi invocado.|C#|

## <a name="generateswitchcases-example"></a>Exemplo de GenerateSwitchCases

O exemplo a seguir mostra como usar a função `GenerateSwitchCases`. Quando este snippet for inserido e uma enumeração for inserida no literal `$switch_on$`, o literal `$cases$` gerará uma instrução `case` para cada valor na enumeração.

```xml
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>switch</Title>
            <Shortcut>switch</Shortcut>
            <Description>Code snippet for switch statement</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal>
                    <ID>expression</ID>
                    <ToolTip>Expression to switch on</ToolTip>
                    <Default>switch_on</Default>
                </Literal>
                <Literal Editable="false">
                    <ID>cases</ID>
                    <Function>GenerateSwitchCases($expression$)</Function>
                    <Default>default:</Default>
                </Literal>
            </Declarations>
            <Code Language="csharp">
                <![CDATA[
                    switch ($expression$)
                    {
                        $cases$
                    }
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="classname-example"></a>Exemplo de ClassName

O exemplo a seguir mostra como usar a função `ClassName`. Quando este snippet for inserido, o literal `$classname$` será substituído pelo nome da classe delimitadora nesse local no arquivo de código.

```xml
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>Common constructor pattern</Title>
            <Shortcut>ctor</Shortcut>
            <Description>Code Snippet for a constructor</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal>
                    <ID>type</ID>
                    <Default>int</Default>
                </Literal>
                <Literal>
                    <ID>name</ID>
                    <Default>field</Default>
                </Literal>
                <Literal default="true" Editable="false">
                    <ID>classname</ID>
                    <ToolTip>Class name</ToolTip>
                    <Function>ClassName()</Function>
                    <Default>ClassNamePlaceholder</Default>
                </Literal>
            </Declarations>
            <Code Language="csharp" Format="CData">
                <![CDATA[
                    public $classname$ ($type$ $name$)
                    {
                        this._$name$ = $name$;
                    }
                    private $type$ _$name$;
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="simpletypename-example"></a>Exemplo de SimpleTypeName

Este exemplo mostra como usar a função `SimpleTypeName`. Quando este snippet for inserido em um arquivo de código, o literal `$SystemConsole$` será substituído pela forma mais simples do tipo <xref:System.Console> no contexto em que o snippet foi invocado.

```xml
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>Console_WriteLine</Title>
            <Shortcut>cw</Shortcut>
            <Description>Code snippet for Console.WriteLine</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal Editable="false">
                    <ID>SystemConsole</ID>
                    <Function>SimpleTypeName(global::System.Console)</Function>
                </Literal>
            </Declarations>
            <Code Language="csharp">
                <![CDATA[
                    $SystemConsole$.WriteLine();
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="see-also"></a>Consulte também

- [Elemento Function](../ide/code-snippets-schema-reference.md#function-element)
- [Referência de esquema dos snippets de código](../ide/code-snippets-schema-reference.md)
