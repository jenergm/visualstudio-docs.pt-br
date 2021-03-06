---
title: 'Como: Criar um item de trabalho para um defeito de código gerenciado'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managed code, creating work items for code defects
- code analysis, creating work items
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: e2e55ddf51e0c81f57c504e398c23c8e1d3f721a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55934790"
---
# <a name="how-to-create-a-work-item-for-a-managed-code-defect"></a>Como: Criar um item de trabalho para um defeito de código gerenciado

Você pode usar o recurso de rastreamento de item de trabalho para o item de trabalho do log de dentro do Visual Studio. Para usar esse recurso, o projeto deve ser parte de um projeto de DevOps do Azure no [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)].

## <a name="to-create-a-work-item-for-managed-code-defect"></a>Para criar um item de trabalho para defeitos de código gerenciado

1. No **análise de código** janela, selecione o aviso.

2. Escolher **ações**, em seguida, escolha **Criar Item de trabalho** e escolha o tipo de item de trabalho a ser criado.

     Um novo item de trabalho é criado para você especificar as informações de defeito.

## <a name="to-create-a-work-item-for-multiple-managed-code-defects"></a>Para criar um item de trabalho para vários defeitos de código gerenciado

1. No **Error List**, selecione vários avisos e, em seguida, clique com botão direito os avisos.

2. Aponte para **Criar Item de trabalho** e clique no tipo de item de trabalho para criar.

     Um único item de trabalho é criado para todos os avisos selecionados para que você especifique as informações de bug.