---
title: 'VsgDbg:: ~ VsgDbg (destruidor) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7a3b97fb-d344-4df7-b195-9347d1edfcf7
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c0ae3dd206953e728175f4479920861295feae00
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58925089"
---
# <a name="vsgdbgvsgdbg-destructor"></a>VsgDbg::~VsgDbg (Destruidor)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Destrói uma instância da `VsgDbg` classe. Se informações de gráficos ativamente está sendo registradas, o arquivo de log de gráficos é finalizado e fechado, e os recursos que foram usados durante a captura ativamente informações gráficas são liberados.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
~VsgDbg();  
```  
  
## <a name="see-also"></a>Consulte também  
 [VsgDbg::VsgDbg (Construtor)](../debugger/vsgdbg-vsgdbg-constructor.md)
