---
ms.openlocfilehash: 0fc18fab56f5b46ef097cdf699e4f0569dc190c9
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58342632"
---
A Implantação da Web 3.6 para Servidores de Hospedagem fornece recursos adicionais de configuração que permitem a criação do arquivo de configurações da publicação por meio da interface do usuário.

1. Se você já tiver a Implantação da Web 3.6 instalada no Windows Server, desinstale-a usando **Painel de Controle** > **Programas** > **Desinstalar um Programa**.

2. Em seguida, instale Implantação da Web 3.6 para Servidores de Hospedagem no Windows Server.

    Para instalar a Implantação da Web para Servidores de Hospedagem, use o [WebPI (Web Platform Installer)](https://www.microsoft.com/web/downloads/platform.aspx). (Para localizar o link do Web Platform Installer do IIS, selecione **IIS** no painel esquerdo do Gerenciador do Servidor. Clique com o botão direito do mouse e selecione **Gerenciador do IIS (Serviços de Informações da Internet)**).

    No Web Platform Installer, você encontra a **Implantação da Web para Servidores de Hospedagem** na guia Aplicativos.

3. Se você ainda não instalou as **Ferramentas e Scripts de Gerenciamento do IIS**, instale-as agora.

    Acesse **Selecionar funções de servidor** > **Servidor Web (IIS)** > **Ferramentas de Gerenciamento** e, em seguida, selecione a função **Scripts de gerenciamento e ferramentas do IIS**, clique em **Avançar** e, em seguida, instale a função.

    ![Instalar Scripts de gerenciamento e ferramentas do IIS](../../deployment/media/tutorial-iis-management-scripts-and-tools.png)

    Os scripts e as ferramentas são necessários para permitir a geração do arquivo de configurações da publicação.

4. (Opcional) Verifique se a Implantação da Web está em execução corretamente abrindo **Painel de Controle > Sistema e Segurança > Ferramentas Administrativas > Serviços** e verifique se o **Serviço do Agente de Implantação da Web** está em execução (o nome do serviço é diferente em versões mais antigas).

    Se o serviço de agente não estiver em execução, inicie-o. Se não estiver presente em todos os, acesse **painel de controle > Programas > desinstalar um programa**, localize **Microsoft Web Deploy \<versão >**. Escolha **Alterar** a instalação e certifique-se de escolher **Será instalado na unidade de disco rígido local** para os componentes de Implantação da Web. Conclua as etapas de instalação de alteração.