---
title: Criar um pacote de extensão com o modelo de Item do pacote de extensão | Microsoft Docs
ms.date: 07/27/2018
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - extensions
ms.assetid: 5388EEBA-211D-4114-8CD9-70C899919F7E
author: gregvanl
ms.author: gregvanl
manager: Meng
ms.workload:
- vssdk
ms.openlocfilehash: 7899a096bb2a56e93ea55a4ba0a17cde272bd615
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58193699"
---
# <a name="walkthrough-create-an-extension-pack"></a>Passo a passo: Criar um pacote de extensões

Um pacote de extensão é um conjunto de extensões que podem ser instalados juntos. Pacotes de extensão permitem que você facilmente compartilhar suas extensões favoritas com outros usuários ou agrupar um conjunto de extensões em conjunto para um cenário específico.

## <a name="prerequisites"></a>Pré-requisitos

A partir do Visual Studio 2015, o SDK do Visual Studio é incluído como um recurso opcional na instalação do Visual Studio. Você também pode instalar o SDK do VS mais tarde. Para obter mais informações, consulte [instalando o SDK do Visual Studio](../extensibility/installing-the-visual-studio-sdk.md).

O recurso de pacote de extensão está disponível a partir do Visual Studio 15.8 Preview 2.

## <a name="create-an-extension-with-an-extension-pack-item-template"></a>Criar uma extensão com um modelo de item do pacote de extensão

O modelo de item do pacote de extensão cria um pacote de extensão com o conjunto de extensões que podem ser instalados juntos.

1. No **novo projeto** caixa de diálogo, pesquise por "vsix" e selecione **projeto VSIX**. Para **nome do projeto**, digite "Pacote de extensão de teste". Selecione **Criar**.

2. No **Gerenciador de soluções**, clique com botão direito no nó do projeto e selecione **Add** > **Novo Item**. Vá para o Visual C# **extensibilidade** nó e selecione **pacote de extensão**. Deixe o nome de arquivo padrão (ExtensionPack1.cs).

3. Arquivo ExtensionPack1.vsext é adicionado, que contém o código a seguir

   ```json
   {
    "id": "ExtensionPack1",
    "name": "ExtensionPack1",
    "description": "Read about creating extension packs at https://aka.ms/vsextpack",
    "version": "1.0.0.0",
    "extensions": [  // List of extensions that are included in the Extension Pack.
      {
        "vsixId": "41858b2d-ff0b-4a43-80b0-f1b2d6084935", // The vsix id of the extension you want to   include.
        "name": "AlignAssignments"
      },
      {
          "vsixId": "42374550-426a-400e-96f9-237682e8dea6",
        "name": "CopyAsHtml"
      }
    ]
   }
   ```

4. O vsixid da extensão para incluir no pacote de extensão pode ser encontrado na [Visual Studio Marketplace](https://marketplace.visualstudio.com/). Localize a extensão que você deseja incluir e clique em **ID da cópia**. Você pode atualizar existente **vsixId** no arquivo ou adicione outra extensão à lista.

    ![Copiar VsixId do Marketplace](media/vsixid-marketplace.png)

5. Compile o projeto e carregar sua extensão no Marketplace. Ver [publicando uma extensão do Visual Studio](../extensibility/walkthrough-publishing-a-visual-studio-extension.md).

> [!NOTE]
> Um pacote de extensão só pode instalar extensões que estão disponíveis sobre o [Visual Studio Marketplace](https://marketplace.visualstudio.com/) ou [Galeria privada](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md).

## <a name="install-the-extension-pack-from-the-visual-studio-marketplace"></a>Instalar o pacote de extensão do Visual Studio Marketplace

Agora que a extensão for publicada, instalá-lo no Visual Studio e testá-lo lá.

::: moniker range="vs-2017"

1. No Visual Studio, sobre o **ferramentas** menu, clique em **extensões e atualizações**.

::: moniker-end

::: moniker range=">=vs-2019"

1. No Visual Studio, sobre o **extensões** menu, clique em **extensões gerenciadas**.

::: moniker-end

2. Clique em **Online** e, em seguida, pesquise por "Pacote de extensão de teste".

3. Clique em **Baixar**. A extensão e sua lista de extensões incluídas no pacote de extensão, em seguida, serão agendadas para instalação.

4. Abaixo está um exemplo de exibição de download de pacote de extensão do **gerenciar extensões** caixa de diálogo. Se você preferir instalar apenas algumas das extensões incluídas no pacote de extensão, você pode modificar a lista de extensões **agendada para instalar**.

    ![Baixe o pacote de extensão do Marketplace](media/vside-extensionpack.png)

5. Para concluir a instalação, feche todas as instâncias do Visual Studio.

## <a name="remove-the-extension"></a>Remover a extensão

Para remover a extensão do seu computador:

::: moniker range="vs-2017"

1. No Visual Studio, sobre o **ferramentas** menu, clique em **extensões e atualizações**.

::: moniker-end

::: moniker range=">=vs-2019"

1. No Visual Studio, sobre o **extensões** menu, clique em **extensões gerenciadas**.

::: moniker-end

2. Selecione **pacote de extensão de teste** e, em seguida, clique em **desinstalar**. A extensão e sua lista de extensões incluídas no pacote de extensão, em seguida, serão agendadas para desinstalação.

3. Para concluir a desinstalação, feche todas as instâncias do Visual Studio.
