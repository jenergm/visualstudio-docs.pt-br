---
title: IDebugDocumentHelper::AddDeferredText | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.AddDeferredText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::AddDeferredText
ms.assetid: 9463cfb0-76cc-45ee-b32c-f37dce2b2e0e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1219543c438c79ad1add068262d9556dd2d7ce8
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58159329"
---
# <a name="idebugdocumenthelperadddeferredtext"></a>IDebugDocumentHelper::AddDeferredText
Notifica o auxiliar que o texto especificado está disponível, mas ele não fornece os caracteres.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT AddDeferredText(  
   ULONG  cChars,  
   DWORD  dwTextStartCookie  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `cChars`  
 [in] Número de caracteres (Unicode) para adicionar.  
  
 `dwTextStartCookie`  
 [in] Cookie definido pelo host que representa a posição inicial do texto.  
  
## <a name="return-value"></a>Valor de retorno  
 O método retorna um `HRESULT`. Os possíveis valores incluem, mas sem limitação, aqueles na tabela a seguir.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|`S_OK`|O método foi bem-sucedido.|  
|`E_FAIL`|O método falhou.|  
  
## <a name="remarks"></a>Comentários  
 Esse método permite que o host adiar a fornecer os caracteres para adicionar até que sejam necessários, enquanto permite que o auxiliar gerar notificações precisas e informações de tamanho. O `dwTextStartCookie` parâmetro é um cookie, definido pelo host, que representa a posição inicial do texto. As chamadas subsequentes para `IDebugDocumentText::GetText` deve fornecer esse cookie. Por exemplo, em um host que representa o texto em DBCS, o cookie pode ser um deslocamento de bytes.  
  
 Supõe-se que uma única chamada para `IDebugDocumentText::GetText` pode obter caracteres de várias chamadas para `AddDeferredText`. Classes auxiliares também podem solicitar mais de uma vez para o mesmo intervalo de caracteres adiadas.  
  
> [!NOTE]
>  Chamadas para `AddDeferredText` não devem ser misturadas a chamadas para `AddUnicodeText` ou `AddDBCSText`. Se isso ocorrer, `E_FAIL` será retornado.  
  
## <a name="see-also"></a>Consulte também  
 [Interface IDebugDocumentHelper](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)   
 [IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)