---
title: IDiaSymbol::get_isLTCG | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isLTCG method
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b674e99bcb9bd621808b080fffa6873f96cfb707
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611783"
---
# <a name="idiasymbolgetisltcg"></a>IDiaSymbol::get_isLTCG
Recupera um sinalizador que especifica se o [Compiland](../../debugger/debug-interface-access/compiland.md) foi vinculada com a opção de vinculador [/LTCG (geração de código Link-time)](/cpp/build/reference/ltcg-link-time-code-generation), que auxilia na otimização de todo o programa. Essa opção se aplica apenas ao código gerenciado.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT get_iSLTCG(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>Parâmetros
 pFlag

[out] Retorna `TRUE` se o `compiland` foi vinculado com a opção de vinculador /LTCG; caso contrário, retornará `FALSE`.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna `S_FALSE` ou um código de erro.

> [!NOTE]
>  Um valor de retorno `S_FALSE` significa que a propriedade não está disponível para o símbolo.

## <a name="requirements"></a>Requisitos

|Requisito|Descrição|
|-----------------|-----------------|
|Cabeçalho:|dia2.h|
|Versão:|V DIA SDK 8.0|

## <a name="see-also"></a>Consulte também
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)