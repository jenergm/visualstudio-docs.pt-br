---
title: IDebugDocument2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocument2
helpviewer_keywords:
- IDebugDocument2 interface
ms.assetid: 1bc58426-dbf5-4471-9aad-9d66cd80eef0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 28334cc7aa0c8a5587a20d6c9dfdee3133d9ea7e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718190"
---
# <a name="idebugdocument2"></a>IDebugDocument2
Essa interface representa um documento de origem.

## <a name="syntax"></a>Sintaxe

```
IDebugDocument2 : IUnknown
```

## <a name="notes-for-implementers"></a>Observações para implementadores
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] normalmente implementa essa interface. Um mecanismo de depuração (DES) também pode implementar essa interface quando ele precisa fornecer o código-fonte e a origem não existe no disco.  Nesses casos, o DE também implementaria [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) e [IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md) interfaces, bem como alguns métodos adicionais sobre o [ IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) e [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md) interfaces.

## <a name="notes-for-callers"></a>Observações para chamadores
 Métodos de `IDebugDocumentContext2`, `IDebugDisassemblyStream2`, `IDebugDocumentPosition2`, e `IDebugActivateDocumentEvent2` interfaces retornam essa interface.

## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable
 A tabela a seguir mostra os métodos de `IDebugDocument2`.

|Método|Descrição|
|------------|-----------------|
|[GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)|Obtém o nome do documento em uma das várias formas.|
|[GetDocumentClassID](../../../extensibility/debugger/reference/idebugdocument2-getdocumentclassid.md)|Obtém o identificador de classe do documento.|

## <a name="remarks"></a>Comentários
 Essa interface é implementada somente quando o DE fornece o código-fonte. Por exemplo, quando você estiver depurando um script em uma página HTML, o DE fornece o código-fonte porque a fonte é baixada ou gerada dinamicamente e não existe como um arquivo de disco. Durante a depuração de linguagens tradicionais, como C++, essa interface não precisa ser implementado.

## <a name="requirements"></a>Requisitos
 Header: msdbg.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)
- [GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)
- [GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)
- [GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)
- [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)