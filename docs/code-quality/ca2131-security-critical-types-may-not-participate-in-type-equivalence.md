---
title: 'CA2131: Tipos críticos de segurança podem não participar da equivalência de tipo'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2131
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9b5cc0920e56b9fc27ef120d3328f2ba528b54dd
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55947686"
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131: Tipos críticos de segurança podem não participar da equivalência de tipo

|||
|-|-|
|NomeDoTipo|CriticalTypesMustNotParticipateInTypeEquivalence|
|CheckId|CA2131|
|Categoria|Microsoft.Security|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um tipo participa da equivalência de tipo e um o tipo em si, ou um membro ou campo do tipo, é marcado com o <xref:System.Security.SecurityCriticalAttribute> atributo.

## <a name="rule-description"></a>Descrição da regra
 Esta regra é acionada em qualquer tipo crítico ou em tipos que contenham métodos críticos ou campos que estejam participando da equivalência do tipo. Quando o CLR detecta desse tipo, não consiga carregá-lo com um <xref:System.TypeLoadException> em tempo de execução. Normalmente, essa regra só é acionada quando usuários implementam equivalência de tipo manualmente, em vez de depender de tlbimp e dos compiladores para fazer a equivalência do tipo.

## <a name="how-to-fix-violations"></a>Como corrigir violações
 Para corrigir uma violação dessa regra, remova o atributo SecurityCritical.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos
 Não suprima um aviso nessa regra.

## <a name="example"></a>Exemplo
 Os exemplos a seguir demonstram uma interface, um método e um campo que fará com que a regra seja disparada.

 [!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../code-quality/codesnippet/CSharp/ca2131-security-critical-types-may-not-participate-in-type-equivalence_1.cs)]

## <a name="see-also"></a>Consulte também
 [Código transparente de segurança, nível 2](/dotnet/framework/misc/security-transparent-code-level-2)