---
title: IDiaSymbol::get_frontEndBuild | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_frontEndBuild method
ms.assetid: f7dab1c6-112b-4966-baa5-afc976949c76
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 65b0fd76f05dd4e8a69122a7187d42e3eaea3a2b
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2019
ms.locfileid: "58924979"
---
# <a name="idiasymbolgetfrontendbuild"></a>IDiaSymbol::get_frontEndBuild
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Recupera o número de compilação de front-end.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT get_frontEndBuild (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pRetVal`  
 [out] Retorna o número de compilação de front-end. Consulte Observações.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna `S_FALSE` ou um código de erro.  
  
> [!NOTE]
>  Um valor de retorno `S_FALSE` significa que a propriedade não está disponível para o símbolo.  
  
## <a name="remarks"></a>Comentários  
 Normalmente, um compilador é composto de dois elementos principais: o front-end (Analisador), que manipula a análise de código-fonte em um formulário intermediário, e um back-end (gerador de código), que converte o formulário intermediário em assembly. Não é incomum para o front-end ter uma versão diferente do back-end.  
  
 Um front-end ou um número de versão de back-end é composto de três partes: \<principal >.\< secundária >. \<compilar >, onde \<principais > é o número de versão principal \<secundária > é o número de versão secundária, e \<compilar > é o número de compilação. Por exemplo, 13.10.3077.  
  
## <a name="requirements"></a>Requisitos  
  
|Requisito|Descrição|  
|-----------------|-----------------|  
|Cabeçalho:|dia2.h|  
|Versão:|DIA SDK v7.0|  
  
## <a name="see-also"></a>Consulte também  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
