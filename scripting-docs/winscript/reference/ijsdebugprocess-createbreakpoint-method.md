---
title: 'Método ijsdebugprocess:: Createbreakpoint | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugProcess.CreateBreakPoint
apilocation:
- jscript9diag.dll
ms.assetid: a2cb4233-2846-4d11-aa13-21de43abda9f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b398b93c2e7b5ad43abd35d385407b39c0c980f9
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152613"
---
# <a name="ijsdebugprocesscreatebreakpoint-method"></a>Método IJsDebugProcess::CreateBreakPoint
Define o ponto de interrupção na posição do documento especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT CreateBreakPoint(  
   UINT64 documentId,  
   DWORD characterOffset,  
   DWORD characterCount,  
   BOOL isEnabled,  
   IJsDebugBreakPoint **ppDebugBreakPoint  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `documentId`  
 [in] Ponteiro para IDebugDocumentText.  
  
 `characterOffset`  
 [in] Deslocamento de caractere desde o início do arquivo.  
  
 `characterCount`  
 [in] Comprimento do texto do documento dentro do qual o ponto de interrupção deve ser inserido.  
  
 `isEnabled`  
 [in] Especifica se o ponto de interrupção está habilitado.  
  
 `ppDebugBreakPoint`  
 [out] Objeto que representa o ponto de interrupção que foi criado.  
  
## <a name="return-value"></a>Valor de retorno  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** jscript9diag.h  
  
## <a name="see-also"></a>Consulte também  
 [Interface IJsDebugProcess](../../winscript/reference/ijsdebugprocess-interface.md)