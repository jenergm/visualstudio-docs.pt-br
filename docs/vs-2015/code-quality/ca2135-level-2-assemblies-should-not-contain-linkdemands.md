---
title: 'CA2135: Assemblies de nível 2 não devem conter LinkDemands | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: cd4b1cb9d69e916a3d5cd547b3ff3714a20a665f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58927476"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: Os assemblies de nível 2 não devem conter LinkDemands
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|Categoria|Microsoft.Security|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Uma classe ou membro de classe está usando um <xref:System.Security.Permissions.SecurityAction> em um aplicativo que está usando segurança de nível 2.

## <a name="rule-description"></a>Descrição da Regra
 LinkDemands são preteridos no conjunto de regras de segurança nível 2. Em vez de usar LinkDemands para impor a segurança em tempo de compilação just-in-time (JIT), marque os métodos, tipos e campos com o <xref:System.Security.SecurityCriticalAttribute> atributo.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, remova os <xref:System.Security.Permissions.SecurityAction> e marque o tipo ou membro com o <xref:System.Security.SecurityCriticalAttribute> atributo.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Não suprima um aviso nessa regra.

## <a name="example"></a>Exemplo
 No exemplo a seguir, o <xref:System.Security.Permissions.SecurityAction> devem ser removidos e o método marcado com o <xref:System.Security.SecurityCriticalAttribute> atributo.

 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2135.securityrulesetlevel2methodsshouldnotbeprotectedwithlinkdemands/cs/ca2135.cs#1)]
