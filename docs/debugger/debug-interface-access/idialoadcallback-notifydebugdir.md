---
title: IDiaLoadCallback::NotifyDebugDir | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::NotifyDebugDir method
ms.assetid: bd04e2f6-0dbf-4742-a556-96f2cd99aa19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ce251da3c1cb7b1da00971d46cc0801ad24b8985
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56600809"
---
# <a name="idialoadcallbacknotifydebugdir"></a>IDiaLoadCallback::NotifyDebugDir
Chamado quando um diretório de depuração foi encontrado no arquivo .exe.

## <a name="syntax"></a>Sintaxe

```C++
HRESULT NotifyDebugDir ( 
   BOOL  fExecutable,
   DWORD cbData,
   BYTE  data[]
);
```

#### <a name="parameters"></a>Parâmetros
 `fExecutable`

[in] `TRUE` se o diretório de depuração é lido a partir de um executável (em vez de um arquivo. dbg).

 `cbData`

[in] Contagem de bytes de dados no diretório de depuração.

 `data[]`

[in] Uma matriz que é preenchida com o diretório de depuração.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro. O código de retorno normalmente é ignorado.

## <a name="remarks"></a>Comentários
 O [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) método invoca esse retorno de chamada quando ele encontra um diretório de depuração ao processar o arquivo executável.

 Esse método remove a necessidade do cliente para o arquivo executável e/ou a depuração de engenharia reversa para dar suporte a informações de depuração que não seja encontrado no arquivo. PDB. Com esses dados, o cliente pode reconhecer o tipo de informações de depuração disponíveis e se ele reside no arquivo executável ou o arquivo. dbg.

 A maioria dos clientes não precisarão esse retorno de chamada porque o `IDiaDataSource::loadDataForExe` método transparentemente abre os arquivos. PDB e. dbg quando necessário, para servir de símbolos.

## <a name="see-also"></a>Consulte também
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)