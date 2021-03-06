---
title: Tour do Visual Studio para Mac
description: O Visual Studio para Mac fornece um ambiente de desenvolvimento integrado para compilar aplicativos .NET no macOS, incluindo sites ASP.NET Core e projetos Xamarin para iOS, Android, Mac e Xamarin.Forms.
author: conceptdev
ms.author: crdun
ms.date: 04/02/2019
ms.assetid: 7DC64A52-AA41-4F3A-A8A1-8A20BCD81CC7
ms.custom: video
ms.openlocfilehash: a621faece8ed0cef3dd48d46fc41857af6e62c9e
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856308"
---
# <a name="visual-studio-2019-for-mac-tour"></a>Tour do Visual Studio 2019 para Mac

O Visual Studio para Mac é um _ambiente de desenvolvimento integrado_ do .NET no Mac que você pode usar para editar, depurar e compilar o código e, em seguida, publicar um aplicativo. Além de recursos esperados, tais como o editor e o depurador padrão, o Visual Studio para Mac inclui compiladores, ferramentas de preenchimento de código, designers gráficos e controle do código-fonte para facilitar o processo de desenvolvimento de software.

O Visual Studio para Mac dá suporte a muitos dos mesmos tipos de arquivo que seu equivalente do Windows, tais como arquivos `.csproj`, `.fsproj`, ou `.sln`. Ele também dá suporte a recursos como EditorConfig, o que significa que você pode usar o IDE que melhor funciona para você.
Criar, abrir e desenvolver um aplicativo será uma experiência familiar para qualquer pessoa que já tenha usado o Visual Studio no Windows. Além disso, o Visual Studio para Mac emprega muitas das ferramentas avançadas que fazem do seu equivalente no Windows um IDE tão avançado. A Roslyn Compiler Platform é usada para refatoração e IntelliSense. Seu sistema de projeto e mecanismo de build usam o MSBuild e seu editor de código-fonte dá suporte a pacotes TextMate. Ele usa os mesmos mecanismos de depuração para aplicativos Xamarin e .NET Core, e os mesmos designers para Xamarin.iOS e Xamarin.Android.

## <a name="what-can-i-do-in-visual-studio-for-mac"></a>O que posso fazer no Visual Studio para Mac

O Visual Studio para Mac é compatível com os seguintes tipos de desenvolvimento:

- Aplicativos Web do ASP.NET Core com C#, F# e o suporte para Razor Pages, JavaScript e TypeScript
- Aplicativo de console .NET Core com C# ou F#
- Jogos do Unity multiplataforma e aplicativos com C#
- Aplicativos Android, iOS, tvOS e watchOS no Xamarin com o C# ou F# e XAML
- Aplicativos da área de trabalho Cocoa no C# ou F#

Este artigo explora várias seções do Visual Studio para Mac, mostrando alguns dos recursos que o tornam uma ferramenta avançada para criar esses aplicativos.

## <a name="ide-tour"></a>Tour do IDE

O Visual Studio para Mac está organizado em várias seções para gerenciar configurações e arquivos de aplicativo, criar código do aplicativo e depuração.

## <a name="start-window"></a>Janela de início

Ao iniciar o Visual Studio 2019 para Mac, os novos usuários verão uma janela de entrada. Entre com sua conta Microsoft para ativar uma licença paga (se tiver uma) ou um link para assinaturas do Azure. Você pode pressionar **Ignorar** e entrar mais tarde pelo item de menu **Visual Studio > Entrar**:

![Entrar com sua conta Microsoft](media/ide-tour-2019-start-signin.png)

Usuários conectados verão a nova _janela de início_, que mostra uma lista de projetos recentes e botões para abrir um projeto existente ou criar um novo:

![Escolher entre projetos recentes ou criar algo novo](media/ide-tour-2019-start-projects.png)

## <a name="solutions-and-projects"></a>Soluções e projetos

A imagem abaixo mostra o Visual Studio para Mac com um aplicativo carregado:

![Visual Studio para Mac com um aplicativo carregado](media/ide-tour-image17.png)

As seções a seguir fornecem uma visão geral das principais áreas no Visual Studio para Mac.

## <a name="solution-pad"></a>Painel de Soluções

O Painel de Soluções organiza os projetos em uma solução:

![Projetos organizados no Painel de Soluções](media/ide-tour-image18.png)

É aqui que os arquivos para o código-fonte, recursos, interface do usuário e dependências são organizados em Projetos específicos da plataforma.

Para saber mais sobre como usar os Projetos e Soluções no Visual Studio para Mac, veja o artigo [Projetos e Soluções](/visualstudio/mac/projects-and-solutions).

## <a name="assembly-references"></a>Referências de assembly

As referências de assembly para cada projeto estão disponíveis na pasta Referências:

![Pasta Referências no painel de soluções](media/ide-tour-image19.png)

As referências adicionais são adicionadas usando a caixa de diálogo **Editar Referências**, que é exibida clicando duas vezes na pasta Referências ou selecionando **Editar Referências** em suas ações de menu de contexto:

![Caixa de diálogo Editar Referências](media/ide-tour-image20.png)

Para saber mais sobre como usar Referências no Visual Studio para Mac, veja o artigo [Gerenciando referências em um projeto](/visualstudio/mac/managing-references-in-a-project).

## <a name="dependencies--packages"></a>Dependências/pacotes

Todas as dependências externas usadas em seu aplicativo são armazenadas nas pastas Dependências ou Pacotes, dependendo se você está em um projeto .Net Core ou Xamarin.iOS/Xamarin.Android. Geralmente, eles são fornecidos na forma de um NuGet.

NuGet é o gerenciador de pacote mais popular para desenvolvimento .NET. Com a compatibilidade do NuGet no Visual Studio, você pode facilmente pesquisar e adicionar pacotes ao seu projeto para o aplicativo.

Para adicionar uma dependência ao seu aplicativo, clique com botão direito do mouse sobre a pasta Dependências / Pacotes e selecione **Adicionar Pacotes**:

![Adicionar um pacote NuGet](media/ide-tour-image21.png)

As informações sobre como usar um pacote do NuGet em um aplicativo podem ser encontradas no artigo [Incluindo um projeto NuGet em seu projeto](/visualstudio/mac/nuget-walkthrough).

## <a name="refactoring"></a>Refatoração

O Visual Studio para Mac oferece duas maneiras úteis de refatorar o código: Ações de contexto e Análise de código-fonte. Leia mais sobre elas no artigo [Refatoração](/visualstudio/mac/refactoring).

## <a name="debugging"></a>Depuração

O Visual Studio para Mac tem um depurador nativo para dar suporte à depuração de aplicativos Xamarin.iOS, Xamarin.Mac e Xamarin.Android. O Visual Studio para Mac usa o Mono Soft Debugger, que foi implementado no tempo de execução Mono, permitindo que o IDE depure código gerenciado em todas as plataformas. Para saber mais adicionais sobre a depuração, visite o artigo [Depuração](/visualstudio/mac/debugging).

O depurador contém visualizadores avançados para tipos especiais, como cadeias de caracteres, cores e URLs, bem como tamanhos, coordenadas e curvas de bézier.

Para saber mais sobre visualizações de dados do depurador, visite o artigo [Visualizações de dados](/visualstudio/mac/data-visualizations).

## <a name="version-control"></a>Controle de versão

O Visual Studio para Mac integra-se aos sistemas de controle do código-fonte Git e Subversion. Projetos com controle do código-fonte são marcados com o branch listado ao lado do nome da Solução:

![Nome do branch para indicar o projeto com controle do código-fonte](media/ide-tour-image22.png)

Os arquivos com alterações não confirmadas têm uma anotação em seus ícones no Painel de Soluções, como mostrado na imagem abaixo:

![Arquivos não confirmados no painel de soluções](media/ide-tour-image23.png)

Para saber mais sobre como usar o controle de versão no Visual Studio, veja o artigo [Controle de Versão](/visualstudio/mac/version-control).

## <a name="next-steps"></a>Próximas etapas

- [Instalar o Visual Studio para Mac](installation.md)
- [Examinar as cargas de trabalho disponíveis](/visualstudio/mac/workloads/)

## <a name="related-video"></a>Vídeo relacionados

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Overview/player]

## <a name="see-also"></a>Consulte também

- [IDE do Visual Studio (no Windows)](/visualstudio/ide/visual-studio-ide)
