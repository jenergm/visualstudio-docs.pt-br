---
title: Threads | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5d931568258099fa4a8fe8f3b82d3fe50d5a3e35
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60099761"
---
# <a name="threads"></a>Threads
Na arquitetura do depurador, uma *thread*:

- É a unidade fundamental de computação. Um thread executa sequencialmente suas instruções dentro do contexto de uma pilha de chamadas, movimentação de contexto de um código para o próximo.

- Pode identificar em si e o programa que ele está em execução no. Threads podem ser nomeados, suspensos e retomados. Um thread também pode enumerar seus quadros de pilha associado e, em algumas condições, pode ser movido para outro quadro de pilha. Considerando o contexto de um quadro de pilha, um thread pode retornar seu thread lógico associado, se houver. Um thread tem propriedades, como uma contagem de suspensões, que pode ser exibido na **Threads** janela do IDE.

- É representado por um [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) interface, geralmente criado por um mecanismo de depuração (DES) ou a máquina virtual como consequência de um programa em execução.

## <a name="see-also"></a>Consulte também
- [Programas](../../extensibility/debugger/programs.md)
- [Quadros de pilha](../../extensibility/debugger/stack-frames.md)
- [Mecanismo de depuração](../../extensibility/debugger/debug-engine.md)
- [Conceitos do depurador](../../extensibility/debugger/debugger-concepts.md)
- [Gerenciador de sessão de depuração](../../extensibility/debugger/session-debug-manager.md)