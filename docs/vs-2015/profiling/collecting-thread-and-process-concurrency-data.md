---
title: Coletando dados de simultaneidade do thread e do processo | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
ms.assetid: fa03d381-a9ee-408c-876d-05111e29225b
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cf8a9de5f2a7e520a745fab81197016d6e1bd15d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54777006"
---
# <a name="collecting-thread-and-process-concurrency-data"></a>Coletando dados de simultaneidade do thread e do processo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O método de criação de perfil de simultaneidade das Ferramentas de Criação de Perfil [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] permite coletar dados de contenção de recursos que inclui informações sobre cada evento de sincronização que faz com que uma função no aplicativo analisado aguarde para obter acesso a um recurso.  
  
 **Requisitos**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
  É possível especificar o método de criação de perfil de simultaneidade usando um dos seguintes recursos:  
  
- Na primeira página do Assistente de Criação de Perfil, clique em **Simultaneidade**  
  
- Na página **Geral** da caixa de diálogo de propriedades da sessão de desempenho, clique em **Simultaneidade**.  
  
- Na barra de ferramentas do **Gerenciador de Desempenho**, na lista **Método**, clique em **Simultaneidade**.  
  
## <a name="common-tasks"></a>Tarefas comuns  
 É possível especificar outras opções na caixa de diálogo _Sessão de Desempenho_**Páginas de Propriedades** da sessão de desempenho. Para abrir essa caixa de diálogo:  
  
- No **Gerenciador de Desempenho**, clique com o botão direito do mouse no nome da sessão de desempenho e clique em **Propriedades**.  
  
  As tarefas na tabela a seguir descrevem as opções que podem ser especificadas na caixa de diálogo _Sessão de Desempenho_**Páginas de Propriedades** quando você cria o perfil usando o método de simultaneidade.  
  
|Tarefa|Conteúdo relacionado|  
|----------|---------------------|  
|Na página **Geral**, especifique detalhes de nomenclatura para o arquivo de dados de criação de perfil gerado (.vsp).|-   [Como: Definir opções de nome de arquivo de dados de desempenho](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Na página **Iniciar**, especifique o aplicativo a ser iniciado se você tiver vários projetos .exe na solução do seu código.|-   [Como: Especificar o binário a ser iniciado](../profiling/how-to-specify-the-binary-to-start.md)|  
|Na página **Interação de Camada**, adicione dados de chamada ADO.NET à execução de criação de perfil.|-   [Coletando dados de interação entre camadas](../profiling/collecting-tier-interaction-data.md)|  
|Na página **Contadores do Windows**, especifique um ou mais contadores de desempenho de sistema operacional para serem adicionados aos dados de criação de perfil como marcas.|-   [Como: Coletar dados de contador do Windows](../profiling/how-to-collect-windows-counter-data.md)|  
|Na página **Avançado**, especifique a versão do tempo de execução do .NET Framework a ter o perfil criado se seus módulos de aplicativo usarem várias versões. Por padrão, a primeira versão carregada é analisada.|-   [Como: Especificar o tempo de execução do .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|
