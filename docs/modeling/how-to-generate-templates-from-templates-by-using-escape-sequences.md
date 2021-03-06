---
title: 'Como: Gerar modelos com base em modelos usando sequências de escape'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, generating templates from templates
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 35047c6c0887d02f3adcba763de05b8d4a1cd00b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60042471"
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>Como: Gerar modelos com base em modelos usando sequências de escape
Você pode criar um modelo de texto que cria outro modelo de texto como sua saída de texto gerado. Para fazer isso, você deve usar sequências de escape para delinear as marcas do modelo de texto. Se você não usar sequências de escape, seu modelo de texto gerada terá um significado predefinido. Para obter mais informações sobre como usar sequências de escape em modelos de texto, consulte [usando sequências de Escape em modelos de texto](../modeling/using-escape-sequences-in-text-templates.md).

### <a name="to-generate-a-text-template-from-within-a-text-template"></a>Para gerar um modelo de texto de dentro de um modelo de texto

- Use a barra invertida (\\) como um caractere de escape para produzir as marcas de marcação necessário dentro do modelo de texto para diretivas, instruções, expressões e classes de recursos em um arquivo de modelo de texto separado.

    ```
    \<#@ directive \#>
    \<# statement \#>
    \<#= expression \#>
    \<#+ classfeature \#>
    ```

## <a name="example"></a>Exemplo
 O exemplo a seguir usa caracteres de escape para produzir um modelo de texto de um modelo de texto. O `output` diretiva define o tipo de arquivo de destino para o tipo de arquivo de modelo de texto (. TT).

```csharp
\<#@ output extension=".tt" \#>
\<#@ assembly name="System.Xml.dll" \#>
\<#@ import namespace="System.Xml" \#>
\<#
XmlDocument xDoc = new XmlDocument();
//System.Diagnostics.Debugger.Break();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {\#>
           \<#= attr.Name \#>
       \<#}
     }
\#>
```

 A saída de texto gerado é um modelo de texto.

```
<#@ output extension=".tt" #>
<#@ assembly name="System.Xml.dll" #>
<#@ import namespace="System.Xml" #>
<#
XmlDocument xDoc = new XmlDocument();
//System.Diagnostics.Debugger.Break();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {#>
           <#= attr.Name #>
       <#}
     }
#>
```