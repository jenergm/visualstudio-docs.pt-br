---
title: IDiaEnumSourceFiles::Clone | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Clone method
ms.assetid: 87a9a9b6-3927-4131-927c-ad95f8f098b9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 328536b64bdea2591b4ab8c242348b8304984466
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56624627"
---
# <a name="idiaenumsourcefilesclone"></a>IDiaEnumSourceFiles::Clone
Cria um enumerador que contém o mesmo estado de enumeração que o enumerador atual.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT Clone ( 
   IDiaEnumSourceFiles** ppenum
);
```

#### <a name="parameters"></a>Parâmetros
 ppenum

[out] Retorna um [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md) objeto que contém uma duplicata do enumerador. A fonte de arquivos não são duplicados, apenas o enumerador.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="see-also"></a>Consulte também
- [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)