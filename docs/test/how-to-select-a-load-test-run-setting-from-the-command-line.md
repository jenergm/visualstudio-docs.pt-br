---
title: Definir as configurações de execução de teste de carga na linha de comando
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, command line
- load tests, run settings, selecting
ms.assetid: 175d1d58-f09a-4449-b132-a29a394a7c8e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e022eec099682581f244ad426500a512c63035d4
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936155"
---
# <a name="how-to-select-a-load-test-run-setting-to-use-from-the-command-line"></a>Como: Selecionar uma configuração de execução de teste de carga a ser usada por meio da linha de comando

Um teste de carga pode incluir *configurações de execução*, que são propriedades que influenciam a forma como um teste de carga é executado. As configurações de execução são organizadas por categorias na janela **Propriedades**. Quando é executado, um teste de carga usa a configuração de execução definida como ativa no momento.

Se contiver apenas uma configuração de execução, o teste de carga será sempre o nó ativo. Se o teste de carga contiver vários nós de configurações de execução, você poderá selecionar um para usar ao executar um teste de carga na linha de comando. Confira [Como: Adicionar outras configurações de execução a um teste de carga](../test/how-to-add-additional-run-settings-to-a-load-test.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-change-the-run-setting-from-the-command-line"></a>Para alterar a configuração de execução na linha de comando

1.  Se quiser usar configurações de execução diferentes na linha de comando para se beneficiar da estratégia do parâmetro de contexto, use o seguinte comando:

    `Set Test.UseRunSetting= CorporateStagingWebServer`

2.  Execute o teste de carga usando mstest:

    `mstest /testcontainer:loadtest1.loadtest`

## <a name="see-also"></a>Consulte também

- [Definir configurações de execução de teste de carga](../test/configure-load-test-run-settings.md)
- [Especificar os conjuntos de contadores e as regras de limite para computadores em um teste de carga](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Como: Adicionar outras configurações de execução a um teste de carga](../test/how-to-add-additional-run-settings-to-a-load-test.md)
- [Como: Selecionar a configuração de execução ativa para um teste de carga](../test/how-to-select-the-active-run-setting-for-a-load-test.md)
