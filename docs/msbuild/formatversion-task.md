---
title: Tarefa FormatVersion | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cc1651ae769a9dbe8ef8fbd9b8a1a50dd83ea0f6
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640708"
---
# <a name="formatversion-task"></a>Tarefa FormatVersion
Acrescenta o número de revisão ao número de versão.

-   Caso 1: Input: Version=\<undefined>;  Revision=\<don't care>;   Output: OutputVersion="1.0.0.0"

-   Caso 2: Input: Version="1.0.0.*"  Revision="5"  Output: OutputVersion="1.0.0.5"

-   Caso 3: Input: Version="1.0.0.0"  Revision=\<don't care>;  Output: OutputVersion="1.0.0.0"

## <a name="parameters"></a>Parâmetros
 A tabela a seguir descreve os parâmetros da tarefa `FormatVersion`.

|Parâmetro|Descrição|
|---------------|-----------------|
|`FormatType`|Parâmetro `String` opcional.<br /><br /> Especifica o tipo do formato.<br /><br /> -"Versão" = versão.<br />-   "Path" = substituir "." por "_";|
|`OutputVersion`|Parâmetro de saída `String` opcional.<br /><br /> Especifica a versão de saída que inclui o número de revisão.|
|`Revision`|Parâmetro `Int32` opcional.<br /><br /> Especifica a revisão a ser acrescentada à versão.|
|`Version`|Parâmetro `String` opcional.<br /><br /> Especifica a cadeia de caracteres do número de versão para o formato.|

## <a name="remarks"></a>Comentários
 Além de ter os parâmetros listados acima, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Tasks.TaskExtension>, que herda da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, confira [Classe base TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Consulte também
- [Tarefas](../msbuild/msbuild-tasks.md)
- [Referência de tarefas](../msbuild/msbuild-task-reference.md)