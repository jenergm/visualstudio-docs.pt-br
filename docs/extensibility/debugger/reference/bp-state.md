---
title: BP_STATE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_STATE
helpviewer_keywords:
- BP_STATE enumeration
ms.assetid: 08aa6a3f-3e5f-4c83-8eca-7b7b5f8e208d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4117b3cb92eef555d5ed9a6c3e829fb3302924ae
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709246"
---
# <a name="bpstate"></a>BP_STATE
Especifica a existência de um ponto de interrupção associada e também especifica se ele está habilitado.

## <a name="syntax"></a>Sintaxe

```cpp
enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
typedef DWORD BP_STATE;
```

```csharp
public enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
```

## <a name="members"></a>Membros
BPS_NONE Especifica que nenhum ponto de interrupção existe.

BPS_DELETED Especifica que o ponto de interrupção foi excluído.

BPS_DISABLED Especifica que o ponto de interrupção está desabilitado.

BPS_ENABLED Especifica que o ponto de interrupção está habilitado.

## <a name="remarks"></a>Comentários
Retornado do [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md) método.

## <a name="requirements"></a>Requisitos
Header: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [Enumerações](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)
