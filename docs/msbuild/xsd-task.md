---
title: Tarefa XSD | Microsoft Docs
ms.date: 06/27/2018
ms.topic: reference
f1_keywords:
- vc.task.xsd
- VC.Project.VCXMLDataGeneratorTool.Namespace
- VC.Project.VCXMLDataGeneratorTool.GenerateFromSchema
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XSD task (MSBuild (Visual C++))
- MSBuild (Visual C++), XSD task
ms.assetid: 15c99f5c-7124-4bbc-bc03-70c7bcce8893
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 742b2b1660b5a1776edca0a4b64c56222cd1c163
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62777633"
---
# <a name="xsd-task"></a>tarefa XSD
Encapsula a ferramenta de definição de esquema XML (*xsd.exe*), a qual gera arquivos de classe ou de esquema com base em uma origem.

> [!NOTE]
> A partir do Visual Studio 2017, o suporte a projetos em C++ para *xsd.exe* foi preterido. Você ainda pode usar as APIs **Microsoft.VisualC.CppCodeProvider** manualmente adicionando *CppCodeProvider.dll* ao cache de assembly global.

## <a name="parameters"></a>Parâmetros
 A tabela a seguir descreve os parâmetros da tarefa **XSD**.

- **AdditionalOptions**

     Parâmetro **String** opcional.

     Uma lista de opções, conforme especificado na linha de comando. Por exemplo, /\<option1> /\<option2> /\<option#>. Use esse parâmetro para especificar opções não representadas por nenhum outro parâmetro da tarefa **XSD**.

- **GenerateFromSchema**

     Parâmetro **String** opcional.

     Especifica os tipos gerados com base no esquema especificado.

     Especifique um dos valores a seguir, cada um dos quais correspondente a uma opção XSD.

    - **classes** - **/classes**

    - **dataset** - **/dataset**

- **Linguagem**

     Parâmetro **String** opcional.

     Especifica a linguagem de programação a ser usada para o código gerado.

     Escolha **CS** (C#, que é o padrão), **VB** (Visual Basic) ou **JS** (JScript). Você também pode especificar um nome totalmente qualificado para uma classe que implementa `System.CodeDom.Compiler.CodeDomProvider Class`

- **Namespace**

     Parâmetro **String** opcional.

     Especifica o namespace de tempo de execução para os tipos gerados.

- **Sources**

     Parâmetro `ITaskItem[]` obrigatório.

     Define uma matriz de itens de arquivo de origem do MSBuild que pode ser consumida e emitida por tarefas.

- **SuppressStartupBanner**

     Parâmetro **Boolean** opcional.

     Se `true`, impedirá a exibição da mensagem de direitos autorais e de número de versão quando a tarefa for iniciada.

- **TrackerLogDirectory**

     Parâmetro **String** opcional.

     Especifica o diretório do log de rastreamento.

## <a name="see-also"></a>Consulte também
- [Referência de tarefas](../msbuild/msbuild-task-reference.md)