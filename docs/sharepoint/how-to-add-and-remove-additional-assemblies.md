---
title: 'Como: Adicionar e remover Assemblies adicionais | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.CustomAssembly
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fa25413a40c9b2333acbaba96d55008dbcebfd39
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60051603"
---
# <a name="how-to-add-and-remove-additional-assemblies"></a>Como: Adicionar e remover assemblies adicionais
  Se um pacote do SharePoint depende de outros assemblies para funcionalidade ou dados, você pode adicionar os assemblies ao seu pacote de solução (. wsp). Dessa forma, o servidor do SharePoint certifica-se de que os assemblies personalizados são instalados com um pacote.

 Você também pode adicionar e alterar os controles seguros e arquivos de recurso de classe associados com os assemblies.

## <a name="add-additional-assemblies-safe-controls-and-class-resources"></a>Adicionar assemblies adicionais, controles seguros e recursos de classe
 Você pode adicionar assemblies adicionais no pacote de solução do SharePoint. Assemblies adicionais em uma solução de área restrita e implantar no cache de assembly global, mas os itens de projeto do SharePoint em uma solução em área restrita são adicionados ao banco de dados. Você também pode adicionar controles seguros e os recursos de classe para esses assemblies adicionais. Para obter mais informações sobre controles seguros, consulte [fornecendo informações de pacote e implantação em itens de projeto](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) ou "Criando uma entrada SafeControl" no [implantação de Web Parts no SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkId=245505).

#### <a name="to-add-an-existing-assembly"></a>Para adicionar um assembly existente

1. Abra o **Designer de pacote**. Para obter mais informações, confira [Como: Personalizar um pacote de solução do SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).

2. Escolha o **avançado** guia.

3. Escolha o **Add** botão e, em seguida, escolha **adicionar Assembly existente** na lista.

     O **adicionar Assembly existente** caixa de diálogo é exibida.

4. Escolha as reticências (![elipse do Designer de dispositivo móvel do ASP.NET](../sharepoint/media/mwellipsis.gif "elipse do Designer de dispositivo móvel do ASP.NET")) e, em seguida, escolha o assembly que você deseja adicionar. É recomendável usar um caminho relativo para o assembly selecionado para fins de portabilidade.

5. Para o **destino de implantação**, escolha o **GlobalAssemblyCache** botão de opção para implantar o assembly no cache de assembly global, ou escolher o **WebApplication** opção botão para implantar o assembly na pasta WebApplication no servidor que está executando o SharePoint.

#### <a name="to-add-an-assembly-from-project-output"></a>Para adicionar um assembly da saída do projeto

1. Abra o **Designer de pacote**.

     Para obter mais informações, confira [Como: Personalizar um pacote de solução do SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).

2. Escolha o **avançado** guia.

3. Escolha o **Add** botão e, em seguida, escolha **adicionar Assembly da saída do projeto** na lista.

     O **adicionar Assembly da saída do projeto** caixa de diálogo é exibida.

4. No **projeto de origem** lista e, em seguida, escolha o projeto de origem que você deseja adicionar.

5. Para o **destino de implantação**, escolha o **GlobalAssemblyCache** botão de opção para implantar o assembly no cache de assembly global, ou escolher o **WebApplication** opção botão para implantar o assembly na pasta WebApplication no servidor que está executando o SharePoint.

#### <a name="to-add-a-safe-control"></a>Para adicionar um controle seguro

1. Abra o **Editar Assembly existente** caixa de diálogo. Para fazer isso, abra o Designer de pacote, escolha o **Advanced** guia, escolha um assembly e, em seguida, escolha o **editar** botão.

2. No **controles seguros** painel, escolha o **clique aqui para adicionar um novo item** botão.

3. No **nome do Assembly** coluna, digite o nome do assembly.

4. No **Namespace** coluna, digite o nome do namespace para o controle seguro.

5. No **nome do tipo** coluna, digite o nome do tipo.

#### <a name="to-add-a-class-resource"></a>Para adicionar um recurso de classe

1. Abra o **Editar Assembly existente** caixa de diálogo. Para fazer isso, abra o Designer de pacote, escolha o **Advanced** guia, escolha um assembly e, em seguida, escolha o **editar** botão.

2. No **recursos de classe** painel, escolha o **clique aqui para adicionar um novo item** botão.

3. No **nome do arquivo** coluna, escolha as reticências (![elipse do Designer de dispositivo móvel do ASP.NET](../sharepoint/media/mwellipsis.gif "elipse do Designer de dispositivo móvel do ASP.NET")) e escolha o recurso de classe que você deseja adicionar.

## <a name="delete-custom-assemblies"></a>Excluir os assemblies personalizados
 Você pode excluir os assemblies de um pacote do SharePoint ou excluir os controles de seguros e recursos de classe de assemblies existentes.

#### <a name="to-delete-an-existing-assembly"></a>Para excluir um assembly existente

1. Abra o **Designer de pacote**. Para obter mais informações, confira [Como: Personalizar um pacote de solução do SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).

2. Escolha o **avançado** guia.

3. No **Assemblies adicionais** painel, escolha o assembly personalizado que você deseja excluir.

4. Escolha o **excluir** botão.

#### <a name="to-delete-a-safe-control-for-an-assembly"></a>Para excluir um controle seguro para um assembly

1. Abra o **Editar Assembly existente** caixa de diálogo. Para fazer isso, abra o Designer de pacote, escolha o **Advanced** guia, escolha um assembly e, em seguida, escolha o **editar** botão.

2. Escolha o controle de seguro que você deseja excluir.

3. Escolha a tecla Delete.

#### <a name="to-delete-a-class-resource-for-an-assembly"></a>Para excluir um recurso de classe para um assembly

1. Abra o **Editar Assembly existente** caixa de diálogo. Para fazer isso, abra o Designer de pacote, escolha o **Advanced** guia, escolha um assembly e, em seguida, escolha o **editar** botão.

2. Escolha o recurso de classe que você deseja excluir.

3. Escolha a tecla Delete.

## <a name="see-also"></a>Consulte também
- [Criar recursos do SharePoint](../sharepoint/creating-sharepoint-features.md)
- [Como: Personalizar um recurso do SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md)
- [Como: Adicionar e remover itens de recursos do SharePoint](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)
