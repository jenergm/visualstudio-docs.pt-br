---
title: Enumerador de código de comando | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command code enumerator
- source control plug-ins, command code enumeration
ms.assetid: 5d2c360c-59e4-4da8-bcb4-dd07c7441e40
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ddb2e88db15d60731bc17fcc60cb69772779f14e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718411"
---
# <a name="command-code-enumerator"></a>Enumerador de código de comando
Este enumerador é usado nas opções para o [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) e o [SccPopulateList](../extensibility/sccpopulatelist-function.md)para indicar o comando para o qual as opções são especificadas.

## <a name="syntax"></a>Sintaxe

```
enum SCCCOMMAND {
   SCC_COMMAND_GET,
   SCC_COMMAND_CHECKOUT,
   SCC_COMMAND_CHECKIN,
   SCC_COMMAND_UNCHECKOUT,
   SCC_COMMAND_ADD,
   SCC_COMMAND_REMOVE,
   SCC_COMMAND_DIFF,
   SCC_COMMAND_HISTORY,
   SCC_COMMAND_RENAME,
   SCC_COMMAND_PROPERTIES,
   SCC_COMMAND_OPTIONS
};
```

## <a name="members"></a>Membros
SCC_COMMAND_GET corresponde do [SccGet](../extensibility/sccget-function.md).

SCC_COMMAND_CHECKOUT corresponde do [SccCheckout](../extensibility/scccheckout-function.md).

SCC_COMMAND_CHECKIN corresponde do [SccCheckin](../extensibility/scccheckin-function.md).

SCC_COMMAND_UNCHECKOUT corresponde do [SccUncheckout](../extensibility/sccuncheckout-function.md).

SCC_COMMAND_ADD corresponde do [SccAdd](../extensibility/sccadd-function.md).

SCC_COMMAND_REMOVE corresponde do [SccRemove](../extensibility/sccremove-function.md).

SCC_COMMAND_DIFF corresponde do [SccDiff](../extensibility/sccdiff-function.md).

SCC_COMMAND_HISTORY corresponde do [SccHistory](../extensibility/scchistory-function.md).

SCC_COMMAND_RENAME corresponde do [SccRename](../extensibility/sccrename-function.md).

SCC_COMMAND_PROPERTIES corresponde do [SccProperties](../extensibility/sccproperties-function.md).

SCC_COMMAND_OPTIONS corresponde do [SccSetOption](../extensibility/sccsetoption-function.md).

## <a name="see-also"></a>Consulte também
- [Plug-ins de controle de origem](../extensibility/source-control-plug-ins.md)
- [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)
- [SccPopulateList](../extensibility/sccpopulatelist-function.md)
