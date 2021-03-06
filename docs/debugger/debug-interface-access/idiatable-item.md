---
title: 'Idiatable:: item | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable::Item method
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1d8070acfa254ae26e017a0070a21884309bc4d7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56616333"
---
# <a name="idiatableitem"></a>IDiaTable::Item
Recupera uma referência para a entrada especificada na tabela.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT Item ( 
   DWORD      index,
   IUnknown** element
);
```

#### <a name="parameters"></a>Parâmetros
 `index`

[in] O índice da entrada da tabela no intervalo de 0 a `count`-1, onde `count` é retornado pelo [idiatable:: Get_count](../../debugger/debug-interface-access/idiatable-get-count.md)método.

 `element`

[out] Retorna um `IUnknown` objeto que representa a entrada da tabela especificada.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
 Uma tabela representa uma coleção de objetos. Dependendo desses objetos, o parâmetro de elemento pode ser convertido para a interface apropriada. Por exemplo, se uma tabela contiver [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) objetos, em seguida, o parâmetro de elemento pode ser convertido para o `IDiaSegment` interface.

 É uma abordagem mais comum para chamar o `QueryInterface` método na [IDiaTable](../../debugger/debug-interface-access/idiatable.md) interface para a interface de enumerador apropriado e usar métodos de específicos do enumerador para acessar o conteúdo da tabela. Consulte a [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) interface para obter um exemplo.

## <a name="see-also"></a>Consulte também
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)
- [IDiaTable::get_Count](../../debugger/debug-interface-access/idiatable-get-count.md)
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)
- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)