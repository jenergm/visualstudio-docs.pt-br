---
title: Criação de arquivos de dados de criação de perfil portáteis com a linha de comando | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 10f314f0b587c438c6691a6d7fe5d9d108d06479
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56654003"
---
# <a name="create-portable-profiling-data-files-from-the-command-line"></a>Criar arquivos de dados de criação de perfil móveis por meio da linha de comando
Para facilitar o compartilhamento de dados de criação de perfil, use a ferramenta de linha de comando [VSPerfReport](../profiling/vsperfreport.md) para inserir os símbolos de uma execução de criação de perfil no arquivo .*vsp*.

 Crie também um arquivo de dados de criação de perfil pré-analisado (.*vsps*) que é menor e mais rápido para ser carregado no IDE.

> [!NOTE]
>  Verifique se os arquivos de símbolo (.*pdb*) estão disponíveis para **VSPerfReport**. Para obter mais informações, confira [Como: Especificar locais de arquivo de símbolo da linha de comando](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).
>
>  Para obter informações sobre o caminho para **VSReport**, confira [Especificar o caminho para as ferramentas de linha de comando](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).
>
>  Os dados de criação de perfil em um arquivo .*vsps* não podem ser filtrados.

### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Para inserir os símbolos de uma execução de criação de perfil em um arquivo de dados de criação de perfil (.*vsp*)

- Em uma janela de prompt de comando, digite o seguinte comando:

   \<Caminho><strong>VSPerfReport \<</strong>arquivo VSP> **/PackSymbols**

   Por padrão, o arquivo .*vsps* é nomeado com o nome base do arquivo .*vsp*. Você pode especificar um nome alternativo usando a opção **Saída**.

### <a name="to-create-a-summary-profiling-data-file"></a>Para criar um arquivo de dados de criação de perfil de resumo

- Em uma janela de prompt de comando, digite o seguinte comando:

   \<Caminho><strong>VSPerfReport \<</strong>arquivo VSP > **/SummaryFile** [**/Output:**\<nome do arquivo>]

   Por padrão, o arquivo .*vsps* é nomeado com o nome base do arquivo .*vsp*. Você pode especificar um nome alternativo usando a opção **Saída**.