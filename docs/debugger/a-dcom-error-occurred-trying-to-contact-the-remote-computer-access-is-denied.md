---
title: Ocorreu um erro de DCOM durante a tentativa de contatar o computador remoto. O acesso foi negado. | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.remote.dcom_access_denied
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, DCOM error
- remote DCOM access denied error
- DCOM, access errors
ms.assetid: 9d7dfc1b-9fe0-4f54-9c50-9c0e0f8358c5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 75d1c9f9c23df04ca19f68dada718fba12dc51f3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56622833"
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>Ocorreu um erro de DCOM durante a tentativa de contatar o computador remoto. O acesso foi negado.
Depuração remota usa DCOM para se comunicar entre os computadores locais e remotos nas seguintes situações:

- O depurador está definido como **modo de compatibilidade nativa** ou **modo de compatibilidade gerenciado** check-in a **Ferramentas > Opções > depuração** página

- Você está depurando C++ gerenciado (C + + / CLI) código.

- No Visual Studio 2013, quando **habilitar nativo editar e continuar** check-in a **Ferramentas > Opções > depuração** página

- Alguns cenários de depuração de terceiros

  Esse erro ocorre quando o processo do Visual Studio não puder se autenticar (ou as credenciais fornecidas forem julgadas insuficientes) para o processo remoto do depurador sobre DCOM. Uma ou mais das seguintes alternativas podem resolver o problema:

- Desative **modo de compatibilidade nativa** e **modo de compatibilidade gerenciado**.

- No Visual Studio 2013, desative **habilitar nativo editar e continuar**.

- Reinicializar ambos os computadores.

- Se a depuração remota exigir a inserção de credenciais, verifique a opção para salvar as credenciais.

## <a name="see-also"></a>Consulte também

- [Erros e solução de problemas de depuração remota](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Depuração remota](../debugger/remote-debugging.md)