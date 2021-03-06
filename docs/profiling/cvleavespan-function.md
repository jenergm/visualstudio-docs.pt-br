---
title: Função CvLeaveSpan | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvLeaveSpan
helpviewer_keywords:
- CvLeaveSpan method
ms.assetid: 3bf65fdf-a471-4efd-ac7a-03e701bbae5d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 776c24777403b9d88de31e11d0c28fe104666600
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56639161"
---
# <a name="cvleavespan-function"></a>Função CvLeaveSpan
Marca o fim do intervalo.

## <a name="syntax"></a>Sintaxe

```C
HRESULT CvLeaveSpan(
   _In_ PCV_SPAN pSpan
);
```

#### <a name="parameters"></a>Parâmetros
 `pSpan` Objeto de período retornado pela chamada anterior a CvEnterSpan*. Não pode ser NULL.

## <a name="return-value"></a>Valor de retorno
 S_OK quando a mensagem é gravada com êxito. Código de erro em caso de erros. Use as macros SUCCEEDED/FAILED para verificar a condição de erro.

## <a name="requirements"></a>Requisitos
 **Cabeçalho:** *cvmarkers.h*

## <a name="see-also"></a>Consulte também
- [Referência de biblioteca C++](../profiling/cpp-library-reference.md)