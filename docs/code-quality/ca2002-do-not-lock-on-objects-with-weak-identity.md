---
title: 'CA2002: Não bloquear objetos com identidade fraca'
ms.date: 01/31/2018
ms.topic: reference
f1_keywords:
- DoNotLockOnObjectsWithWeakIdentity
- CA2002
helpviewer_keywords:
- CA2002
- DoNotLockOnObjectsWithWeakIdentity
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 054f809483cf2a9c4647370e2f69187795c5c203
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55916577"
---
# <a name="ca2002-do-not-lock-on-objects-with-weak-identity"></a>CA2002: Não bloquear objetos com identidade fraca

|||
|-|-|
|NomeDoTipo|DoNotLockOnObjectsWithWeakIdentity|
|CheckId|CA2002|
|Categoria|Microsoft.Reliability|
|Alteração Significativa|Não são significativas|

## <a name="cause"></a>Causa

Um thread tenta adquirir um bloqueio em um objeto que tem uma identidade fraca.

## <a name="rule-description"></a>Descrição da regra

Diz-se que um objeto tem uma identidade fraca quando puder ser acessado diretamente em todos os limites de domínio do aplicativo. Um thread que tente adquirir um bloqueio em um objeto com uma identidade fraca pode ser bloqueado por um segundo thread em um domínio de aplicativo diferente com um bloqueio no mesmo objeto.

Os seguintes tipos tem uma identidade fraca e são sinalizados pela regra:

- <xref:System.String>

- Matrizes de tipos de valor, incluindo [tipos integrais](/dotnet/csharp/language-reference/keywords/integral-types-table), [tipos de ponto flutuante](/dotnet/csharp/language-reference/keywords/floating-point-types-table), e <xref:System.Boolean>.

- <xref:System.MarshalByRefObject>

- <xref:System.ExecutionEngineException>

- <xref:System.OutOfMemoryException>

- <xref:System.StackOverflowException>

- <xref:System.Reflection.MemberInfo>

- <xref:System.Reflection.ParameterInfo>

- <xref:System.Threading.Thread>

## <a name="how-to-fix-violations"></a>Como corrigir violações

Para corrigir uma violação dessa regra, use um objeto de um tipo que não está na lista na seção de descrição.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos

Não suprima um aviso nessa regra.

## <a name="related-rules"></a>Regras relacionadas

[CA2213: os campos descartáveis devem ser descartados](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

## <a name="example"></a>Exemplo

O exemplo a seguir mostra alguns bloqueios de objeto que violam a regra.

[!code-vb[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/VisualBasic/ca2002-do-not-lock-on-objects-with-weak-identity_1.vb)]
[!code-csharp[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/CSharp/ca2002-do-not-lock-on-objects-with-weak-identity_1.cs)]

## <a name="see-also"></a>Consulte também

- <xref:System.Threading.Monitor>
- <xref:System.AppDomain>
- [bloqueio de instrução (C#)](/dotnet/csharp/language-reference/keywords/lock-statement)
- [Instrução SyncLock (Visual Basic)](/dotnet/visual-basic/language-reference/statements/synclock-statement)