---
title: IActiveScriptError | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptError interface
ms.assetid: c8e0288d-38ff-4145-a7e3-f8cdfb72eefe
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ca783e2100fe74ed05499f9611a9b8f3399817f
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144414"
---
# <a name="iactivescripterror"></a>IActiveScriptError
Um objeto que implementa essa interface é passado para o [IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md) método sempre que o mecanismo de script encontra um erro sem tratamento. O host, em seguida, chama métodos neste objeto para obter informações sobre o erro que ocorreu.  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable  
  
|Método|Descrição|  
|------------|-----------------|  
|[IActiveScriptError::GetExceptionInfo](../../winscript/reference/iactivescripterror-getexceptioninfo.md)|Recupera informações sobre o erro.|  
|[IActiveScriptError::GetSourcePosition](../../winscript/reference/iactivescripterror-getsourceposition.md)|Recupera o local no código-fonte em que ocorreu um erro.|  
|[IActiveScriptError::GetSourceLineText](../../winscript/reference/iactivescripterror-getsourcelinetext.md)|Recupera a linha no arquivo de origem em que ocorreu um erro.|  
  
## <a name="see-also"></a>Consulte também  
 [Interfaces de script ativo](../../winscript/reference/active-script-interfaces.md)