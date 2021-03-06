---
title: IDiaPropertyStorage::ReadLONG | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadLONG
ms.assetid: 32054cbc-db55-4513-a1b4-de80e77aac8a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2fb277368e23cf51a4d3d3b69226ee6bf093d6c3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56615566"
---
# <a name="idiapropertystoragereadlong"></a>IDiaPropertyStorage::ReadLONG
Lê `LONG` valores em um conjunto de propriedades.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT ReadDLONG ( 
   PROPID id,
   LONG*  pValue
);
```

#### <a name="parameters"></a>Parâmetros
 `id`

[in] Identificador da propriedade a ser lido (`PROPID` é definido em wtypes. H como um `ULONG`).

 `pValue`

[out] Retorna o valor da propriedade.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retornará um código de erro. Retorna `E_INVALIDARG` se a propriedade não é do tipo `LONG`.

## <a name="remarks"></a>Comentários
 Um `LONG` é definido pelo Windows como um inteiro com sinal de 32 bits.

## <a name="see-also"></a>Consulte também
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)