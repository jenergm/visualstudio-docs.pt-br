---
title: Hierarquia de tipos de símbolo de classes | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [DIA SDK], class hierarchies
ms.assetid: 0ccd6990-4654-44cd-a6f3-bdd82fe90f6c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 67e32d855ec6d0c172542cbdacc235f6b3e1b003
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604438"
---
# <a name="class-hierarchy-of-symbol-types"></a>Hierarquia de classes de tipos de símbolos
A tabela a seguir descreve os tipos de símbolo na hierarquia de classe.

## <a name="symbol-types"></a>Tipos de símbolo

|Tipo de símbolo|Descrição|
|-----------------|-----------------|
|[UDT](../../debugger/debug-interface-access/udt.md)|Símbolo usado para representar cada classe, estrutura e união.|
|[Enum (SDK de Acesso à Interface de Depuração)](../../debugger/debug-interface-access/enum-debug-interface-access-sdk.md)|Símbolo de tipos enumerados.|
|[PointerType](../../debugger/debug-interface-access/pointertype.md)|Símbolo de tipos de ponteiro.|
|[ArrayType](../../debugger/debug-interface-access/arraytype.md)|Símbolo de tipos de matriz.|
|[BaseType](../../debugger/debug-interface-access/basetype.md)|Símbolo de tipos base|
|[Typedef (SDK de Acesso à Interface de Depuração)](../../debugger/debug-interface-access/typedef-debug-interface-access-sdk.md)|Símbolo que apresenta nomes para outros tipos.|
|[BaseClass](../../debugger/debug-interface-access/baseclass.md)|Símbolo usado para cada classe base de um tipo definido pelo usuário (UDT).|
|[Friend (SDK de Acesso à Interface de Depuração)](../../debugger/debug-interface-access/friend-debug-interface-access-sdk.md)|Símbolo para funções de amigo e classes de amigo.|
|[FunctionType](../../debugger/debug-interface-access/functiontype.md)|Símbolo para cada assinatura de função exclusiva.|
|[FunctionArgType](../../debugger/debug-interface-access/functionargtype.md)|Símbolo para cada parâmetro para uma função.|
|[VTableShape](../../debugger/debug-interface-access/vtableshape.md)|Símbolo para o tamanho da tabela virtual.|
|[VTable](../../debugger/debug-interface-access/vtable.md)|Símbolo de uma tabela virtual.|
|[CustomType](../../debugger/debug-interface-access/customtype.md)|Símbolo de tipo definido pelo fornecedor.|
|[ManagedType](../../debugger/debug-interface-access/managedtype.md)|Símbolo de um tipo definido nos metadados.|
|[Dimensão](../../debugger/debug-interface-access/dimension.md)|Símbolo de dimensões de matriz.|

> [!NOTE]
>  Cada símbolo pode ter propriedades que contêm informações sobre o símbolo, bem como referências a outros símbolos. Essas propriedades são listadas nos tópicos individuais de símbolo.

## <a name="see-also"></a>Consulte também
- [Enumeração CV_access_e](../../debugger/debug-interface-access/cv-access-e.md)
- [Hierarquia lexical de tipos de símbolo](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)
- [Símbolos e marcações de símbolos](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)