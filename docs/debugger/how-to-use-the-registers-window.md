---
title: Modo de exibição dos valores de registro no depurador | Microsoft Docs
ms.custom: seodec18
ms.date: 11/19/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.registers
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- registers, debugging
- register contents
- flags, Registers window
- register groups
- debugging [Visual Studio], Registers window
- Registers window
ms.assetid: 2918ffa2-562f-40d6-9053-ef321bbeb767
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: afcada407060af2072e3cf1c30e86153762890b5
ms.sourcegitcommit: 847d192013eb8225776243045c9b5a53d1ba4a59
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2019
ms.locfileid: "59584383"
---
# <a name="view-register-values-in-the-registers-window-c-c-visual-basic-f"></a>Valores de registro de modo de exibição na janela de registros (C#, C++, Visual Basic, F#)

O **registra** janela exibe conteúdo do registro durante a depuração do Visual Studio. Para obter uma introdução aos conceitos por trás de registros de alto nível e o **registra** janela, consulte [Noções básicas de depuração: Janela de registros](../debugger/debugging-basics-registers-window.md).

> [!NOTE]
> Informações de registro não estão disponíveis para aplicativos SQL ou script.

Durante a depuração, registre alterações de valores como o código é executado em seu aplicativo. Valores que foram alterados recentemente são exibidos em vermelho na **registra** janela.

Para reduzir a desordem, a janela **Registros** organiza registros em grupos, que variam de acordo com a plataforma e o tipo de processador. Você pode exibir ou ocultar grupos de registros. Para obter mais informações, confira [Como: Exibir e ocultar grupos de registros](../debugger/how-to-display-and-hide-register-groups.md).

Para obter informações sobre os sinalizadores de você ver a **registra** janela, consulte [sobre registra a janela](../debugger/debugging-basics-registers-window.md)

Você pode editar valores do registro. Para obter mais informações, confira [Como: Editar um valor de registro](../debugger/how-to-edit-a-register-value.md).

**Para abrir a janela registros**

1. Habilitar depuração no nível do endereço, selecionando **habilitar a depuração do nível de endereços** na **ferramentas** (ou **depurar**) > **opções**  >  **Depuração**.

1. Durante a depuração em execução ou em um ponto de interrupção, selecione **Debug** > **Windows** > **registra**, ou pressione **Alt** + **5**.

>[!NOTE]
>Caixas de diálogo e comandos de menu podem ser diferentes dependendo da sua edição do Visual Studio ou configurações. Para alterar suas configurações, selecione **Import and Export Settings** no Visual Studio **ferramentas** menu. Para obter mais informações, confira [Redefinir as configurações](../ide/environment-settings.md#reset-settings).

### <a name="see-also"></a>Consulte também

- [Noções básicas de depuração: Janela Registros](../debugger/debugging-basics-registers-window.md)
- [Exibição de dados no depurador](../debugger/viewing-data-in-the-debugger.md)
