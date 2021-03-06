---
title: Microsoft Visual Studio (exceção lançada) caixa de diálogo do depurador | Microsoft Docs
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.exceptions.thrown
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Microsoft Visual Studio Debugger (Exception Thrown) dialog box
- exception handling, during debugging
- debugger, exceptions
- throwing exceptions, during debugging
ms.assetid: 1fe98d10-c8f9-4b39-a920-99169bfd542e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e1111bc7f3fbb0f515bfeb5247f70925c1ab304d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56681277"
---
# <a name="microsoft-visual-studio-debugger-exception-thrown-dialog-box"></a>Caixa de diálogo Depurador do Microsoft Visual Studio (exceção gerada)
Ocorreu uma exceção no seu programa. Esta caixa de diálogo relata o tipo de exceção lançada. Seu código precisa tratar essa exceção. Você pode escolher entre as seguintes opções para tratar a exceção:

 **Quebra** permite a execução de invadir o depurador. O manipulador de exceção não será invocado antes da interrupção. Se você continuar a partir da interrupção, o manipulador de exceção será invocado.

 **Continuar** permite que a execução continue, dando a oportunidade de lidar com a exceção do manipulador de exceção. Essa opção não está disponível para determinados tipos de exceções. **Continuar** permitirá que o aplicativo continue. Em um aplicativo nativo, ela fará com que a exceção seja relançada. Em um aplicativo gerenciado, ela fará com que o programa seja encerrado ou a exceção seja tratada por um aplicativo de hospedagem.

> [!NOTE]
>  Você não pode continuar depois de uma exceção sem tratamento em código gerenciado. A escolha de **Continuar** depois de uma exceção sem tratamento no código gerenciado faz com que a depuração pare.

 **Ignorar** permite a execução continue sem invocar o manipulador de exceção. Como o manipulador de exceção não é invocado, isso poderá resultar em outras consequências, incluindo erros e exceções adicionais. Essa opção não está disponível para determinados tipos de exceções.

## <a name="see-also"></a>Consulte também
- [Gerenciando exceções com o depurador](../debugger/managing-exceptions-with-the-debugger.md)
- [Práticas recomendadas para exceções](/dotnet/standard/exceptions/best-practices-for-exceptions)
- [Tratamento de Exceção](/cpp/windows/exception-handling-cpp-component-extensions)