---
title: 'CA1716: Identificadores não devem corresponder a palavras-chave | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 35a97e62e17895cb700a1420c7851878f329112a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58924578"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Identificadores não devem corresponder a palavras-chave
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|Categoria|Microsoft.Naming|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um nome de um namespace, um tipo ou membro viritual ou interface corresponde a uma palavra-chave reservada em uma linguagem de programação.

## <a name="rule-description"></a>Descrição da Regra
 Identificadores de namespaces, tipos e virtuais e os membros de interface não devem corresponder a palavras-chave que são definidas por linguagens que visam o common language runtime. Dependendo da linguagem que é usada e a palavra-chave, ambiguidades e erros do compilador podem dificultar a biblioteca usar.

 Esta regra verifica em palavras-chave nos seguintes idiomas:

- Visual Basic

- C#

- C++/CLI

  Comparação de maiusculas e minúsculas é usada para [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] comparação diferencia maiusculas de minúsculas e palavras-chave é usada para os outros idiomas.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Selecione um nome que não aparece na lista de palavras-chave.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Você pode suprimir um aviso nessa regra, se você estiver convencido de que o identificador não confundir os usuários da API, e que a biblioteca é utilizável em todos os idiomas disponíveis no [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].
