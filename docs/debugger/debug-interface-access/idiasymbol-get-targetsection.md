---
title: IDiaSymbol::get_targetSection | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_targetSection method
ms.assetid: 95382395-da41-4aa8-87f1-5b03da128565
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e6e91c7b13bbc9162993a016e040c2922f6dcde7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56599398"
---
# <a name="idiasymbolgettargetsection"></a>IDiaSymbol::get_targetSection
Recupera a seção de endereço de um destino da conversão.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT get_targetSection ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parâmetros
 `pRetVal`

[out] Parte da seção de um endereço de destino da conversão.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna `S_FALSE` ou um código de erro.

> [!NOTE]
>  Um valor de retorno `S_FALSE` significa que a propriedade não está disponível para o símbolo.

## <a name="see-also"></a>Consulte também
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)