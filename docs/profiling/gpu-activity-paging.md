---
title: Atividade de GPU (paginação) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuactivity
- vs.cv.threads.timeline.gpupaging
ms.assetid: 95284ac5-3492-4f7b-a79f-7d2840a07679
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8bd28c7b41a01992ad52fa343b098b0a02460806
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608325"
---
# <a name="gpu-activity-paging"></a>Atividade de GPU (paginação)
Os segmentos de **Atividade de GPU (paginação)** na guia **Threads** representam o tempo durante o qual a GPU estava processando solicitações de paginação.  O tamanho de um segmento representa o tempo durante o qual a GPU estava processando um pacote de paginação de DMA (acesso direto à memória). Normalmente, pacotes de paginação são associados à transferência de memória entre a CPU e a GPU.

 Quando você seleciona um segmento de paginação da GPU, o relatório na guia **Atual** exibe informações sobre o pacote de DMA que foi processado. Isso inclui a quantidade de tempo que ele esperou na fila de hardware associada ao mecanismo do DirectX, o processo que enviou o pacote de DMA e o tempo necessário para processar o pacote.

## <a name="see-also"></a>Consulte também
- [Exibição da utilização](../profiling/utilization-view.md)