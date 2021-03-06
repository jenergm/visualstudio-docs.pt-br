---
title: Usar o Visual Studio para criar seu primeiro aplicativo de console em C#
titleSuffix: ''
description: Saiba como criar passo a passo um aplicativo simples de console Olá, Mundo no Visual Studio em C#.
ms.custom: seodec18
ms.date: 03/23/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: quickstart
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: a90324d1d9321be3f3105d5830e0c08927c4f535
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856574"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-c-console-app"></a>Início Rápido: Usar o Visual Studio para criar seu primeiro aplicativo de console em C#

Nesta introdução de 5 a 10 minutos ao IDE (ambiente de desenvolvimento integrado) do Visual Studio, você criará um aplicativo simples em C# para ser executado no console.

::: moniker range="vs-2017"

Se você ainda não tiver instalado o Visual Studio, acesse a página [Downloads do Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) para instalá-lo gratuitamente.

::: moniker-end

::: moniker range="vs-2019"

Se você ainda não tiver instalado o Visual Studio, acesse a página [Downloads do Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) para instalá-lo gratuitamente.

::: moniker-end

## <a name="create-a-project"></a>Criar um projeto

Primeiro, você criará um projeto de aplicativo em C#. O tipo de projeto inclui todos os arquivos de modelo que você precisará, mesmo sem adicionar nada!

::: moniker range="vs-2017"

1. Abra o Visual Studio 2017.

2. Na barra de menus superior, escolha **Arquivo** > **Novo** > **Projeto**.

3. Na caixa de diálogo **Novo Projeto** no painel esquerdo, expanda **C#** e escolha **.NET Core**. No painel central, escolha **Aplicativo de Console (.NET Core)**. Em seguida, nomeie o projeto como *HelloWorld*.

   ![Modelo de projeto do aplicativo do console (.NET Core) na caixa de diálogo Novo projeto no IDE do Visual Studio](../ide/media/new-project-csharp-dotnetcore-helloworld-console-app.png)

     Se você não vir o modelo de projeto do **Aplicativo de Console (.NET Core)**, escolha o link **Abrir Instalador do Visual Studio** no painel esquerdo da caixa de diálogo **Novo Projeto**.

   ![Escolha o link Abrir Instalador do Visual Studio na caixa de diálogo Novo Projeto](../ide/media/csharp-open-visual-studio-installer-hello-world.png)

     O Instalador do Visual Studio é iniciado. Escolha a carga de trabalho **Desenvolvimento multiplaforma do .NET Core** e, em seguida, selecione **Modificar**.

     ![Carga de trabalho de desenvolvimento multiplataforma do .NET Core no Instalador do Visual Studio](../ide/media/dot-net-core-xplat-dev-workload.png)

::: moniker-end

::: moniker range="vs-2019"

1. Abra o Visual Studio 2019.

1. Na tela Iniciar, selecione **Criar um novo projeto**.

   ![Janela 'Criar um novo projeto'](../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Na janela **Criar um novo projeto**, insira ou digite *console* na caixa de pesquisa. Em seguida, escolha **C#** na lista Linguagem de programação e, em seguida, escolha **Windows** na lista Plataforma. 

   Depois de aplicar os filtros de linguagem de programação e plataforma, escolha o modelo **Aplicativo de Console (.NET Core)** e, em seguida, escolha **Avançar**.

   ![Escolha o modelo de C# para o Aplicativo de Console (.NET Framework)](../get-started/csharp/media/vs-2019/csharp-create-new-project-search-console-net-core-filtered.png)

   > [!NOTE]
   > Se não vir o modelo **Aplicativo de Console (.NET Core)**, você poderá instalá-lo da janela **Criar um novo projeto**. Na mensagem **Não encontrou o que precisa?**, escolha o link **Instalar mais ferramentas e recursos**.
   >
   > ![O link 'Instalar mais ferramentas e recursos' da mensagem 'Não encontrou o que precisa?' na janela 'Criar novo projeto'](../get-started/media/vs-2019/not-finding-what-looking-for.png) 
   > 
   > Em seguida, no Instalador do Visual Studio, escolha a carga de trabalho de **desenvolvimento multiplataforma do .NET Core**.
   >
   > ![Carga de trabalho de desenvolvimento multiplataforma do .NET Core no Instalador do Visual Studio](./media/dot-net-core-xplat-dev-workload.png)
   >
   > Depois disso, escolha o botão **Modificar** no Instalador do Visual Studio. Pode ser solicitado que você salve seu trabalho; nesse caso, faça isso. Em seguida, escolha **Continuar** para instalar a carga de trabalho. Em seguida, retorne para a etapa 2 deste procedimento para "[Criar um projeto](#create-a-project)".

1. Na janela **Configurar seu novo projeto**, digite ou insira *OláMundo* na caixa **Nome do projeto**. Em seguida, escolha **Criar**.

   ![Na janela "Configurar seu novo projeto", dê ao projeto o nome 'OláMundo'](../get-started/csharp/media/vs-2019/csharp-name-your-helloworld-project.png)

   O Visual Studio abre seu novo projeto.
   
::: moniker-end

## <a name="create-the-application"></a>Criar o aplicativo

::: moniker range="vs-2017"

Depois que você seleciona o modelo em C# e dá um nome ao projeto, o Visual Studio cria um aplicativo simples “Olá, Mundo”.

::: moniker-end

::: moniker range="vs-2019"

O Visual Studio inclui o código de "Olá, Mundo" padrão em seu projeto.

::: moniker-end

Para isso, ele chama o método <xref:System.Console.WriteLine%2A> para exibir a cadeia de caracteres literal "Olá, Mundo!" na janela do console.

   ![Exibir o código Olá, Mundo padrão do modelo](../ide/media/csharp-console-helloworld-template.png)

Se pressionar **F5**, você poderá executar o programa no modo de depuração. Entretanto, a janela do console fica visível somente por um momento antes de fechar.

(Esse comportamento ocorre porque o método `Main` é encerrado após a execução da única instrução e, portanto, o aplicativo é encerrado.)

### <a name="add-some-code"></a>Adicionar código

Vamos adicionar alguns códigos para pausar o aplicativo de modo que a janela do console não seja fechada até você pressionar **Enter**.

1. Adicione o seguinte código imediatamente após a chamada ao método <xref:System.Console.WriteLine%2A>:

   ```csharp
   Console.ReadLine();
   ```

1. Verifique se tem esta aparência no editor de código:

   ![Adicione o código para pausar o aplicativo Olá, Mundo](../ide/media/csharp-console-helloworld-add-code.png)

## <a name="run-the-application"></a>Executar o aplicativo

1. Escolha o botão **HelloWorld** na barra de ferramentas para executar o aplicativo no modo de depuração. Ou pressione **F5**.

   ![Escolha o botão Olá, Mundo para executar o aplicativo da barra de ferramentas](../ide/media/csharp-console-hello-world-button.png)

1. Visualize o aplicativo na janela do console.

   ![Janela do console mostrando Olá, Mundo!](../ide/media/csharp-console-hello-world.png)

### <a name="close-the-application"></a>Feche o aplicativo

1. Pressione **Enter** para fechar a janela do console.

1. Feche o painel **Saída** no Visual Studio.

   ![Fechar o painel Saída no Visual Studio](../ide/media/csharp-hello-world-close-output-pane.png)

1. Feche o Visual Studio.

## <a name="next-steps"></a>Próximas etapas

Parabéns por concluir este Guia de Início Rápido! Esperamos que você tenha aprendido um pouco sobre C# e o IDE do Visual Studio. Para saber mais, continue com os tutoriais a seguir.

> [!div class="nextstepaction"]
> [Introdução ao aplicativo de console do C# no Visual Studio](../get-started/csharp/tutorial-console.md)
