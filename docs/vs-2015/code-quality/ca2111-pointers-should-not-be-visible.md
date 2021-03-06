---
title: 'CA2111: Ponteiros não devem ser visíveis | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PointersShouldNotBeVisible
- CA2111
helpviewer_keywords:
- CA2111
- PointersShouldNotBeVisible
ms.assetid: b3a8d466-895b-43bc-a2df-5d7058fe915f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8497433088e4c49868a76dd3281d02a5e79babe5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58928684"
---
# <a name="ca2111-pointers-should-not-be-visible"></a>CA2111: Ponteiros não devem ser visíveis
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|PointersShouldNotBeVisible|
|CheckId|CA2111|
|Categoria|Microsoft.Security|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um público ou protegido <xref:System.IntPtr?displayProperty=fullName> ou <xref:System.UIntPtr?displayProperty=fullName> campo não é somente leitura.

## <a name="rule-description"></a>Descrição da Regra
 <xref:System.IntPtr> e <xref:System.UIntPtr> são tipos de ponteiro que são usados para acessar a memória não gerenciada. Se um ponteiro não for privado, interno ou somente leitura, o código mal-intencionado pode alterar o valor do ponteiro, potencialmente permitindo o acesso a locais arbitrários na memória ou causando falhas no aplicativo ou sistema.

 Se você pretender para proteger o acesso para o tipo que contém o campo de ponteiro, consulte [CA2112: Tipos seguros não devem expor campos](../code-quality/ca2112-secured-types-should-not-expose-fields.md).

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Proteger o ponteiro, tornando-o somente leitura, interno ou privado.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Suprima um aviso nessa regra, se você não confie no valor do ponteiro.

## <a name="example"></a>Exemplo
 O código a seguir mostra os ponteiros que violam e atendem à regra. Observe que os ponteiros não privados também violam a regra [CA1051: Não declarar campos de instância visíveis](../code-quality/ca1051-do-not-declare-visible-instance-fields.md).

 [!code-csharp[FxCop.Security.PointersArePrivate#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.PointersArePrivate/cs/FxCop.Security.PointersArePrivate.cs#1)]

## <a name="related-rules"></a>Regras relacionadas
 [CA2112: Tipos seguros não devem expor campos](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA1051: Não declarar campos de instância visíveis](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>Consulte também
 <xref:System.IntPtr?displayProperty=fullName> <xref:System.UIntPtr?displayProperty=fullName>
