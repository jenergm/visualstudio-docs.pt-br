---
title: IDiaEnumInjectedSources::Item | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Item method
ms.assetid: 14846955-7270-451d-91d2-9cb34bb65187
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2fd803520a6b6bb58679dd30dbf913450ce6066a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56636260"
---
# <a name="idiaenuminjectedsourcesitem"></a>IDiaEnumInjectedSources::Item
Recupera uma fonte injetada por meio de um índice.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT Item ( 
   DWORD                index,
   IDiaInjectedSource** injectedSource
);
```

#### <a name="parameters"></a>Parâmetros
 índice

[in] Índice do [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) objeto a ser recuperado. O índice é o intervalo de 0 a `count`-1, onde `count` é retornado pelo [idiaenuminjectedsources:: Get_count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md) método.

 injectedSource

[out] Retorna um [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) objeto que representa a origem injetada.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="see-also"></a>Consulte também
- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)
- [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)