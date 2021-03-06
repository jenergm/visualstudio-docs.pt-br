---
title: 'CA1034: Tipos aninhados não devem ser visíveis'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fb01065fed41a30f26e15d7295fabc03fb3f1f4f
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55942551"
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034: Tipos aninhados não devem ser visíveis

|||
|-|-|
|NomeDoTipo|NestedTypesShouldNotBeVisible|
|CheckId|CA1034|
|Categoria|Microsoft.Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa

Um tipo visível externamente contém uma declaração de tipo visível externamente. Enumerações aninhadas e tipos protegidos são isentos dessa regra.

## <a name="rule-description"></a>Descrição da regra
 Um tipo aninhado é um tipo declarado no escopo de outro tipo. Tipos aninhados são úteis para encapsular os detalhes de implementação privada do tipo recipiente. Usados para essa finalidade, os tipos aninhados não devem ser visíveis externamente.

 Não use tipos aninhados visíveis externamente para agrupamento lógico ou para evitar colisões de nome; em vez disso, usam namespaces.

 Tipos aninhados incluem a noção de acessibilidade de membro, o que alguns programadores não entendem claramente.

 Tipos protegidos podem ser usados em subclasses e tipos aninhados em cenários de personalização avançadas.

## <a name="how-to-fix-violations"></a>Como corrigir violações
 Se você não for do tipo aninhado para ser visível externamente, altere a acessibilidade do tipo. Caso contrário, remova o tipo aninhado de seu pai. Se a finalidade de aninhamento é categorizar o tipo aninhado, use um namespace para criar a hierarquia em vez disso.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos
 Não suprima um aviso nessa regra.

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra um tipo que viola a regra.

 [!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
 [!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]