---
title: Regras de desempenho de memória e paginação | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f37972b2-efe4-4a1c-a5d1-a246ccd76817
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1f779a050c334e8f61d6d3711ed2be2a7b087e72
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640032"
---
# <a name="memory-and-paging-performance-rules"></a>Regras de desempenho de memória e de paginação
As regras de desempenho na memória e categoria de paginação identificam a atividade de paginação em uma execução de criação de perfil que pode afetar a capacidade de resposta e o desempenho do aplicativo.

|||
|-|-|
|[DA0014: Taxas de paginação de memória ativa para o disco extremamente altas](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|Uma taxa extremamente alta de paginação de memória ativa de e para o disco ocorreu durante toda a execução de criação de perfil. Geralmente, taxas de paginação nesse nível afetam a capacidade de resposta e o desempenho do aplicativo. Considere a redução das alocações de memória revisando os algoritmos. Talvez você também precise considerar os requisitos de memória do aplicativo. Tente executar a criação de perfil novamente em um computador com mais memória. Essa regra é acionada quando a quantidade de atividade de paginação excede o limite superior de regra D0017.|
|[DA0017: Altas taxas de paginação de memória ativa para o disco](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|Uma taxa relativamente alta de paginação de memória ativa de e para o disco ocorreu durante toda a execução de criação de perfil. Geralmente, taxas de paginação nesse nível afetam a capacidade de resposta e o desempenho do aplicativo. Considere a redução das alocações de memória revisando os algoritmos. Talvez você também precise considerar os requisitos de memória do aplicativo. Tente executar a criação de perfil novamente em um computador com mais memória.|