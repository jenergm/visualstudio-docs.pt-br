---
title: LocationType | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- LocationType enumeration
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 28bcaa626797313f6ea68a17da33ef9ea192a856
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58927364"
---
# <a name="locationtype"></a>LocationType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Indica o tipo de informações de localização contidas em um símbolo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
enum LocationType {   
   LocIsNull,  
   LocIsStatic,  
   LocIsTLS,  
   LocIsRegRel,  
   LocIsThisRel,  
   LocIsEnregistered,  
   LocIsBitField,  
   LocIsSlot,  
   LocIsIlRel,  
   LocInMetaData,  
   LocIsConstant,  
   LocTypeMax  
};  
```  
  
## <a name="elements"></a>Elementos  
 `LocIsNull`  
 Informações de localização não estão disponíveis.  
  
 `LocIsStatic`  
 Localização é estática.  
  
 `LocIsTLS`  
 Local está no armazenamento local de thread.  
  
 `LocIsRegRel`  
 Local é relativo ao registro.  
  
 `LocIsThisRel`  
 Local é `this`-relativo.  
  
 `LocIsEnregistered`  
 Localização é um registro.  
  
 `LocIsBitField`  
 Localização é um campo de bits.  
  
 `LocIsSlot`  
 Local é um slot de Microsoft Intermediate Language (MSIL).  
  
 `LocIsIlRel`  
 Local é relativo ao MSIL.  
  
 `LocInMetaData`  
 Local é nos metadados.  
  
 `LocIsConstant`  
 Localização é um valor constante.  
  
 `LocTypeMax`  
 O número de tipos de localização nesta enumeração.  
  
## <a name="remarks"></a>Comentários  
 As propriedades disponíveis para o [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) interface dependem do local do símbolo no arquivo de imagem. Para obter mais informações, consulte [locais de símbolos](../../debugger/debug-interface-access/symbol-locations.md).  
  
 Os valores nesta enumeração são retornados por uma chamada para o [idiasymbol:: Get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md) método.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: cvconst.h  
  
## <a name="see-also"></a>Consulte também  
 [Enumerações e estruturas](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)   
 [Locais de símbolos](../../debugger/debug-interface-access/symbol-locations.md)
