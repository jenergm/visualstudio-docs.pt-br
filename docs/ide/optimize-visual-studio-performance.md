---
title: Melhorar o desempenho se o Visual Studio estiver lento
titleSuffix: ''
ms.date: 04/11/2018
ms.topic: conceptual
helpviewer_keywords:
- performance [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- vs.performancecenter
ms.workload:
- multiple
ms.openlocfilehash: bdc605b614fab5b11c2efc8466480ebf49a1fee7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62569843"
---
# <a name="optimize-visual-studio-performance"></a>Otimizar o desempenho do Visual Studio

Este artigo fornece algumas sugestões para tentar se você achar que o Visual Studio está sendo executado lentamente. Você também pode dar uma olhada em [Dicas e truques de desempenho do Visual Studio](../ide/visual-studio-performance-tips-and-tricks.md) para obter mais sugestões sobre como melhorar o desempenho.

## <a name="upgrade-visual-studio"></a>Atualizar o Visual Studio

Se estiver usando o Visual Studio 2015, baixe o [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) ou o [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) gratuitamente para conferir seu desempenho aprimorado. As soluções são carregadas duas a três vezes mais rapidamente no Visual Studio 2015, com melhorias de desempenho em outras áreas também. O Visual Studio 2017 e o Visual Studio 2019 são compatíveis lado a lado com o Visual Studio 2015, portanto você não perderá nada por experimentá-lo.

::: moniker range="vs-2017"

Se já estiver usando o Visual Studio 2017, verifique se está executando a versão 15.6 ou posterior. Dados mostram que as soluções são carregadas duas ou três vezes mais rapidamente na versão 15.6. Faça download dela [aqui](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download).

::: moniker-end

## <a name="extensions-and-tool-windows"></a>Extensões e janelas de ferramentas

Você pode ter extensões instaladas que estão diminuindo o Visual Studio. Para obter ajuda sobre como gerenciar extensões para melhorar o desempenho, consulte [Alterar configurações de extensão para melhorar o desempenho](../ide/optimize-visual-studio-startup-time.md#extensions).

Da mesma forma, você pode ter janelas de ferramentas que estão deixando o Visual Studio mais lento. Para obter ajuda sobre como gerenciar janelas de ferramentas, consulte [Alterar as configurações da janela de ferramentas](../ide/optimize-visual-studio-startup-time.md#tool-windows).

## <a name="hardware"></a>Hardware

Se você estiver pensando em atualizar seu hardware, uma SSD (unidade de estado sólido) tem mais efeito sobre o desempenho do que memória RAM adicional ou uma CPU mais rápida.

Se você adicionar uma SSD, para ter o desempenho ideal, instale o Windows nessa unidade em vez de uma HDD (unidade de disco rígido). O local da unidade de suas soluções do Visual Studio parece não importar tanto.

Além disso, não execute sua solução de uma unidade USB. Copie-a para a HDD ou SSD.

## <a name="help-us-improve"></a>Ajude-nos a melhorar

Seus comentários nos ajudam a melhorar. Use o recurso **Relatar um Problema** para "registrar" um rastreamento e nos enviar. Selecione o ícone de comentários ao lado de **QuickLaunch** ou selecione **Ajuda** > **Enviar Comentários** > **Relatar um Problema** na barra de menus. Para saber mais, consulte [Como relatar um problema com o Visual Studio](../ide/how-to-report-a-problem-with-visual-studio.md).

## <a name="see-also"></a>Consulte também

- [Dicas e truques de desempenho](../ide/visual-studio-performance-tips-and-tricks.md)
- [Blog do Visual Studio – Carregar soluções mais rapidamente com o Visual Studio 2017 versão 15.6](https://devblogs.microsoft.com/visualstudio/load-solutions-faster-with-visual-studio-2017-version-15-6/)