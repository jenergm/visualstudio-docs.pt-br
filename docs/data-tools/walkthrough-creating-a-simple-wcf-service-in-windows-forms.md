---
title: 'Passo a passo: criando um Serviço WCF simples no Windows Forms'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WCF, walkthrough [Visual Studio]
- WCF, Visual Studio tools for
- WCF services
- WCF services, walkthrough
ms.assetid: 5fef1a64-27a4-4f10-aa57-29023e28a2d6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 97bbf8212caf87f28849df15d350811579f22ccd
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58325221"
---
# <a name="walkthrough-create-a-simple-wcf-service-in-windows-forms"></a>Passo a passo: Criar um serviço WCF simples no Windows Forms

Este passo a passo demonstra como criar um serviço simples do Windows Communication Foundation (WCF), testá-lo e, em seguida, acessá-lo de um aplicativo Windows Forms.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="create-a-service"></a>Criar um serviço

1. Abra o Visual Studio.

::: moniker range="vs-2017"

2. No menu **Arquivo**, escolha **Novo** > **Projeto**.

3. No **novo projeto** diálogo caixa, expanda o **Visual Basic** ou **Visual C#**  nó e escolha **WCF**, seguido por **WCF Service Library**.

4. Clique em **OK** para criar o projeto.

   ![O projeto de biblioteca de serviço do WCF](../data-tools/media/wcf1.png)

::: moniker-end

::: moniker range=">=vs-2019"

2. Na tela Iniciar, selecione **Criar um novo projeto**.

3. Tipo de **biblioteca de serviço wcf** na caixa de pesquisa na **criar um novo projeto** página. Selecione o C# ou o modelo de Visual Basic para **WCF Service Library**e, em seguida, clique em **próxima**.

   ![Criar novo projeto de biblioteca de serviço WCF no Visual Studio de 2019](media/vs-2019/create-new-wcf-service-library.png)

   > [!TIP]
   > Se você não vir todos os modelos, você talvez precise instalar o **Windows Communication Foundation** componente do Visual Studio. Escolher **instalar mais ferramentas e recursos** para abrir o instalador do Visual Studio. Escolha o **componentes individuais** guia, role para baixo até **atividades de desenvolvimento**e, em seguida, selecione **Windows Communication Foundation**. Clique em **Modificar**.

4. Sobre o **configurar seu novo projeto** , clique em **criar**.

::: moniker-end

   > [!NOTE]
   > Isso cria um serviço de trabalho que pode ser testado e acessado. As duas etapas a seguir demonstram como você pode modificar o método padrão para usar um tipo de dados diferentes. Em um aplicativo real, você também adicionaria suas próprias funções para o serviço.

5. Na **Gerenciador de soluções**, clique duas vezes em **IService1.vb** ou **IService1.cs**.

   ![O arquivo IService1](../data-tools/media/wcf2.png)

   Localize a seguinte linha:

   [!code-csharp[WCFWalkthrough#4](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.cs)]
   [!code-vb[WCFWalkthrough#4](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.vb)]

   Alterar o tipo para o `value` parâmetro de cadeia de caracteres:

   [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.cs)]
   [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.vb)]

   No código acima, observe os `<OperationContract()>` ou `[OperationContract]` atributos. Esses atributos são necessários para qualquer método exposto pelo serviço.

6. Na **Gerenciador de soluções**, clique duas vezes em **Service1.vb** ou **Service1.cs**.

   ![O arquivo Service1](../data-tools/media/wcf3.png)

   Localize a seguinte linha:

   [!code-vb[WCFWalkthrough#5](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.vb)]
   [!code-csharp[WCFWalkthrough#5](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.cs)]

   Alterar o tipo para o `value` parâmetro de cadeia de caracteres:

   [!code-csharp[WCFWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.cs)]
   [!code-vb[WCFWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.vb)]

## <a name="test-the-service"></a>Testar o serviço

1. Pressione **F5** para executar o serviço. Um **cliente de teste do WCF** formulário é exibida e carrega o serviço.

2. No **cliente de teste do WCF** de formulário, clique duas vezes o **GetData ()** método sob **IService1**. O **GetData** guia é exibida.

     ![O GetData&#40; &#41; método](../data-tools/media/wcf4.png)

3. No **solicitar** caixa, selecione a **valor** campo e digite `Hello`.

     ![O campo de valor](../data-tools/media/wcf5.png)

4. Clique o **Invoke** botão. Se um **aviso de segurança** caixa de diálogo for exibida, clique em **Okey**. O resultado exibe o **resposta** caixa.

     ![O resultado na caixa de resposta](../data-tools/media/wcf6.png)

5. Sobre o **arquivo** menu, clique em **sair** para fechar o formulário de teste.

## <a name="access-the-service"></a>O serviço de acesso

### <a name="reference-the-wcf-service"></a>Referência de serviço do WCF

1. No menu **Arquivo**, aponte para **Adicionar** e clique em **Novo Projeto**.

2. No **novo projeto** diálogo caixa, expanda o **Visual Basic** ou **Visual C#** nó, selecione **Windows**e, em seguida, selecione  **Aplicativo de formulários do Windows**. Clique em **Okey** para abrir o projeto.

     ![Projeto de aplicativo do Windows Forms](../data-tools/media/wcf7.png)

3. Clique com botão direito **WindowsApplication1** e clique em **Add Service Reference**. O **adicionar referência de serviço** caixa de diálogo é exibida.

4. Na caixa de diálogo **Adicionar Referência de Serviço**, clique em **Descobrir**.

     ![A caixa de diálogo Adicionar referência de serviço](../data-tools/media/wcf8.png)

     **Service1** exibe as **Services** painel.

5. Clique em **Okey** para adicionar a referência de serviço.

### <a name="build-a-client-application"></a>Criar um aplicativo cliente

1. Na **Gerenciador de soluções**, clique duas vezes em **Form1.vb** ou **Form1.cs** para abrir o Designer de formulários do Windows, se ele não ainda estiver aberto.

2. Dos **caixa de ferramentas**, arraste um `TextBox` controle, um `Label` controle e um `Button` controle para o formulário.

     ![Adicionando controles ao formulário](../data-tools/media/wcf9.png)

3. Clique duas vezes o `Button`e adicione o seguinte código no `Click` manipulador de eventos:

     [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.cs)]
     [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.vb)]

4. Na **Gerenciador de soluções**, clique com botão direito **WindowsApplication1** e clique em **Set as StartUp Project**.

5. Pressione **F5** para executar o projeto. Digite algum texto e clique no botão. Exibe o rótulo "você digitou:" e mostra o texto que você inseriu.

     ![O formulário mostrando o resultado](../data-tools/media/wcf10.png)

## <a name="see-also"></a>Consulte também

- [Serviços do Windows Communication Foundation e WCF Data Services no Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)