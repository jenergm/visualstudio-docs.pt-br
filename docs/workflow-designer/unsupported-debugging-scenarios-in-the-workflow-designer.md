---
title: Cenários sem suporte de depuração no Designer de Fluxo de Trabalho
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 83c9b1158319b580bc860982b6c51c9c28edf5af
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60099644"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Cenários sem suporte de depuração no Designer de Fluxo de Trabalho

O Designer de fluxo de trabalho do .NET Framework 4 introduziu muitos recursos novos, mas ainda existem alguns cenários de depuração que ele não oferece suporte.

O Designer de fluxo de trabalho não há suporte para cenários de depuração veja a seguir:

- A execução não pode ser continuada após o código foi editado.

- A execução não pode ser continuada de um ponto arbitrário no fluxo de trabalho (definido em seguida).

- A execução não pode ser continuada até que o cursor seja alcançado (execução ao cursor).

- O designer de fluxo de trabalho não pode ser usado para criar fluxos de trabalho criados em código sem o uso de designer.

- Fluxos de trabalho criados em versões anteriores do Windows Workflow Foundation (WF) não podem ser depurados no designer do .NET Framework 4.

- Os pontos de interrupção não podem ser definidos nos links entre atividades ou nós de <xref:System.Activities.Statements.Flowchart> .

- A área de transferência não estão disponíveis durante a depuração.

- Os pontos de interrupção não são mantidas quando as atividades são copiadas ou coladas.

- Os pontos de interrupção de fluxo de trabalho não podem ser definidos na janela de pilha de chamadas.

- Durante a criação de pontos de interrupção no designer, o **linha** e **caractere** configurações no **novo ponto de interrupção** caixa de diálogo não são usados.

- A janela ou o menu de atalho do ponto de interrupção não suportam as seguintes colunas ou opções para depuração de fluxo de trabalho:

    - Condição

    - Contagem de acertos

    - Quando atingido

    - Função

    - Dados

    - Processo

    - Vá para a desmontagem