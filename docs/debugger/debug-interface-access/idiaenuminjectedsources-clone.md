---
title: IDiaEnumInjectedSources::Clone | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Clone method
ms.assetid: 18038691-c140-426a-8617-27f0360650f3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bb1502c875c04955578686113d8ad491311e800d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56632557"
---
# <a name="idiaenuminjectedsourcesclone"></a>IDiaEnumInjectedSources::Clone
Cria um enumerador que contém o mesmo estado de enumeração que o enumerador atual.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT Clone ( 
   IDiaEnumInjectedSources** ppenum
);
```

#### <a name="parameters"></a>Parâmetros
 `ppenum`

[out] Retorna um [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) objeto que contém uma duplicata do enumerador. As fontes injetadas não são duplicadas, apenas o enumerador.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="see-also"></a>Consulte também
- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)