---
title: Programas | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], programs
- programs, debugging
ms.assetid: e1f955d8-95da-493b-837e-e97741a26d7e
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9070b33c7522cdc13fd6217956fcab72cd83f8d1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60069427"
---
# <a name="programs"></a>Programas
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Em termos de arquitetura do depurador, uma **programa**:  
  
- É um contêiner para um conjunto de threads e um conjunto de módulos. Um programa não tem nenhum analogia única no sistema operacional Windows.  
  
     Um programa é um tipo de subprocesso. Por exemplo, quando você estiver depurando um site da Web, um script pode ser visto como um programa. Enquanto um script é executado no processo de mecanismo de script, independente dos outros scripts, ele também tem seu próprio conjunto de threads. Um mecanismo de depuração (DES) anexa a um programa e não a um processo ou um thread.  
  
- Pode identificar em si e o processo que ele está em execução no e pode ser anexado para ser desanexado do e descrever o DE que o criou, se houver. Um programa pode executar, interromper, continuar e ser encerrada.  
  
- Pode enumerar todos os seus threads. Um programa também pode fornecer seu próprio fluxo de desmontagem e pode enumerar todos os contextos de código da posição de um determinado documento.  
  
- É representado por um [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) interface, criada antes que o programa está anexado, ou como parte do processo de anexação, dependendo da implementação. Quando uma porta enumera os programas de um processo, cada programa é criado de acordo com um correspondente [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) interface é passada como um argumento para [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Embora os mecanismos de depuração também criar `IDebugProgram2` interfaces para representar os programas, esses programas não são criadas de acordo com um nó de programa. O `IDebugProgramNode2` interfaces criados por um DE são usados para depuração real, enquanto os criados por uma porta são usados apenas para descobrir quais programas estão em execução em um processo.  
  
## <a name="see-also"></a>Consulte também  
 [Processos](../../extensibility/debugger/processes.md)   
 [Nós de programa](../../extensibility/debugger/program-nodes.md)   
 [Módulos](../../extensibility/debugger/modules.md)   
 [Conceitos do depurador](../../extensibility/debugger/debugger-concepts.md)   
 [Mecanismo de depuração](../../extensibility/debugger/debug-engine.md)   
 [Posição do documento](../../extensibility/debugger/document-position.md)   
 [Contexto de código](../../extensibility/debugger/code-context.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)
