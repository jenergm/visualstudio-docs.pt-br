---
title: Propriedades dinâmicas LINQ to XML
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0455f47c-4a68-4f2e-a3f8-dd1d85b99012
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 181e9e4fb86a0348c0b5adb1d26a0a4e4e1721bb
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55970706"
---
# <a name="linq-to-xml-dynamic-properties"></a>Propriedades dinâmicas do LINQ to XML

Esta seção fornece informações de referência sobre as propriedades dinâmicas em LINQ to XML. Especificamente, essas propriedades são expostos por classes de <xref:System.Xml.Linq.XAttribute> e de <xref:System.Xml.Linq.XElement> , que estão no espaço de <xref:System.Xml.Linq> .

Conforme explicado no tópico [Visão geral da associação de dados do WPF com o LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md), cada uma das propriedades dinâmicas é equivalente a um método ou uma propriedade pública padrão na mesma classe. Esses membros padrão devem ser usados para a maioria das finalidades; as propriedades dinâmicas são fornecidas especificamente para cenários de associação de dados LINQ to XML. Para obter mais informações sobre membros padrão dessas classes, consulte os tópicos de referência de <xref:System.Xml.Linq.XAttribute> e de <xref:System.Xml.Linq.XElement> .

Em relação a seus valores resolvidos, as propriedades dinâmicas nesta seção se enquadram em duas categorias:

- O simples, como as propriedades de `Value` classes de <xref:System.Xml.Linq.XAttribute> e de <xref:System.Xml.Linq.XElement> , que são consideradas como um único valor.

- Valores indexados, como as propriedades [Elementos](../designers/elements-xelement-dynamic-property.md) e [Descendentes](../designers/descendants-xelement-dynamic-property.md) de <xref:System.Xml.Linq.XElement>, que são resolvidas em um tipo de indexador. Para que os tipos do indexador são resolvidos com o valor desejado ou à coleção, um parâmetro expandido do nome deve ser-lhes passado.

Todas as propriedades dinâmicas que retornam um valor indexado do tipo <xref:System.Collections.Generic.IEnumerable%601> usam a execução adiada. Para obter mais informações sobre a execução adiada, confira [Introdução a consultas LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries).

## <a name="reference"></a>Referência

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a>Consulte também

- [Vinculação de dados do WPF com o LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md)
- [Associação de dados do WPF com LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md)
- [Introdução a consultas LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)
