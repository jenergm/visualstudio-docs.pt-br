---
title: 'Aviso de segurança: O depurador deve executar o comando não confiável | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.securityalert
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: e5c004b3-b364-4098-ac98-770076ca9981
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7c4ab45feeae409a1951e1a57e964eaaa5963896
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56690339"
---
# <a name="security-warning-debugger-must-execute-untrusted-command"></a>Aviso de segurança: o depurador deve executar o comando não confiável
Esta caixa de diálogo de aviso aparece quando você estiver usando o servidor de origem. Indica que o comando que o depurador precisa executar para obter o código-fonte não está na lista de comandos confiáveis para o servidor de origem contido no arquivo srcsvr.ini. Se esse for um comando válido, você poderá adicioná-lo ao arquivo srcsvr.ini. Caso contrário, você não deverá executá-lo. Para obter mais informações, consulte [Especificar arquivos de símbolo (.pdb) e de origem](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).

## <a name="message-text"></a>Mensagem de texto
 **O depurador deve executar o seguinte comando não confiável para obter o código-fonte do servidor de origem.**

 **Se o arquivo de símbolo de depuração (\*.pdb) não for de uma origem conhecida e confiável, a execução deste comando pode ser inválida ou perigosa.**

 **Você deseja executar este comando?**

## <a name="uielement-list"></a>Lista UIElement
 Comando de caixa de texto do arquivo. PDB para ser executado.

 Execução permitem que o comando a ser executado.

 Não execute parar a execução do comando e o download do arquivo do servidor de origem.

## <a name="see-also"></a>Consulte também
- [Especificar arquivos de símbolo (.pdb) e de origem](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
- [Segurança do depurador](../debugger/debugger-security.md)
- [Servidor de Origem](/windows/desktop/Debug/source-server-and-source-indexing)