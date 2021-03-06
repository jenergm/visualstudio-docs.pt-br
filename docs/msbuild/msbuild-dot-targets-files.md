---
title: Arquivos .targets do MSBuild | Microsoft Docs
ms.date: 02/24/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- .Targets files
- MSBuild, .Targets files
ms.assetid: f6d98eb4-d2fa-49b7-8e3c-bae1ca3cf596
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fa0366fed1a405acfa600e9af594e32c1ab47346
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56623743"
---
# <a name="msbuild-targets-files"></a>Arquivos .targets do MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] inclui vários arquivos *.targets* que contêm itens, propriedades, destinos e tarefas para cenários comuns. Esses arquivos são automaticamente importados para a maioria dos arquivos de projeto [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] para simplificar a manutenção e a legibilidade.

 Normalmente, os projetos importam um ou mais arquivos *.targets* para definir o processo de build. Por exemplo, um projeto [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] criado pelo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] importará *Microsoft.CSharp.targets*, que importa *Microsoft.Common.targets*. O próprio projeto [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] definirá as propriedades e os itens específicos desse projeto, mas as regras de build padrão para um projeto [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] são definidas nos arquivos *.targets* importados.

 O valor `$(MSBuildToolsPath)` especifica o caminho desses arquivos *.targets* comuns. Se o `ToolsVersion` for 4.0, os arquivos estarão na seguinte localização: *\<CaminhoDeInstalaçãoDoWindows>\Microsoft.NET\Framework\v4.0.30319\\*

> [!NOTE]
>  Para obter informações sobre como criar seus próprios destinos, consulte [Destinos](../msbuild/msbuild-targets.md). Para obter informações sobre como usar o elemento `Import` para inserir um arquivo de projeto em outro arquivo de projeto, confira [Elemento Import (MSBuild)](../msbuild/import-element-msbuild.md) e [Como: Usar o mesmo destino em vários arquivos de projeto](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md).

## <a name="common-targets-files"></a>Arquivos .targets comuns

| Arquivo *.targets* | Descrição |
|---------------------------------| - |
| *Microsoft.Common.targets* | Define as etapas no processo de build padrão de projetos [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] e [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)].<br /><br /> Importado pelos arquivos *Microsoft.CSharp.targets* e *Microsoft.VisualBasic.targets*, que incluem a seguinte instrução: `<Import Project="Microsoft.Common.targets" />` |
| *Microsoft.CSharp.targets* | Define as etapas no processo de build padrão de projetos do Visual C#.<br /><br /> Importado pelos arquivos de projeto do Visual C# (*.csproj*), que incluem a seguinte instrução: `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` |
| *Microsoft.VisualBasic.targets* | Define as etapas no processo de build padrão de projetos do Visual Basic.<br /><br /> Importado pelos arquivos de projeto do Visual Basic (*.vbproj*), que incluem a seguinte instrução: `<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />` |

## <a name="directorybuildtargets"></a>Directory.Build.targets
*Directory.Build.targets* é um arquivo definido pelo usuário que fornece personalizações a projetos em um diretório. Esse arquivo é importado automaticamente de *Microsoft.Common.targets*, a menos que a propriedade **ImportDirectoryBuildTargets** seja definida como **false**.

## <a name="see-also"></a>Consulte também
- [Elemento Import (MSBuild)](../msbuild/import-element-msbuild.md)
- [Referência do MSBuild](../msbuild/msbuild-reference.md)
- [MSBuild](../msbuild/msbuild.md)
