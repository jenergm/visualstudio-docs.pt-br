---
title: 'CA2133: Representantes devem ser associados a métodos com transparência consistente'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2133
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0745506bfe55305c9c3a55f57823e5d80c453006
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55935856"
---
# <a name="ca2133-delegates-must-bind-to-methods-with-consistent-transparency"></a>CA2133: Representantes devem ser associados a métodos com transparência consistente

|||
|-|-|
|NomeDoTipo|DelegatesMustBindWithConsistentTransparency|
|CheckId|CA2133|
|Categoria|Microsoft.Security|
|Alteração Significativa|Quebra|

> [!NOTE]
> Esse aviso só será aplicado ao código que está executando o CoreCLR (a versão do CLR que é específico para aplicativos web do Silverlight).

## <a name="cause"></a>Causa

Esse aviso é acionado em um método que associa um representante que é marcado com o <xref:System.Security.SecurityCriticalAttribute> para um método transparente ou marcado com o <xref:System.Security.SecuritySafeCriticalAttribute>. O aviso também é acionado em um método que associa um representante transparente ou de segurança crítica a um método crítico.

## <a name="rule-description"></a>Descrição da regra

Tipos de delegado e os métodos que elas se associam a devem ter uma transparência consistente. Delegados transparentes e crítico de segurança só podem ser associado a outros métodos transparentes ou de segurança crítica. Da mesma forma, delegados críticos só podem ser associado a métodos críticos. Essas regras de associação garantem que o único código que pode invocar um método por meio de um delegado pode ter também chamado o mesmo método diretamente. Por exemplo, regras de associação de impedir que o código transparente chamando código crítico diretamente por meio de um representante transparente.

## <a name="how-to-fix-violations"></a>Como corrigir violações

Para corrigir uma violação esse aviso, altere a transparência do delegado ou do método que associa para que a transparência dos dois são equivalentes.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos

Não suprima um aviso nessa regra.

### <a name="code"></a>Código

[!code-csharp[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2133-delegates-must-bind-to-methods-with-consistent-transparency_1.cs)]