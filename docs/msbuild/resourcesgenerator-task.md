---
title: Tarefa ResourcesGenerator | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8ef54bdc3b3c692869b4883cf4f92293551a1958
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56636314"
---
# <a name="resourcesgenerator-task"></a>Tarefa ResourcesGenerator
A tarefa <xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> insere um ou mais recursos (j *.jpg*, *.ico*, *.bmp*, [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] em formato binário e outros tipos de extensão) em um arquivo *.resources*.

## <a name="task-parameters"></a>Parâmetros de tarefa

|Parâmetro|Descrição|
|---------------|-----------------|
|`OutputPath`|Parâmetro da **cadeia de caracteres** obrigatório.<br /><br /> Especifica o caminho do diretório de saída. Se o caminho não for um caminho absoluto, ele será tratado como um caminho relativo ao diretório do projeto raiz.|
|`OutputResourcesFile`|Parâmetro de saída **ITaskItem[]** obrigatório.<br /><br /> Especifica o caminho e o nome dos arquivos *.resource* gerados. Se o caminho não for um caminho absoluto, o arquivo *.resources* será gerado em relação ao diretório raiz do projeto.|
|`ResourcesFiles`|Parâmetro obrigatório **ITaskItem[]**.<br /><br /> Especifica um ou mais recursos para ser inserido no arquivo *.resources* gerado.|

## <a name="example"></a>Exemplo
 O exemplo a seguir gera um arquivo *.resources* com um único recurso *.bmp*. O recurso *.bmp* é gerado para um diretório relativo ao diretório raiz do projeto.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="ResourcesGeneratorTask">
    <ResourcesGenerator
      ResourceFiles="Resource1.bmp"
      OutputPath="myresources"
      OutputResourcesFile="myresources\my.resources" />
  </Target>
</Project>
```

## <a name="see-also"></a>Consulte também
- [Referência do WPF MSBuild](../msbuild/wpf-msbuild-reference.md)
- [Referência de tarefas](../msbuild/wpf-msbuild-task-reference.md)
- [Referência do MSBuild](../msbuild/msbuild-reference.md)
- [Referência de tarefas](../msbuild/msbuild-task-reference.md)
- [Compilar um aplicativo WPF](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)