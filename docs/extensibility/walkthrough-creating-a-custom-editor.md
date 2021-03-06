---
title: 'Passo a passo: Criar um Editor personalizado | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - create
ms.assetid: d090abb6-d99f-4083-a3db-cd16bf81ce7d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f85963712fa1b051ea7256e6f805fe8e7c7e70d0
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60056544"
---
# <a name="walkthrough-create-a-custom-editor"></a>Passo a passo: Criar um editor personalizado
O modelo de projeto de VSPackage pode criar um editor personalizado simple em C++. O modelo de projeto de VSPackage não dá suporte a projetos em C# ou Visual Basic. Para obter mais informações, consulte [SDK do Visual Studio](../extensibility/visual-studio-sdk.md).

## <a name="prerequisites"></a>Pré-requisitos
 Para seguir este passo a passo, você deve instalar o SDK do Visual Studio. Para obter mais informações, consulte [instalar o SDK do Visual Studio](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="the-visual-studio-package-project-template"></a>O modelo de projeto do Visual Studio Package
 Você pode encontrar o modelo de projeto no Visual Studio Package a **novo projeto** diálogo sob o **C++ extensibilidade** pasta.

### <a name="to-create-a-vspackage-using-the-visual-studio-package-template"></a>Para criar um VSPackage usando o modelo de pacote do Visual Studio

1. Crie um projeto com o modelo de pacote do Visual Studio.

2. Selecione o **Editor personalizado** opção e clique em **próxima**. O **opções do Editor** página será exibida.

3. Digite o nome do seu editor na **nome do Editor** caixa. Digite a extensão de arquivo que você deseja ser associado com seu editor na **extensão de arquivo** caixa. O editor está disponível para arquivos com essa extensão. A extensão de arquivo está registrada para o Visual Studio apenas, não para Windows. Digite o nome de arquivo padrão para novos documentos criados com o seu editor na **nome de arquivo padrão** caixa.

4. Clique em **concluir** para criar o VSPackage na pasta que você especificou.

### <a name="to-test-your-custom-editor"></a>Para testar seu editor personalizado

1. Sobre o **arquivo** , aponte para **New** e, em seguida, clique em **arquivo**.

2. No **modelos instalados** painel da **novo arquivo** caixa de diálogo, selecione o modelo de arquivo e, em seguida, o arquivo de tipo que você registrou.

3. Clique em **abrir** para exibir e editar o documento.

     O editor dá suporte a operações de recortar e colar, localizar e substituir e aberto e de carga.

## <a name="see-also"></a>Consulte também
- [VSPackages](../extensibility/internals/vspackages.md)