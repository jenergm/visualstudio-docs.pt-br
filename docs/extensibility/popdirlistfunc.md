---
title: POPDIRLISTFUNC | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 259ada240d81b87d2d36e12cddcc28efe8d893f1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56696279"
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
Essa é uma função de retorno de chamada fornecida para o [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) função para atualizar uma coleção de diretórios e (opcionalmente) os nomes de arquivo para descobrir que estão sob controle do código-fonte.

 O `POPDIRLISTFUNC` retorno de chamada deve ser chamado somente para os diretórios e os nomes de arquivo (na lista fornecida para o `SccPopulateDirList` função) que, na verdade, estão sob controle do código-fonte.

## <a name="signature"></a>Assinatura

```cpp
typedef BOOL (*POPDIRLISTFUNC)(
   LPVOID pvCallerData,
   BOOL bFolder,
   LPCSTR lpDirectoryOrFileName
);
```

## <a name="parameters"></a>Parâmetros
 pvCallerData

[in] Valor de usuário atribuído ao [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md).

 bFolder

[in] `TRUE` se o nome no `lpDirectoryOrFileName` é um diretório; caso contrário, o nome é um nome de arquivo.

 lpDirectoryOrFileName

[in] Caminho do local completo para um nome de diretório ou arquivo que está sob controle do código-fonte.

## <a name="return-value"></a>Valor retornado
 O IDE retorna um código de erro apropriado:

|Valor|Descrição|
|-----------|-----------------|
|SCC_OK|Continue o processamento.|
|SCC_I_OPERATIONCANCELED|Pare o processamento.|
|SCC_E_xxx|Qualquer erro de controle de origem apropriado deve parar o processamento.|

## <a name="remarks"></a>Comentários
 Se o `fOptions` parâmetro do `SccPopulateDirList` função contiver o `SCC_PDL_INCLUDEFILES` sinalizar e, em seguida, a lista conterá, possivelmente, nomes de arquivo, bem como os nomes de diretório.

## <a name="see-also"></a>Consulte também
- [Funções de retorno de chamada implementadas pelo IDE](../extensibility/callback-functions-implemented-by-the-ide.md)
- [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)
- [Códigos de erro](../extensibility/error-codes.md)