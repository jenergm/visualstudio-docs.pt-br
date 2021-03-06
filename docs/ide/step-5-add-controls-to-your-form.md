---
title: 'Etapa 5: Adicionar controles ao formulário'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: dc2746f4-0b5c-4674-9ef7-f40f94150f52
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3da5294b085354d85e71445a30395072f091ae23
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55954701"
---
# <a name="step-5-add-controls-to-your-form"></a>Etapa 5: Adicionar controles ao formulário
Nessa etapa, você adiciona controles como um controle <xref:System.Windows.Forms.PictureBox> e um controle <xref:System.Windows.Forms.CheckBox> em seu formulário. Para adicionar controles <xref:System.Windows.Forms.Button> ao seu formulário.

 ![link para vídeo](../data-tools/media/playvideo.gif) Para obter uma versão em vídeo deste tópico, confira [Tutorial 1: Criar um visualizador de imagens no Visual Basic – Vídeo 2](http://go.microsoft.com/fwlink/?LinkId=205211) ou [Tutorial 1: Criar um visualizador de imagens em C# – Vídeo 2](http://go.microsoft.com/fwlink/?LinkId=205200). Esses vídeos usam uma versão anterior do Visual Studio, portanto, existem pequenas diferenças em alguns comandos de menu e em outros elementos da interface do usuário. No entanto, os conceitos e procedimentos funcionam de maneiras semelhantes na versão atual do Visual Studio.

## <a name="to-add-controls-to-your-form"></a>Para adicionar controles ao seu formulário

1.  Vá para a guia **Caixa de Ferramentas** (localizada no lado esquerdo do IDE do Visual Studio) e expanda o grupo **Common Controls**. Isso mostra os controles mais comuns que você vê em formulários.

2.  Escolha o controle **TableLayoutPanel** no formulário. Para verificar se o TableLayoutPanel está selecionado, certifique-se de que o nome aparece na caixa de listagem suspensa na parte superior da janela **Propriedades**. Você também pode escolher os controles de formulário usando a caixa de listagem suspensa na parte superior da janela **Propriedades**. Escolher um controle desta maneira sempre pode ser mais fácil do que escolher um pequeno controle com um mouse.

3.  Clique duas vezes no item **PictureBox** para adicionar um controle PictureBox ao seu formulário. Como o TableLayoutPanel é encaixado para preencher o formulário, a IDE adiciona o controle da PictureBox à primeira célula vazia (canto superior esquerdo).

4.  Escolha o novo controle **PictureBox** para selecioná-lo, e então escolha o triângulo preto no novo controle PictureBox para exibir a lista de tarefas, como mostrado na seguinte imagem.

     ![Tarefas PictureBox](../ide/media/express_pictureboxtasks.png)
Tarefas **PictureBox**

    > [!NOTE]
    >  Se você adicionar acidentalmente o tipo errado de controle a seu TableLayoutPanel, poderá excluí-lo. Clique com o botão direito do mouse no controle e escolha **Excluir** no menu de contexto. Você pode também remover os controles de formulário usando a barra de menus. Na barra de menus, escolha **Editar** > **Desfazer** ou **Editar** > **Excluir**.

5.  Escolha o link **Encaixar no contêiner pai**. Isso define automaticamente a propriedade **Dock** de PictureBox como **Fill**. Para ver isso, escolha o controle **PictureBox** para selecioná-lo, vá para a janela **Propriedades** e certifique-se de que a propriedade **Dock** está definida como **Fill**.

6.  Faça a PictureBox se estender por ambas as colunas alterando sua propriedade **ColumnSpan**. Escolha o controle **PictureBox** e defina sua propriedade **ColumnSpan** como **2**. Além disso, quando a PictureBox está vazia, você deseja mostrar uma estrutura vazia. Defina sua propriedade **BorderStyle** para **Fixed3D**.

    > [!NOTE]
    >  Se você não vir uma propriedade **ColumnSpan** para sua PictureBox, então será provável que a PictureBox tenha sido adicionada ao formulário em vez de ao TableLayoutPanel. Para corrigir isso, escolha o **PictureBox**, exclua-o, escolha o **TableLayoutPanel**, e adicione um novo PictureBox.

7.  Escolha o **TableLayoutPanel** no formulário e adicione um controle CheckBox ao formulário. Clique duas vezes no item **CheckBox** na **Caixa de Ferramentas** para adicionar um novo controle CheckBox à próxima célula livre em sua tabela. Como um PictureBox ocupa as duas primeiras células em TableLayoutPanel, o controle de caixa de seleção é adicionado à célula do canto inferior esquerdo. Escolha a propriedade **Text** e digite a palavra **Stretch**, como mostrado na imagem a seguir.

     ![Controle TextBox com a propriedade Stretch](../ide/media/express_pictureviewercheckbox.png)
Controle **TextBox** com a propriedade **Stretch**

8.  Escolha o **TableLayoutPanel** no formulário e, em seguida, vá para o grupo **Contêineres** na **Caixa de Ferramentas** (na qual você obteve o controle TableLayoutPanel) e clique duas vezes no item **FlowLayoutPanel** para adicionar um novo controle à última célula em PictureBox (canto inferior direito). Encaixe então o FlowLayoutPanel no TableLayoutPanel (escolhendo **Encaixar no contêiner pai** na lista de tarefas de triângulo preto de FlowLayoutPanel ou configurando a propriedade **Dock** de FlowLayoutPanel para **Fill**).

    > [!NOTE]
    >  Um <xref:System.Windows.Forms.FlowLayoutPanel> é um contêiner que organiza outros controles em linhas nítidas na ordem. Quando você redimensiona um FlowLayoutPanel, se ele tiver espaço para colocar todos os controles em uma única linha, ele faz isso. Caso contrário, organize-os em linhas, um sobre o outro. Você usará um FlowLayoutPanel para armazenar quatro botões. Se os botões forem organizados uns sobre os outros quando adicionados, verifique se FlowLayoutPanel está selecionado antes de adicionar os botões. Embora tenha sido indicado anteriormente que cada célula pode conter somente um controle, a célula inferior direita de TableLayoutPanel possui quatro controles de botão. Isso ocorre porque você pode colocar um controle em uma célula que contém outros controles. O tipo de controle é chamado de recipiente, e o FlowLayoutPanel é um recipiente.

## <a name="to-add-buttons"></a>Para adicionar botões

1.  Escolha o novo FlowLayoutPanel que você adicionou. Vá para **Common Controls** na **Caixa de Ferramentas** e clique duas vezes no item **Button** para adicionar um controle de botão chamado **button1** ao seu FlowLayoutPanel. Repita para adicionar outro botão. O IDE determina que já há um botão chamado **button1** e chama o próximo de **button2**.

2.  Normalmente, você adiciona outros botões usando a **caixa de ferramentas**. Desta vez, escolha **button2** e, na barra de menus, escolha **Editar** > **Copiar** (ou pressione **Ctrl**+**C**). Na barra de menus, escolha **Editar** > **Colar** (ou pressione **Ctrl**+**V**) para colar uma cópia do botão. Agora cole-o novamente. O IDE agora adicionou **button3** e **button4** ao FlowLayoutPanel.

    > [!NOTE]
    >  Você pode copiar e colar qualquer controle. O IDE nomeia e coloca os novos controles de uma maneira lógica. Se você colar um controle em um contêiner, o IDE escolherá o próximo espaço lógico para posicionamento.

3.  Escolha o primeiro botão e defina sua propriedade **Text** como **Show a picture**. Em seguida, defina as propriedades **Text** dos próximos três botões como **Limpar a imagem**, **Definir a cor da tela de fundo** e **Fechar**.

4.  A próxima etapa é dimensionar os botões e organizá-los de forma a alinhá-los no lado direito do painel. Escolha o **FlowLayoutPanel** e examine sua propriedade **FlowDirection**. Altere-a para que ela seja definida como **RightToLeft**. Assim que fizer isso, os botões devem alinhar-se para o lado direito da célula e reverter a ordem de modo que o botão **Mostrar uma imagem** fique à direita.

    > [!NOTE]
    >  Se os botões ainda estiverem na ordem errada, você poderá arrastar os botões em torno do FlowLayoutPanel para reorganizá-los em qualquer ordem. Você pode escolher um botão e o arrastar para a esquerda ou direita.

5.  Escolha o botão **Fechar** para selecioná-lo. Mantenha pressionada a tecla **Ctrl** e escolha os outros três botões, de forma que todos eles sejam selecionados. Quando todos os botões são selecionados, vá para a janela **Propriedades** e role até a propriedade **AutoSize**. Essa propriedade informa o botão para redimensionar automaticamente para ajustar todo o texto correspondente. Defina-a como **true**. Os botões agora devem ser dimensionados corretamente e estar na ordem correta. (Enquanto todos os quatro botões estiverem selecionados, você pode alterar todas as quatro propriedades **AutoSize** ao mesmo tempo.) A figura a seguir mostra os quatro botões.

     ![Visualizador de Imagens com quatro botões](../ide/media/express_autosize.png)
**Visualizador de Imagens** com quatro botões

6.  Agora execute o programa novamente para ver seu formulário recentemente apresentado. A escolha dos botões e da caixa de seleção não faz nada ainda, mas funcionará em breve.

## <a name="to-continue-or-review"></a>Para continuar ou revisar

-   Para ir para a próxima etapa do tutorial, confira [Etapa 6: Nomear os controles de botão](../ide/step-6-name-your-button-controls.md).

-   Para retornar à etapa anterior do tutorial, confira [Etapa 4: Definir o layout do formulário com um controle TableLayoutPanel](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md).
