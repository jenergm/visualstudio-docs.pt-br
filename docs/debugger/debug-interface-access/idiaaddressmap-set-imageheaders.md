---
title: IDiaAddressMap::set_imageHeaders | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 10835f422f8d2d116234eadd91da0d27c424f314
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635937"
---
# <a name="idiaaddressmapsetimageheaders"></a>IDiaAddressMap::set_imageHeaders
Conjuntos de cabeçalhos para habilitar a conversão de endereço virtual relativo de imagem.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT set_imageHeaders ( 
   DWORD cbData,
   BYTE  data[],
   BOOL  originalHeaders
);
```

#### <a name="parameters"></a>Parâmetros
 cbData

[in] Número de bytes de dados de cabeçalho. Deve ser `n*sizeof(IMAGE_SECTION_HEADER)` onde `n` é o número de cabeçalhos de seção no executável.

 data[]

[in] Uma matriz de `IMAGE_SECTION_HEADER` estruturas a ser usado como o cabeçalho de imagem.

 originalHeaders

[in] Definido como `FALSE` se os cabeçalhos de imagem forem da nova imagem, `TRUE` se eles refletem a imagem original antes de um upgrade. Normalmente, isso seria definido como `TRUE` apenas em combinação com chamadas para o [idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) método.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
 O `IMAGE_SECTION_HEADER` estrutura é declarada em Winnt. h e representa o formato de cabeçalho de seção de imagem do executável.

 Dependem de cálculos de endereço virtual relativo a `IMAGE_SECTION_HEADER` valores. Normalmente, o DIA recupera esses do arquivo de banco de dados (. PDB) do programa. Se esses valores estiverem ausentes, o DIA não consegue calcular endereços virtuais e o [idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) retorno do método `FALSE`. O cliente deve, em seguida, chamar o [idiaaddressmap:: Put_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) método para habilitar os cálculos de endereço virtual relativo depois de fornecer os cabeçalhos de imagem ausentes da imagem em si.

## <a name="see-also"></a>Consulte também
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
- [IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)
- [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)