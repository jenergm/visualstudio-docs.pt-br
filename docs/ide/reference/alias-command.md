---
title: Comando Alias
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- tools.alias
helpviewer_keywords:
- aliases, Visual Studio commands
- commands, aliases
- Tools.Alias command
- command aliases
- alias command
ms.assetid: bdf857df-b5d5-450f-8c10-a6fd4dccc130
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e55b27ebc3a0a9690e04e19e53b65a7aa44834de
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55919411"
---
# <a name="alias-command"></a>Comando Alias
Cria um novo alias para um comando completo, comando e argumentos completos ou outro alias.

> [!TIP]
> Digitar `>alias` sem argumentos exibe a lista atual de aliases e suas definições.


## <a name="syntax"></a>Sintaxe

```cmd
Tools.Alias [/delete] [/reset] [aliasname] [aliasstring]
```

## <a name="arguments"></a>Arguments
 `aliasname` Opcional. O nome do novo alias. Se nenhum valor for fornecido para `aliasname`, aparecerá uma lista de aliases atuais e suas definições.

 `aliasstring` Opcional. O nome do comando completo ou alias existente e qualquer parâmetro que você quiser criar como alias. Se nenhum valor for fornecido para `aliasstring`, o nome do alias e a cadeia de caracteres de alias do alias especificado serão exibidos.

## <a name="switches"></a>Opções
 /delete, /del ou /d Opcional. Exclui o alias especificado, removendo-o do preenchimento automático.

 /reset Opcional. Redefine a lista de aliases predefinidos para suas configurações originais. Ou seja, restaura todos os aliases predefinidos e remove todos os aliases definidos pelo usuário.

## <a name="remarks"></a>Comentários
 Como aliases representam comandos, eles devem estar localizados no início da linha de comando.

 Ao emitir esse comando, você deve incluir as opções imediatamente após o comando, e não após os aliases. Caso contrário, a própria opção será incluída como parte da cadeia de caracteres de alias.

 A opção `/reset` solicita uma confirmação antes que os aliases sejam restaurados. Não há nenhuma forma abreviada de `/reset`.

## <a name="examples"></a>Exemplos
 Este exemplo cria um novo alias, `upper`, para o comando completo Edit.MakeUpperCase.

```cmd
>Tools.Alias upper Edit.MakeUpperCase
```

 Este exemplo exclui o alias `upper`.

```cmd
>Tools.alias /delete upper
```

 Este exemplo exibe uma lista de todos os aliases e definições atuais.

```cmd
>Tools.Alias
```

## <a name="see-also"></a>Consulte também

- [Comandos do Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Janela Comando](../../ide/reference/command-window.md)
- [Caixa Localizar/Comando](../../ide/find-command-box.md)
- [Aliases de comando do Visual Studio](../../ide/reference/visual-studio-command-aliases.md)