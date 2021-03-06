---
title: IDebugDocumentContext2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2
helpviewer_keywords:
- IDebugDocumentContext2
ms.assetid: 2a446c71-8100-4c09-a1cc-fd446bd74030
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3de9f48109590d6c59a46fd6451a750eecfbaa01
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678757"
---
# <a name="idebugdocumentcontext2"></a>IDebugDocumentContext2
Essa interface representa uma posição em um documento do arquivo de origem.

## <a name="syntax"></a>Sintaxe

```
IDebugDocumentContext2 : IUnknown
```

## <a name="notes-for-implementers"></a>Observações para implementadores
 O mecanismo de depuração (DES) implementa essa interface como parte de seu suporte para depuração no nível do código-fonte código. Além de uma posição no código-fonte, essa interface fornece métodos para comparar os contextos e navegar por meio de um documento de código-fonte.

## <a name="notes-for-callers"></a>Observações para chamadores
 Métodos em várias interfaces, geralmente o [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) e [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) interfaces, retorne a esta interface.

## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable
 A tabela a seguir mostra os métodos de `IDebugDocumentContext2`.

|Método|Descrição|
|------------|-----------------|
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)|Obtém o documento que contém o contexto do documento.|
|[GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)|Obtém o nome de exibição do documento que contém o contexto do documento.|
|[EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)|Recupera uma lista de todos os contextos de código associado a este contexto de documento.|
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugdocumentcontext2-getlanguageinfo.md)|Obtém o idioma associado a este contexto de documento.|
|[GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|Obtém o intervalo de instrução de arquivo deste contexto de documento.|
|[GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)|Obtém o intervalo de origem de arquivo deste contexto de documento.|
|[Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)|Compara este contexto de documento para uma determinada matriz de contextos de documento.|
|[Buscar](../../../extensibility/debugger/reference/idebugdocumentcontext2-seek.md)|Move o contexto do documento por um determinado número de instruções ou linhas.|

## <a name="requirements"></a>Requisitos
 Header: msdbg.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Consulte também
- [GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)
- [GetDocumentContext](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocumentcontext.md)
- [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)
- [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)