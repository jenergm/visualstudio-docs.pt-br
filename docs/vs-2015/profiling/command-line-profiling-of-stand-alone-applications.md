---
title: Criação de perfil de linha de comando de aplicativos autônomos | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3f4b2b78f7187b7a49b78312a1105a2af884fda3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54752182"
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>Criação de perfil de linha de comando dos aplicativos autônomos
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Esta seção descreve os procedimentos e as opções para coletar dados de desempenho para aplicativos autônomos (clientes) usando as Ferramentas de Criação de Perfil do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] na linha de comando.  
  
## <a name="common-tasks"></a>Tarefas comuns  
  
|Tarefa|Conteúdo relacionado|  
|----------|---------------------|  
|**Coletar estatísticas do aplicativo:** Use o método de amostragem para coletar estatísticas de desempenho. Os dados de amostragem são úteis para analisar problemas de utilização de CPU e para entender as características de desempenho geral de um aplicativo.|-   [Coletando estatísticas do aplicativo usando amostragem](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Coletar dados detalhados:** Usar o método de instrumentação para coletar informações de tempo detalhadas. Os dados de instrumentação são úteis para analisar problemas de E/S e para análise refinada de cenários de aplicativo.|-   [Coletando dados de tempo detalhados usando a instrumentação](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**Coletar dados de memória do .NET:** Use a amostragem ou a instrumentação para coletar dados de alocação de memória do .NET que mostra o tamanho e o número de objetos alocados. Também é possível coletar dados de tempo de vida do objeto que mostram o tamanho e o número de objetos recuperados em cada geração de coleta de lixo.|-   [Coletando dados de memória do .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Coletar dados de simultaneidade:** Use o método de simultaneidade para coletar dados de contenção de recursos e dados de atividade do thread que mostram a utilização da CPU, contenção e migração de threads, atrasos na sincronização, áreas de E/S sobrepostas e outros eventos do sistema.|-   [Coletando dados de simultaneidade](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Adicionar dados de interação de camada:** É possível adicionar dados de desempenho sobre chamadas ADO.NET síncronas que o aplicativo efetuou para um banco de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] da Microsoft. Adicionar dados de interação de camada a uma execução de criação de perfil requer procedimentos específicos com ferramentas de criação de perfil de linha de comando.|-   [Coletando dados de interação entre camadas](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Experimente:** Use procedimentos passo a passo para criar o perfil de um aplicativo cliente de exemplo usando o método de amostragem ou de instrumentação.|-   [Passo a passo: Criação de perfil de linha de comando usando amostragem](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [Passo a passo: Criação de perfil de linha de comando usando instrumentação](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  
  
## <a name="related-tasks"></a>Tarefas relacionadas  
  
|Tarefa|Conteúdo relacionado|  
|----------|---------------------|  
|**Aplicativos ASP.NET do perfil**|-   [Criando perfil de aplicativos Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**Profile services (Serviços de perfil)**|-   [Serviços de Criação de Perfil](../profiling/command-line-profiling-of-services.md)|
