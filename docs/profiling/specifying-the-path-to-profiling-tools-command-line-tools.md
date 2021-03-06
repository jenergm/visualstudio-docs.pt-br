---
title: Especificando o caminho para ferramentas de linha de comando de ferramentas de criação de perfil | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 03b11b478ef441dc7a09902a7185bfdf45e20dc3
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "57868944"
---
# <a name="specify-the-path-to-profiling-tools-command-line-tools"></a>Especificar o caminho para as ferramentas de linha de comando das Ferramentas de Criação de Perfil

O caminho das ferramentas de linha de comando das Ferramentas de Criação de Perfil do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] não é adicionado à variável de ambiente PATH. Em computadores de 32 bits, as ferramentas permanecem em um único diretório. Existem versões de 32 e 64 bits das ferramentas de criação de perfil em computadores de 64 bits.

## <a name="32-bit-computers"></a>Computadores 32 bits
::: moniker range=">=vs-2019"
 Para o código nativo, as APIs do criador de perfil do Visual Studio estão em *VSPerf.dll*. O arquivo de cabeçalho, *VSPerf.h*, e a biblioteca de importação, *VSPerf.lib*, estão localizados no diretório *Microsoft Visual Studio\2019\Team Tools\Performance Tools\PerfSDK*.
::: moniker-end
::: moniker range="vs-2017"
 Para o código nativo, as APIs do criador de perfil do Visual Studio estão em *VSPerf.dll*. O arquivo de cabeçalho, *VSPerf.h*, e a biblioteca de importação, *VSPerf.lib*, estão localizados no diretório *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK*.
::: moniker-end

 Para o código gerenciado, as APIs do criador de perfil estão na *Microsoft.VisualStudio.Profiler.dll*. Essa DLL é encontrada no diretório *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*.

## <a name="64-bit-computers"></a>Computadores de 64 bits

Em computadores de 64 bits, especifique o caminho de acordo com a plataforma de destino do aplicativo cujo perfil foi criado.

::: moniker range=">=vs-2019"
-   No caso de aplicativos de 32 bits, o diretório padrão das ferramentas de criação de perfil é:

     (nativo) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\PerfSDK* (gerenciado) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

-   No caso de aplicativos de 64 bits, o diretório padrão das ferramentas de criação de perfil é:

     (nativo) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\x64\PerfSDK* (gerenciado) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end

::: moniker range="vs-2017"
-   No caso de aplicativos de 32 bits, o diretório padrão das ferramentas de criação de perfil é:

     (nativo) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK* (gerenciado) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

-   No caso de aplicativos de 64 bits, o diretório padrão das ferramentas de criação de perfil é:

     (nativo) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\x64\PerfSDK* (gerenciado) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end