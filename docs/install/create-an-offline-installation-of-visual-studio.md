---
title: Criar uma instalação offline
description: Saiba como instalar o Visual Studio offline quando você tiver uma conexão com a Internet não confiável ou largura de banda baixa.
ms.date: 03/28/2019
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 2b813d92188a2b4e33b87a1391c7ebbea63292f6
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856989"
---
# <a name="create-an-offline-installation-of-visual-studio"></a>Criar uma instalação offline do Visual Studio

::: moniker range="vs-2017"

Projetamos o Visual Studio 2017 para funcionar bem em uma variedade de configurações de rede e do computador. Embora seja recomendável que você experimente o [instalador Web do Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017), que é um arquivo pequeno e permite que você permaneça atualizado com todas as correções e recursos mais recentes, entendemos que talvez você não possa fazer isso.

::: moniker-end

::: moniker range="vs-2019"

Projetamos o Visual Studio 2019 para funcionar bem em uma variedade de configurações de rede e do computador. Embora seja recomendável que você experimente o [instalador Web do Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), que é um arquivo pequeno e permite que você permaneça atualizado com todas as correções e recursos mais recentes, entendemos que talvez você não possa fazer isso.

::: moniker-end

Por exemplo, você pode ter uma conexão com a Internet não confiável ou que tem largura de banda baixa. Nesse caso, você tem algumas opções: Você pode usar a nova funcionalidade "Baixar tudo, depois instalar" para baixar os arquivos antes de instalar ou usar a linha de comando para criar um cache local dos arquivos.

> [!NOTE]
> Se você for um administrador de empresas que deseja executar uma implantação do Visual Studio em uma rede de estações de trabalho cliente protegidas da Internet por firewall, confira nossas páginas [Criar uma instalação de rede do Visual Studio](../install/create-a-network-installation-of-visual-studio.md) e [Instalar os certificados necessários para a instalação offline do Visual Studio](../install/install-certificates-for-visual-studio-offline.md).

## <a name="use-the-download-all-then-install-feature"></a>Usar o recurso "baixar tudo, depois instalar"

::: moniker range="vs-2017"

[**Novidades na versão 15.8**](/visualstudio/releasenotes/vs2017-relnotes-v15.8#install): Depois de baixar o instalador da Web, selecione a nova opção **Baixar tudo, depois instalar** do Instalador do Visual Studio. Em seguida, continue com a instalação.

   ![A opção "Baixar tudo, depois instalar"](media/download-all-then-install.png)

::: moniker-end

::: moniker range="vs-2019"

Depois de baixar o instalador da Web, selecione a nova opção **Baixar tudo, depois instalar** do Instalador do Visual Studio. Em seguida, continue com a instalação.

   ![A opção "Baixar tudo, depois instalar"](media/vs-2019/download-all-then-install-from-installer.png)

::: moniker-end

Criamos o recurso "Baixar tudo, depois instalar" para que você possa baixar o Visual Studio como uma instalação única, no mesmo computador em que você o baixar. Dessa maneira, você pode se desconectar com segurança da Web antes de instalar o Visual Studio.

> [!IMPORTANT]
> Não use o recurso "Baixar tudo, depois instalar" para criar um cache offline, que você pretende transferir para outro computador. Ele não foi desenvolvido para funcionar dessa maneira. <br><br>Se pretende criar um cache offline para instalar o Visual Studio em outro computador, confira a seção [Usar a linha de comando para criar um cache local](#use-the-command-line-to-create-a-local-cache) nesta página para saber como criar um cache local. Para saber mais sobre como criar um cache de rede, confira a página [Criar uma instalação de rede do Visual Studio](../install/create-a-network-installation-of-visual-studio.md).

## <a name="use-the-command-line-to-create-a-local-cache"></a>Use a linha de comando para criar um cache local

Depois de baixar um bootstrapper pequeno, use a linha de comando para criar um cache local. Em seguida, use o cache local para instalar o Visual Studio. (Esse processo substitui os arquivos ISO que estavam disponíveis para versões anteriores.)

Veja como.

### <a name="step-1---download-the-visual-studio-bootstrapper"></a>Etapa 1 – Baixar o bootstrapper do Visual Studio

É preciso ter uma conexão com a Internet para concluir esta etapa.

Comece baixando o bootstrapper do Visual Studio para sua edição do Visual Studio escolhida. O arquivo de instalação, ou bootstrapper, corresponderá ou será semelhante a um dos listados a seguir.

::: moniker range="vs-2017"

| Edição                    | Arquivo                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Comunidade Visual Studio    | [vs_community.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2017)       |
| Visual Studio Professional | [vs_professional.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2017) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2017)     |

::: moniker-end

::: moniker range="vs-2019"

| Edição                    | Arquivo                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Comunidade Visual Studio    | [vs_community.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019)       |
| Visual Studio Professional | [vs_professional.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019)     |

::: moniker-end

### <a name="step-2---create-a-local-install-cache"></a>Etapa 2 – Criar um cache local de instalação

É preciso ter uma conexão com a Internet para concluir esta etapa.

> [!IMPORTANT]
> Se você instalar o Visual Studio Community, deverá ativá-lo no prazo de 30 dias após a instalação. Isso exige uma conexão com a Internet.

Abra um prompt de comando e use um dos comandos dos exemplos a seguir. Os exemplos listados aqui supõem que você esteja usando a edição Community do Visual Studio; ajuste o comando conforme apropriado para sua edição.

> [!TIP]
> Para evitar erro, certifique-se de que seu caminho de instalação completo seja menor do que 80 caracteres.

- Para .NET Web e desenvolvimento de área de trabalho do .NET, execute:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
    ```

- Para a área de trabalho do .NET e o desenvolvimento do Office, execute:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US
    ```

- Para desenvolvimento do C++ da área de trabalho, execute:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US
    ```

- Para criar um layout de local completo com todos os recursos (isso levará algum tempo&mdash;, pois temos _muitos_ recursos!), execute:

   ```cmd
    vs_community.exe --layout c:\vslayout --lang en-US
    ```

  > [!NOTE]
  > Um layout completo do Visual Studio exige no mínimo 35 GB de espaço em disco. Confira [Usar parâmetros de linha de comando para instalar o Visual Studio](use-command-line-parameters-to-install-visual-studio.md) para saber mais sobre como criar um layout apenas com os componentes que você deseja instalar.

Se você quiser instalar um idioma diferente do inglês, altere `en-US` para uma localidade da [lista de localidades de idioma](#list-of-language-locales). Em seguida, use a [lista de componentes e cargas de trabalho disponíveis](workload-and-component-ids.md) para personalizar ainda mais o cache de instalação.

### <a name="step-3---install-visual-studio-from-the-local-cache"></a>Etapa 3 – Instalar o Visual Studio do cache local

> [!TIP]
> Ao executar de um cache local de instalação, usaremos as versões locais de cada um desses arquivos. Porém, se durante a instalação você selecionar componentes que não estão no cache, tentaremos baixá-los da Internet.

Para garantir que você instale somente os arquivos que baixou, use as mesmas opções de linha de comando que usou para criar o cache de layout. Por exemplo, se você tiver criado um cache de layout com o seguinte comando:

```cmd
vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
```

Depois use este comando para executar a instalação:

```cmd
c:\vslayout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional
```

> [!NOTE]
> Caso ocorra um erro indicando que a assinatura é inválida, será necessário instalar certificados atualizados. Abra a pasta Certificados no cache offline. Clique duas vezes em cada um dos arquivos de certificado e, em seguida, clique no assistente do Gerenciador de Certificados. Se for solicitado que você forneça uma senha, deixe-a em branco.

### <a name="list-of-language-locales"></a>Lista de localidades de idioma

| **Localidade de idioma** | **Idioma** |
| ----------------------- | --------------- |
| cs-CZ | Tcheco |
| de-DE | Alemão |
| en-US | Inglês |
| es-ES | Espanhol |
| fr-FR | Francês |
| it-IT | Italiano |
| ja-JP | Japonês |
| ko-KR | Coreano |
| pl-PL | Polonês |
| pt-BR | Português - Brasil |
| ru-RU | Russo |
| tr-TR | Turco |
| zh-CN | Chinês – Simplificado |
| zh-TW | Chinês – Tradicional |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Consulte também

- [Criar uma instalação de rede do Visual Studio](../install/create-a-network-installation-of-visual-studio.md)
- [Instalar os certificados necessários para instalação offline do Visual Studio](../install/install-certificates-for-visual-studio-offline.md)
- [Usar parâmetros de linha de comando para instalar o Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
- [IDs de carga de trabalho e de componente do Visual Studio](workload-and-component-ids.md)
