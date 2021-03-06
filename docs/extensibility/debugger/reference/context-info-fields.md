---
title: CONTEXT_INFO_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CONTEXT_INFO_FIELDS
helpviewer_keywords:
- CONTEXT_INFO_FIELDS enumeration
ms.assetid: ef436bd3-738e-47e8-828c-8febce752439
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 13501c86eabd249e0e47137099862cd6db654415
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706087"
---
# <a name="contextinfofields"></a>CONTEXT_INFO_FIELDS
Especifica quais informações devem ser recuperadas sobre um contexto de memória.

## <a name="syntax"></a>Sintaxe

```cpp
enum enum_CONTEXT_INFO_FIELDS {
    CIF_MODULEURL =       0x00000001,
    CIF_FUNCTION =        0x00000002,
    CIF_FUNCTIONOFFSET =  0x00000004,
    CIF_ADDRESS =         0x00000008,
    CIF_ADDRESSOFFSET =   0x00000010,
    CIF_ADDRESSABSOLUTE = 0x00000020,
    CIF_ALLFIELDS =       0x0000003f
};
typedef DWORD CONTEXT_INFO_FIELDS;
```

```csharp
public enum enum_CONTEXT_INFO_FIELDS {
    CIF_MODULEURL =       0x00000001,
    CIF_FUNCTION =        0x00000002,
    CIF_FUNCTIONOFFSET =  0x00000004,
    CIF_ADDRESS =         0x00000008,
    CIF_ADDRESSOFFSET =   0x00000010,
    CIF_ADDRESSABSOLUTE = 0x00000020,
    CIF_ALLFIELDS =       0x0000003f
};
```

## <a name="members"></a>Membros
CIF_MODULEURL Initialize/usar o `bstrModuleUrl` campo do [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) estrutura.

CIF_FUNCTION Initialize/usar o `bstrFunction` campo do `CONTEXT_INFO` estrutura.

CIF_FUNCTIONOFFSET Initialize/usar o `posFunctionOffset` campo do `CONTEXT_INFO` estrutura.

CIF_ADDRESS Initialize/usar o `bstrAddress` campo do `CONTEXT_INFO` estrutura.

CIF_ADDRESSOFFSET Initialize/usar o `bstrAddressOffset` campo do `CONTEXT_INFO` estrutura.

CIF_ALLFIELDS Initialize/usar todos os campos do `CONTEXT_INFO` estrutura.

## <a name="remarks"></a>Comentários
Esses valores são passados a um parâmetro para o [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) método para indicar quais campos da [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) são de estrutura a ser inicializado.

Esses sinalizadores também são usados para indicar quais campos do `CONTEXT_INFO` estrutura são usados e válidos quando a estrutura é retornada.

Esses valores podem ser combinados com um OR bit a bit.

## <a name="requirements"></a>Requisitos
Header: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [Enumerações](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)
