---
title: Envio de eventos | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 98247b894d2db628d508713875ba0ea7d0642729
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58926998"
---
# <a name="sending-events"></a>Enviando eventos
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

O mecanismo de comunicação entre o depurador e o mecanismo de depuração (DES) é um modelo de evento com base no DCOM. Os eventos são enviados como objetos COM, e cada evento tem parâmetros que especificam o seguinte:  
  
- O DE que o evento de chamada.  
  
- Uma descrição do que aconteceu.  
  
- O processo, programa e informações de thread que identifica o contexto de onde o evento ocorreu. O processo não é enviado para eventos enviados a partir DE.  
  
- O tipo de evento que indica se o evento é síncrona ou assíncrona.  
  
  Todos os eventos de depuração são enviados usando o método [IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="in-this-section"></a>Nesta seção  
 [Event Sources](../../extensibility/debugger/event-sources-visual-studio-sdk.md)  
 Explica as duas fontes de eventos: o mecanismo de depuração (DE) e a sessão de depuração do SDM (Gerenciador).  
  
 [Tipos de eventos com suporte](../../extensibility/debugger/supported-event-types.md)  
 Discute os tipos de eventos com suporte no momento: síncrono e assíncrono.  
  
 [Descrição do evento](../../extensibility/debugger/event-descriptions.md)  
 Define os eventos e os motivos para seu uso.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Criar um mecanismo de depuração personalizado](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Descreve como a DE funciona com o sistema operacional ou interpretador para fornecer serviços de depuração.
