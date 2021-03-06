---
title: Folhas de estilos XSLT de edição
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 080bed0f-0ca9-4be7-aecd-6bdaebc04007
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dab4013bf3921a2af4f69d464c10d1e70f9407b3
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526198"
---
# <a name="edit-xslt-style-sheets"></a>Editar folhas de estilos XSLT

O editor XML também pode ser usado para editar folhas de estilos XSLT. Você pode tirar proveito dos recursos do editor padrão como o IntelliSense, estruturação, snippets XML, e assim por diante. Além disso, há também os novos recursos que tornam ficar em XSLT.

## <a name="xslt-features"></a>Recursos de fonte

A tabela a seguir descreve os recursos específicos para trabalhar com folhas de estilos XSLT.

**Coloração de sintaxe**

Palavras-chave XSLT, tais como `template` e `match`, são exibidos na cor da palavra-chave XSLT especificada pela **fontes e cores** configurações.

**Sublinhados ondulados**

O editor XML usa a instalada *XSLT* arquivo para validar folhas de estilos XSLT. Os erros de validação são mostrados como sublinhados ondulados azuis. O editor XML também compila a folha de estilos no plano de fundo e relata os erros de compilador ou avisos com traços ondulados apropriadas.

**Suporte para blocos de script**

O código nos blocos de script é suportado pelo depurador XSLT para que você pode definir pontos de interrupção e percorrer o código de bloco de script.

**Saída XSLT de exibição**

Você pode executar uma transformação XSL e exibir a saída do editor XML. Para obter mais informações, confira [Como: Executar uma transformação XSLT do editor XML](../xml-tools/how-to-execute-an-xslt-transformation-from-the-xml-editor.md).

**Debug XSLT**

Você pode iniciar o depurador XSLT de um arquivo XSLT no editor de XML. O depurador oferece suporte pontos de interrupção no arquivo XSLT, estado de configuração de execução XSLT de exibição, e assim por diante. Passa sobre uma variável XSLT traz anterior um ToolTip com o valor da variável. O depurador pode ser usado para depurar uma folha de estilos, ou depurar uma transformação XSL compilado chamada de outro aplicativo. Para obter mais informações, consulte [depuração XSLT](../xml-tools/debugging-xslt.md).

## <a name="see-also"></a>Consulte também

- [Editor de XML](../xml-tools/xml-editor.md)