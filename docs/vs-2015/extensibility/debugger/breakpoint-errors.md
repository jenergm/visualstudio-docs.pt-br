---
title: Erros de ponto de interrupção | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, errors
- debugging [Debugging SDK], breakpoint errors
- errors [Debugging SDK]
ms.assetid: 79221c6b-a924-4c8e-a778-e312e4e0c0c8
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e98dc5e4645ac67ecdf5ebb06ecf0f31510202e2
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60114686"
---
# <a name="breakpoint-errors"></a>Erros de ponto de interrupção
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

O exemplo a seguir descreve o processo quando um ponto de interrupção tenta associar ao código, mas falha:  
  
## <a name="troubleshooting-a-breakpoint-error"></a>Solução de problemas de um erro de ponto de interrupção  
  
1. O mecanismo de depuração (DES) envia uma [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) para o Gerenciador de sessão de depuração (SDM).  
  
2. As chamadas SDM [IDebugBreakpointErrorEvent2::GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) (IDebugErrorBreakpoint2 * * `ppErrorBP`) para obter o ponto de interrupção de erro.  
  
3. As chamadas SDM [IDebugErrorBreakpoint2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md) para obter o ponto de interrupção pendente do qual o ponto de interrupção de erro foi originado.  
  
4. As chamadas SDM [IDebugErrorBreakpoint2::GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) para obter a razão por que o ponto de interrupção de erro Falha ao associar.  
  
## <a name="see-also"></a>Consulte também  
 [Chamar eventos do depurador](../../extensibility/debugger/calling-debugger-events.md)
