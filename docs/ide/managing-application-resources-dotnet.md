---
title: Gerenciar recursos do aplicativo (.NET)
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- Resource Designer
- resources [Visual Studio]
- Resources page in Project Designer
- application resources [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1681484500c382b296a03e78661b808825768a5b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62538103"
---
# <a name="manage-application-resources-net"></a>Gerenciar recursos do aplicativo (.NET)

Arquivos de recurso são arquivos que fazem parte de um aplicativo, mas não são compilados, por exemplo, arquivos de ícone ou arquivos de áudio. Como esses arquivos não fazem parte do processo de compilação, você pode alterá-los sem precisar recompilar os binários. Se estiver planejando localizar seu aplicativo, você deverá usar arquivos de recurso para todas as cadeias de caracteres e outros recursos que precisam ser alterados ao localizar o aplicativo.

> [!NOTE]
> Este tópico aplica-se ao Visual Studio no Windows. Para o Visual Studio para Mac, confira [Gerenciando recursos de aplicativo (Visual Studio para Mac)](/visualstudio/mac/managing-app-resources).

Para obter mais informações sobre recursos em aplicativos de área de trabalho do .NET, confira [Recursos em aplicativos de área de trabalho](/dotnet/framework/resources/index).

## <a name="work-with-resources"></a>Trabalhar com recursos

Em um projeto de código gerenciado, abra a janela de propriedades do projeto. Você pode abrir a janela Propriedades das seguintes maneiras:

- Clicando com o botão direito do mouse no nó do projeto, no **Gerenciador de Soluções**, e selecionar **Propriedades**
- Digitando **propriedades do projeto** na caixa de pesquisa **Ctrl**+**Q**
- Escolhendo **Alt**+**Enter** no **Gerenciador de Soluções**

Selecione a guia **Recursos**. Você poderá adicionar um arquivo *.resx* se o projeto ainda não contiver um, adicionar e excluir diferentes tipos de recursos e modificar os recursos existentes.

## <a name="resources-in-other-project-types"></a>Recursos em outros tipos de projeto

Recursos são gerenciados de forma diferente em projetos do .NET que em outros tipos de projeto. Para obter mais informações sobre os recursos em:

- Aplicativos UWP (Plataforma Universal do Windows), consulte [Recursos do aplicativo e o Sistema de Gerenciamento de Recursos](/windows/uwp/app-resources/)
- Projetos C++, confira [trabalhar com arquivos de recurso](/cpp/windows/working-with-resource-files) e [Como: Criar um recurso](/cpp/windows/how-to-create-a-resource)

## <a name="see-also"></a>Consulte também

- [Recursos em aplicativos de área de trabalho (.NET Framework)](/dotnet/framework/resources/index)
- [Gerenciando recursos de aplicativo (Visual Studio para Mac)](/visualstudio/mac/managing-app-resources)
