---
title: IDiaSourceFile::get_checksumType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksumType method
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 35e5719d285e9e99e5f7429685fa04a2c6d7f3ab
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56646389"
---
# <a name="idiasourcefilegetchecksumtype"></a>IDiaSourceFile::get_checksumType
Recupera o tipo de soma de verificação.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT get_checksumType ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parâmetros
 `pRetVal`

[out] Retorna o tipo de soma de verificação.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
 O tipo de soma de verificação é um valor que pode ser mapeado para um algoritmo de soma de verificação. Por exemplo, o formato de arquivo PDB padrão normalmente pode ter um dos seguintes valores:

|Tipo de soma de verificação|Rótulo de CryptoAPI|Descrição|
|-------------------|---------------------|-----------------|
|0|\<nenhum>|Soma de verificação não presente.|
|1|`CALG_MD5`|soma de verificação gerada com o algoritmo de hash MD5.|
|2|`CALG_SHA1`|soma de verificação gerada com o algoritmo de hash SHA1.|

 O `CryptoAPI` rótulos são do `ALG_ID` enumeração. Para obter mais informações sobre algoritmos de hash, consulte o `CryptoAPI` seção do Microsoft [!INCLUDE[winsdkshort](../../debugger/debug-interface-access/includes/winsdkshort_md.md)].

 Para obter os bytes da soma de verificação atual para o arquivo de origem, chame o [idiasourcefile:: Get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md) método.

## <a name="see-also"></a>Consulte também
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)