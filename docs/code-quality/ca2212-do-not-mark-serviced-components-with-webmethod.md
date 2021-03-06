---
title: 'CA2212: Não marcar componentes atendidos com WebMethod'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
helpviewer_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a47b7e703d811ff5dce421db103af89bb3a76512
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55917032"
---
# <a name="ca2212-do-not-mark-serviced-components-with-webmethod"></a>CA2212: Não marcar componentes atendidos com WebMethod

|||
|-|-|
|NomeDoTipo|DoNotMarkServicedComponentsWithWebMethod|
|CheckId|CA2212|
|Categoria|Microsoft.Usage|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa

Um método em um tipo que herda de <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName> está marcado com <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>.

## <a name="rule-description"></a>Descrição da regra

<xref:System.Web.Services.WebMethodAttribute> se aplica aos métodos dentro de um serviço web XML criados usando o ASP.NET; ele torna o método chamável de clientes web remoto. O método e a classe devem ser pública e em execução em um aplicativo web ASP.NET. <xref:System.EnterpriseServices.ServicedComponent> tipos são hospedados por aplicativos COM+ e podem usar serviços COM+. <xref:System.Web.Services.WebMethodAttribute> não é aplicado a <xref:System.EnterpriseServices.ServicedComponent> porque eles não devem ser os mesmos cenários. Especificamente, adicionando o atributo para o <xref:System.EnterpriseServices.ServicedComponent> método não faz o método que pode ser chamado por clientes da web remoto. Porque <xref:System.Web.Services.WebMethodAttribute> e um <xref:System.EnterpriseServices.ServicedComponent> método têm comportamentos conflitantes e requisitos para o contexto e fluxo de transações, o comportamento do método estará incorretos em alguns cenários.

## <a name="how-to-fix-violations"></a>Como corrigir violações

Para corrigir uma violação dessa regra, remova o atributo do <xref:System.EnterpriseServices.ServicedComponent> método.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos

Não suprima um aviso nessa regra. Não há nenhum cenário em que a combinação desses elementos está correto.

## <a name="see-also"></a>Consulte também

- <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>
- <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>