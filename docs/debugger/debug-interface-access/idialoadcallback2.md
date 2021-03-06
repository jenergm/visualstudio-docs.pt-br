---
title: IDiaLoadCallback2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2 interface
ms.assetid: 9a44277d-cbed-4811-9bad-5a2aa0f09323
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: daf0b48aca06b404824059030052223a8545a6b0
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641449"
---
# <a name="idialoadcallback2"></a>IDiaLoadCallback2
Receber retornos de chamada do símbolo de DIA de localizar o procedimento, permitindo que as restrições a serem impostas sobre o processo de localização.

## <a name="syntax"></a>Sintaxe

```
IDiaLoadCallback2 : IDiaLoadCallback
```

## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable
 Além dos métodos na [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md) interface, essa interface expõe os métodos a seguir:

|Método|Descrição|
|------------|-----------------|
|[IDiaLoadCallback2::RestrictOriginalPathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictoriginalpathaccess.md)|Determina se procurando por um arquivo. PDB no diretório de depuração do original.|
|[IDiaLoadCallback2::RestrictReferencePathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictreferencepathaccess.md)|Determina se procurando um arquivo. PDB é permitido no caminho de onde se encontra o arquivo .exe.|
|[IDiaLoadCallback2::RestrictDBGAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictdbgaccess.md)|Determina se procurando por informações de depuração é permitido de arquivos. dbg.|
|[IDiaLoadCallback2::RestrictSystemRootAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictsystemrootaccess.md)|Determina se a procura de arquivos. PDB é permitido no diretório raiz do sistema.|

## <a name="remarks"></a>Comentários
 O aplicativo cliente implementa essa interface e fornece uma referência a ele na chamada para o [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) método. Lembre-se de implementar todos os métodos de [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md) interface também.

## <a name="requirements"></a>Requisitos
 Cabeçalho: Dia2.h

 Biblioteca: diaguids.lib

 DLL: msdia80.dll

## <a name="see-also"></a>Consulte também
- [Interfaces (SDK de Acesso à Interface de Depuração)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
- [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)