---
title: IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 024ccd78-5867-4ca7-bc26-548758e9ac53
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 673ca8137244fed933df0be3fa0221115951a9c1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56618101"
---
# <a name="idiasymbolfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag
Dado um valor de marca correspondente, esse método retorna uma enumeração de símbolos que estão contidas nessa função stub em um endereço virtual relativo de especificado.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT findSymbolsByRVAForAcceleratorPointerTag (
   DWORD             tagValue,
   DWORD             rva,
   IDiaEnumSymbols** ppResult);
```

#### <a name="parameters"></a>Parâmetros
 `tagValue`

[in] O valor de marca de ponteiro para o qual os registros de símbolo pointee são encontrados.

 `rva`

[in] O rva é usado para filtrar os símbolos que correspondem à variável pointee com o valor de marca especificados.

 `ppResult`

[out] Um ponteiro para um `IDiaEnumSymbols` ponteiro de interface que é inicializado com o resultado.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna `S_FALSE` ou um código de erro.

## <a name="remarks"></a>Comentários
 Chame esse método somente em um `IDiaSymbol` interface que corresponde a uma função de stub do acelerador.

## <a name="see-also"></a>Consulte também
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)