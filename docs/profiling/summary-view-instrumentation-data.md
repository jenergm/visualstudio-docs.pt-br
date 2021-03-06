---
title: Exibição Resumo – Dados de instrumentação | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 0a3b3a1f-e22b-4ac8-b46e-71694e9b2cf1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91d53eef12c1c2dc59d8c442a040f721af75e7b3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62557044"
---
# <a name="summary-view---instrumentation-data"></a>Exibição Resumo – dados de instrumentação
A exibição Resumo exibe informações sobre as funções mais caras de desempenho em uma execução da criação de perfil. Para obter mais informações, incluindo uma descrição das listas de Links de Notificação e Relatório, confira [Exibição Resumo](../profiling/summary-view.md).

## <a name="timeline-graph"></a>Gráfico de linha do tempo
 O gráfico de linha do tempo na exibição Resumo mostra a utilização do processador (CPU) pelo aplicativo com perfil ao longo do tempo em que ocorreu a criação de perfil. É possível usar o gráfico de linha do tempo para filtrar a exibição para um intervalo de tempo selecionado. Para obter mais informações, confira [Como: Filtrar as exibições de relatório da linha do tempo resumida](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).

## <a name="hot-path"></a>Afunilamento
 O **Afunilamento** exibe o caminho de execução que consumiu mais tempo. É possível clicar em uma função para mostrar a exibição Detalhes da Função referente a ela. Para exibir outras exibições da função, clique com o botão direito do mouse na função e, em seguida, clique em uma exibição na lista.

 O **Afunilamento** inclui os seguintes dados para cada função:

|Column|Descrição|
|------------|-----------------|
|**Nome**|O nome da função.|
|**% de Tempo Inclusivo Decorrido**|O percentual de todo o tempo nos dados de criação de perfil gasto pela função na execução do código em seu corpo e nas funções chamadas por ela.|
|**% de Tempo Exclusivo Decorrido**|O percentual de todo o tempo nos dados de criação de perfil que a função gastou na execução do código no corpo da função. O tempo gasto em funções que foram chamadas pela função não é incluído.|

## <a name="functions-with-most-individual-work"></a>Funções com mais trabalho individual
 Uma lista das funções que consumiram mais tempo executando o código no corpo da função e não em funções que foram chamadas por ela.

 **Funções com a maior parte do trabalho individual** inclui os seguintes dados para cada função:

|Column|Descrição|
|------------|-----------------|
|**Nome**|O nome da função.|
|**% de tempo exclusivo**|O percentual de todo o tempo nos dados de criação de perfil que a função gastou na execução do código no corpo da função. O tempo gasto em funções que foram chamadas pela função não é incluído.|

## <a name="see-also"></a>Consulte também
- [Exibição Resumo – dados de amostragem](../profiling/summary-view-sampling-data.md)
- [Exibição Resumo – dados de memória do .NET](../profiling/summary-view-dotnet-memory-data.md)