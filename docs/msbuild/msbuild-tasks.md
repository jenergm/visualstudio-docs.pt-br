---
title: Tarefas do MSBuild | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- tasks
- MSBuild, tasks
ms.assetid: 5d3cc4a7-e5db-4f73-b707-8b6882fddcf8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 90b6731cf75a1825139aba57fe8491cd7cb0253f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56642762"
---
# <a name="msbuild-tasks"></a>tarefas MSBuild
Uma plataforma de build precisa de capacidade para executar qualquer número de ações durante o processo de build. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] usa *tarefas* para executar essas ações. Uma tarefa é uma unidade de código executável usada por [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] para executar operações atômicas de build.

## <a name="task-logic"></a>Lógica da tarefa
 O formato de arquivo de projeto XML [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] não consegue executar totalmente operações de build por conta própria, então, a lógica de tarefa deve ser implementada fora do arquivo de projeto.

 A lógica de execução de uma tarefa é implementada como uma classe do .NET que implementa a interface <xref:Microsoft.Build.Framework.ITask>, que é definida no namespace <xref:Microsoft.Build.Framework>.

 A classe de tarefa também define os parâmetros de entrada e saída disponíveis para a tarefa no arquivo de projeto. Todas as propriedades públicas não estáticas e não abstratas configuráveis expostas pela classe de tarefa podem ser acessadas no arquivo de projeto colocando um atributo correspondente com o mesmo nome no elemento de [tarefa](../msbuild/task-element-msbuild.md).

 Você pode escrever sua própria tarefa por meio da criação de uma classe gerenciada que implementa a interface <xref:Microsoft.Build.Framework.ITask>. Para saber mais, confira [Produção de tarefas](../msbuild/task-writing.md).

## <a name="execute-a-task-from-a-project-file"></a>Executar uma tarefa de um arquivo de projeto
 Antes de executar uma tarefa no seu arquivo de projeto, primeiro você deve mapear o tipo no assembly que implementa a tarefa para o nome da tarefa com o elemento [UsingTask](../msbuild/usingtask-element-msbuild.md). Isso permite que [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] saiba onde procurar a lógica de execução da sua tarefa ao encontrá-la em seu arquivo de projeto.

 Para executar uma tarefa em um arquivo de projeto [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], crie um elemento com o nome da tarefa como um filho de um elemento `Target`. Se uma tarefa aceita parâmetros, eles são passados como atributos do elemento.

 As listas de item [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] e as propriedades podem ser usadas como parâmetros. Por exemplo, o código a seguir chama a tarefa `MakeDir` e define o valor da propriedade `Directories` do objeto `MakeDir` igual ao valor da propriedade `BuildDir` declarada no exemplo anterior.

```xml
<Target Name="MakeBuildDirectory">
    <MakeDir
        Directories="$(BuildDir)" />
</Target>
```

 As tarefas também podem retornar informações para o arquivo de projeto, que pode ser armazenado em itens ou propriedades para uso posterior. Por exemplo, o código a seguir chama a tarefa `Copy` e armazena as informações da propriedade de saída `CopiedFiles` na lista de itens `SuccessfullyCopiedFiles`.

```xml
<Target Name="CopyFiles">
    <Copy
        SourceFiles="@(MySourceFiles)"
        DestinationFolder="@(MyDestFolder)">
        <Output
            TaskParameter="CopiedFiles"
            ItemName="SuccessfullyCopiedFiles"/>
     </Copy>
</Target>
```

## <a name="included-tasks"></a>Tarefas incluídas
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] é fornecido com várias tarefas, como [Copiar](../msbuild/copy-task.md), que copia arquivos, [MakeDir](../msbuild/makedir-task.md), que cria diretórios e [Csc](../msbuild/csc-task.md), que compila arquivos de código-fonte [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]. Para obter uma lista completa das tarefas disponíveis e informações de uso, confira [Referência de tarefas](../msbuild/msbuild-task-reference.md).

## <a name="overridden-tasks"></a>Tarefas substituídas
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] procura por tarefas em vários locais. O primeiro local está em arquivos com a extensão *.OverrideTasks* armazenada nos diretórios do .NET Framework. As tarefas nesses arquivos substituem quaisquer outras tarefas com os mesmos nomes, incluindo tarefas no arquivo de projeto. O segundo local está nos arquivos com a extensão *.Tasks* nos diretórios do .NET Framework. Se a tarefa não for encontrada em um desses locais, a tarefa no arquivo de projeto será usada.

## <a name="see-also"></a>Consulte também
- [Conceitos do MSBuild](../msbuild/msbuild-concepts.md)
- [MSBuild](../msbuild/msbuild.md)
- [Produção de tarefas](../msbuild/task-writing.md)
- [Tarefas embutidas](../msbuild/msbuild-inline-tasks.md)