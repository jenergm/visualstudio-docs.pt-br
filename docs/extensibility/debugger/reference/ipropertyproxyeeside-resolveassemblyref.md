---
title: IPropertyProxyEESide::ResolveAssemblyRef | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::ResolveAssemblyRef
helpviewer_keywords:
- IPropertyProxyEESide::ResolveAssemblyRef
ms.assetid: 662ca0a6-dad0-4c00-a718-bb3bbc5bd9da
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3294c19455b5ddf36ebecff52dab4908be84afab
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56681407"
---
# <a name="ipropertyproxyeesideresolveassemblyref"></a>IPropertyProxyEESide::ResolveAssemblyRef
Determina o local da referência de assembly gerenciado especificado.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT ResolveAssemblyRef(
   BSTR*                  assemName,
   IEEDataStorage**       assemBytes,
   IEEDataStorage**       assemPdb,
   BSTR*                  assemLocation,
   ASSEMBLYLOCRESOLUTION* alr
);
```

```csharp
int ResolveAssemblyRef(
   ref string                     assemName,
   out IEEDataStorage             assemBytes,
   out IEEDataStorage             assemPdb,
   out string                     assemLocation,
   out enum_ASSEMBLYLOCRESOLUTION alr
);
```

#### <a name="parameters"></a>Parâmetros
 `assemName`

 [in] Nome do assembly para resolver.

 `assemBytes`

 [out] Retorna um [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) contendo os bytes de assembly associados à referência de objeto.

 `assemPdb`

 [out] Retorna um `IEEDataStorage` objeto que contém o símbolo de armazena os dados associados a esta referência.

 `assemLocation`

 [out] Retorna o local do caminho dessa referência.

 `alr`

 [out] Retorna um valor da [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) enumeração que indica o local do assembly dessa referência.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
 Normalmente, esse método não é implementado por um avaliador de expressão personalizada.

## <a name="see-also"></a>Consulte também
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
- [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)