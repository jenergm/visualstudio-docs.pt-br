---
title: OPTNAMECHANGEPFN | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- OPTNAMECHANGEPFN
helpviewer_keywords:
- OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 32d173925d8970ec6be0872c8260d1d6219625fc
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56692938"
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
Essa é uma função de retorno de chamada especificada em uma chamada para o [SccSetOption](../extensibility/sccsetoption-function.md) (usando a opção `SCC_OPT_NAMECHANGEPFN`) e é usado para comunicar alterações de nome feitas pelo controle de fonte de plug-in voltar ao IDE.

## <a name="signature"></a>Assinatura

```cpp
typedef void (*OPTNAMECHANGEPFN)(
   LPVOID pvCallerData,
   LPCSTR pszOldName,
   LPCSTR pszNewName
);
```

## <a name="parameters"></a>Parâmetros
 pvCallerData

[in] Valor de usuário especificado em uma chamada anterior para o [SccSetOption](../extensibility/sccsetoption-function.md) (usando a opção `SCC_OPT_USERDATA`).

 pszOldName

[in] O nome original do arquivo.

 pszNewName

[in] O nome do arquivo foi renomeado para.

## <a name="return-value"></a>Valor retornado
 nenhuma.

## <a name="remarks"></a>Comentários
 Se um arquivo é renomeado durante uma operação de controle do código-fonte, o plug-in de controle do código-fonte pode notificar o IDE sobre a alteração de nome por meio desse retorno de chamada.

 Se o IDE não dá suporte a esse retorno de chamada, ele não chamará o [SccSetOption](../extensibility/sccsetoption-function.md) especificá-lo. Se o plug-in não suporta esse retorno de chamada, ele retornará `SCC_E_OPNOTSUPPORTED` do `SccSetOption` quando o IDE tenta definir o retorno de chamada de função.

## <a name="see-also"></a>Consulte também
- [Funções de retorno de chamada implementadas pelo IDE](../extensibility/callback-functions-implemented-by-the-ide.md)
- [SccSetOption](../extensibility/sccsetoption-function.md)