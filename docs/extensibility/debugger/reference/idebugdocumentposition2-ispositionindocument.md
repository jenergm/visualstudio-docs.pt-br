---
title: IDebugDocumentPosition2::IsPositionInDocument | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentPosition2::IsPositionInDocument
helpviewer_keywords:
- IDebugDocumentPosition2::IsPositionInDocument
ms.assetid: d5cf57cb-b93b-4e1d-bec9-185f4fe8668d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e5701df9085de7a63e7f09ea37c28244897122b7
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678911"
---
# <a name="idebugdocumentposition2ispositionindocument"></a>IDebugDocumentPosition2::IsPositionInDocument
Determina se a posição do documento está contida em um determinado documento.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT IsPositionInDocument( 
   IDebugDocument2* pDoc
);
```

```csharp
int IsPositionInDocument( 
   IDebugDocument2 pDoc
);
```

#### <a name="parameters"></a>Parâmetros
 `pDoc`

 [in] O [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) objeto que representa o recipiente candidato de documento.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
 Esse método é usado principalmente em Configurar pontos de interrupção [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) interfaces. Como documentos são carregados, a posição do ponto de interrupção é chamada para determinar se o documento contém nessa posição.

## <a name="see-also"></a>Consulte também
- [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)