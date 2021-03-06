---
title: ISimpleConnectionPoint Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ISimpleConnectionPoint interface
ms.assetid: f632a82f-942d-4291-963e-e9fa2b162493
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d18c8f9eef6ddb1a38473eb19984bd9cf7dbd96
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58146923"
---
# <a name="isimpleconnectionpoint-interface"></a>Interface ISimpleConnectionPoint
Fornece uma maneira simples para descrever e enumerar os eventos acionados em um ponto de conexão específico. Essa interface também torna mais fácil conectar um `IDispatch` objeto para esses eventos. Essa interface é implementada pelo processo de depuração PDM (Gerenciador de) e consumida por mecanismos de script.  
  
 Esta interface está disponível no `IDebugHelper::CreateSimpleConnectionPoint`.  
  
 Além dos métodos herdados de `IUnknown`, o `ISimpleConnectionPoint` interface expõe os métodos a seguir.  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable  
  
|Método|Descrição|  
|------------|-----------------|  
|[ISimpleConnectionPoint::Advise](../../winscript/reference/isimpleconnectionpoint-advise.md)|Estabelece uma conexão entre o objeto de ponto de conexão simples e o coletor do cliente.|  
|[ISimpleConnectionPoint::DescribeEvents](../../winscript/reference/isimpleconnectionpoint-describeevents.md)|Retorna o DISPID e o nome para cada evento em um intervalo especificado de eventos.|  
|[ISimpleConnectionPoint::GetEventCount](../../winscript/reference/isimpleconnectionpoint-geteventcount.md)|Retorna o número de eventos expostos nesta interface.|  
|[ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)|Encerra uma conexão de consultoria estabelecida anteriormente por meio de `ISimpleConnectionPoint::Advise`.|  
  
## <a name="see-also"></a>Consulte também  
 [Interface IDebugProperty](../../winscript/reference/idebugproperty-interface.md)