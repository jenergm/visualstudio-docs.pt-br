---
title: Tarefa UpdateManifest | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, UpdateManifest task
- UpdateManifest task [MSBuild]
ms.assetid: 1291fd33-b89e-4e15-8fb1-69f9625cf2d2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0dd2ddfdbe784a45badfd0138b41b1f5dbff8ec7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641059"
---
# <a name="updatemanifest-task"></a>Tarefa UpdateManifest
Atualiza as propriedades selecionadas em um manifesto e assina-as novamente.

## <a name="parameters"></a>Parâmetros
 A tabela a seguir descreve os parâmetros da tarefa `UpdateManifest`.

|Parâmetro|Descrição|
|---------------|-----------------|
|`ApplicationManifest`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem> obrigatório.<br /><br /> Especifica o manifesto do aplicativo.|
|`ApplicationPath`|Parâmetro `String` obrigatório.<br /><br /> Especifica o caminho do manifesto do aplicativo.|
|`InputManifest`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem> obrigatório.<br /><br /> Especifica o manifesto a atualizar.|
|`OutputManifest`|Parâmetro de saída <xref:Microsoft.Build.Framework.ITaskItem> opcional.<br /><br /> Especifica o manifesto que contém propriedades atualizadas.|

## <a name="remarks"></a>Comentários
 Além de ter os parâmetros listados na tabela, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, confira [Classe base Task](../msbuild/task-base-class.md).

## <a name="see-also"></a>Consulte também
- [Tarefas](../msbuild/msbuild-tasks.md)
- [Referência de tarefas](../msbuild/msbuild-task-reference.md)