---
title: Criando um projeto de serviço de nuvem do Azure
description: Saiba como criar um projeto de serviço de nuvem do Azure com o Visual Studio
author: ghogen
manager: jillfra
assetId: ec580df7-3dcc-45a9-a1d9-8c110678dfb5
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: c4daf3d92aa08e6dbbb81eac79112772900d08d8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58923925"
---
# <a name="creating-an-azure-cloud-service-project-with-visual-studio"></a>Criando um projeto de serviço de nuvem do Azure com o Visual Studio
As Ferramentas do Azure para Visual Studio fornecem um modelo de projeto que permite criar um [serviço de nuvem do Azure](/azure/cloud-services/cloud-services-choose-me), que é um serviço simples do Azure para fins gerais. Após a criação do projeto, o Visual Studio permite configurar, depurar e implantar o serviço de nuvem no Azure.

## <a name="steps-to-create-an-azure-cloud-service-project-in-visual-studio"></a>Etapas para criar um projeto de serviço de nuvem do Azure no Visual Studio
Esta seção explica como criar um projeto de serviço de nuvem do Azure no Visual Studio com uma ou mais funções web.

1. Inicie o Visual Studio como administrador.

1. No menu principal, selecione **Arquivo** > **Novo** > **Projeto**.

1. Selecione **Nuvem** nos nós do modelo de projeto do Visual C# ou Visual Basic e selecione **Serviço de Nuvem do Azure** na lista de modelos.

    ![Novo serviço de nuvem do Azure](./media/vs-azure-tools-azure-project-create/new-project-wizard-for-cloud-service.png)

1. Especifica qual versão do .NET Framework você deseja usar para desenvolver o projeto.

1. Insira um nome e local para seu projeto e um nome para a solução.

1. Selecione **OK**.

1. Na caixa de diálogo **Novo Serviço de Nuvem do Microsoft Azure**, selecione as funções que você deseja adicionar e escolha o botão de seta para a direita para adicioná-las à solução.

    ![Selecionar novas funções do serviço de nuvem do Azure](./media/vs-azure-tools-azure-project-create/new-cloud-service.png)

1. Para renomear uma função adicionada, focalize a função na caixa de diálogo **Novo Serviço de Nuvem do Microsoft Azure** e, no menu de contexto, selecione **Renomear**. Você também pode renomear uma função na solução (no **Gerenciador de Soluções**) depois de adicioná-la.

    ![Renomear uma função do serviço de nuvem do Azure](./media/vs-azure-tools-azure-project-create/new-cloud-service-rename.png)

O projeto do Azure no Visual Studio tem associações aos projetos de função na solução. Ele também inclui o *arquivo de definição de serviço* e o *arquivo de configuração de serviço*:

- **Arquivo de definição de serviço** – define as configurações de tempo de execução do aplicativo, incluindo quais funções são necessárias, pontos de extremidade e tamanho da máquina virtual.
- **Arquivo de configuração de serviço** – configura quantas instâncias de uma função são executadas e os valores das configurações definidas para uma função.

Para obter mais informações sobre esses arquivos, consulte [Configurar as funções para um serviço de nuvem do Azure com o Visual Studio](vs-azure-tools-configure-roles-for-cloud-service.md).

## <a name="next-steps"></a>Próximas etapas
- [Gerenciando funções em projetos de serviço de nuvem do Azure com o Visual Studio](./vs-azure-tools-cloud-service-project-managing-roles.md)
