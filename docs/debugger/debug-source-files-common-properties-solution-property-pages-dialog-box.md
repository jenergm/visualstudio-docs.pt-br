---
title: Caixa de diálogo de páginas de propriedade do código-fonte arquivos, propriedades comuns, solução de depuração | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.options.FindSource
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Debug Source Files property page
- debugging [Visual Studio], specifying source and symbol files
- source files, specifying in debugger
- debugger, source files
ms.assetid: 0af11464-eeb1-4d0b-87a6-0cc96779afb1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83bed0588a0959ab85906d949e1b0752396223ae
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56609703"
---
# <a name="debug-source-files-common-properties-solution-property-pages-dialog-box"></a>Caixa de diálogo Depurar Arquivos de Origem, Propriedades Comuns, Páginas de Propriedades da Solução
Esta página de propriedades especifica onde o depurador procurará arquivos de origem ao depurar a solução.

 Para acessar a página de propriedades **Depurar Arquivos de Origem**, clique com o botão direito do mouse na solução em **Gerenciador de Soluções** e selecione **Propriedades** no menu de atalho. Expanda a pasta **Propriedades Comuns** e clique na página **Depurar Arquivos de Origem**.

 **Diretórios que contêm o código-fonte** contém uma lista de diretórios em que o depurador procura por arquivos de origem ao depurar a solução. Os subdiretórios dos diretórios especificados também são pesquisados.

 **Não procurar por esses arquivos de origem** digite os nomes de todos os arquivos que você não deseja que o depurador leia. Se o depurador encontrar um desses arquivos em um dos diretórios especificados acima, ele o ignorará. Se a caixa de diálogo **Localizar Fonte** aparecer durante a depuração e você clicar em **Cancelar**, o arquivo que você procurava será adicionado a essa lista para que o depurador não continue a procurar o arquivo.

## <a name="see-also"></a>Consulte também

- [Segurança do depurador](../debugger/debugger-security.md)
- [Preparação e configurações do depurador](../debugger/debugger-settings-and-preparation.md)