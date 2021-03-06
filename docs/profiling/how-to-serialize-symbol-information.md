---
title: 'Como: Serializar informações de símbolo | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Performance.General
helpviewer_keywords:
- profiling tools, serializing symbol information
- performance tools, serializing symbol information
ms.assetid: 9e0da706-6325-4073-83d1-aeab3b7c137a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3b88268ba0ed8b1c324eda08ec3db969e088f279
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62539240"
---
# <a name="how-to-serialize-symbol-information"></a>Como: Como serializar informações de símbolo
Você pode serializar os símbolos que são necessários para analisar seu aplicativo. A serialização de símbolos adiciona símbolos ao arquivo .*vsp*. Ao adicionar informações de símbolo ao arquivo .*vsp*, outras pessoas podem analisar um relatório de desempenho sem ter acesso aos símbolos originais. Se os símbolos não forem serializados, você precisará ter os arquivos originais instrumentados .*exe* e .*pdb* para analisar o arquivo .*vsp*.

### <a name="to-automatically-serialize-symbol-information"></a>Para serializar informações de símbolo automaticamente

1. No menu **Ferramentas**, clique em **Opções**.

     A caixa de diálogo **Opções** é exibida.

2. Clique em **Ferramentas de Desempenho**.

3. Em **Configuração Geral**, selecione **Serializar informações de símbolo automaticamente**.

## <a name="see-also"></a>Consulte também
- [Configurar sessões de desempenho](../profiling/configuring-performance-sessions.md)
- [Como: Referenciar informações de símbolo do Windows](../profiling/how-to-reference-windows-symbol-information.md)
- [Como: Salvar arquivos de relatório analisados](/previous-versions/visualstudio/visual-studio-2010/bb763106\(v\=vs.100\))