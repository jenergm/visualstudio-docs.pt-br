---
title: Comando Abrir Arquivo
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- file.openfile
helpviewer_keywords:
- Open File command
- File.OpenFile command
- of command
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b76db52534f4c264e065152548d49f9773863a29
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55937923"
---
# <a name="open-file-command"></a>Comando Abrir arquivo

Abre um arquivo existente e permite que você especifique um editor.

## <a name="syntax"></a>Sintaxe

```cmd
File.OpenFile filename [/e:editorname]
```

## <a name="arguments"></a>Arguments

`filename`

Necessário. O caminho total ou parcial e o nome do arquivo a abrir. Caminhos que contêm espaços devem ser colocados entre aspas.

## <a name="switches"></a>Opções

/e:`editorname`

Opcional. Nome do editor no qual o arquivo será aberto. Se o argumento for especificado, mas nenhum nome de editor for fornecido, a caixa de diálogo **Abrir com** será exibida.

A sintaxe do argumento /e:`editorname` usa os nomes de editor como eles são exibidos na Caixa de Diálogo Abrir com, entre aspas.

Por exemplo, para abrir um arquivo no editor de código-fonte, insira o seguinte para o argumento /e:`editorname`.

```cmd
/e:"Source Code (text) Editor"
```

## <a name="remarks"></a>Comentários

Conforme você digita um caminho, o preenchimento automático tenta localizar o caminho e o nome do arquivo corretos.

## <a name="example"></a>Exemplo

Este exemplo abre o arquivo de estilo "Test1.css" no editor de código-fonte.

```cmd
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"
```

## <a name="see-also"></a>Consulte também

- [Comandos do Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Janela Comando](../../ide/reference/command-window.md)
- [Janela imediata](../../ide/reference/immediate-window.md)
- [Caixa Localizar/Comando](../../ide/find-command-box.md)
- [Aliases de comando do Visual Studio](../../ide/reference/visual-studio-command-aliases.md)