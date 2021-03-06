---
title: 'Como: Suprimir Avisos usando o Item de Menu | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- warnings, suppressing
- code analysis, suppressing warnings
ms.assetid: 36bd1850-dcde-4ed0-9bc3-0b83df434362
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a8fbc314580b106f5e1e8dae5a0a78d043d3940b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60080898"
---
# <a name="how-to-suppress-warnings-by-using-the-menu-item"></a>Como: Suprimir avisos usando o item de menu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[OBSERVAÇÃO]
>  No código-fonte supressão não há suporte para projetos de site.  
  
 Você pode usar a janela de análise de código para suprimir avisos da análise de código. Suprimir um aviso não é igual a desabilitá-lo. Quando você suprime um aviso, ele se aplica somente a uma instância particular da violação. Outras violações do aviso mesmo ainda serão relatadas na janela lista de erros.  
  
 Depois de executar a análise de código, você pode determinar que um ou mais dos avisos de análise de código que são exibidos na janela análise de código não são aplicáveis ao seu aplicativo. Por exemplo, você pode determinar que o código esteja correto, como está. Ou então, ele pode ser o caso que algumas violações são de baixa prioridade e não serão corrigidas no ciclo de desenvolvimento atual. Independentemente do motivo, geralmente é útil indicar que o aviso é não aplicáveis para permitir que os membros da equipe sabe que o código foi revisado e que foi determinado que o aviso pode ser suprimido. No código-fonte supressão é útil porque permite colocar uma supressão perto de onde o aviso será gerado.  
  
 Você pode escolher se a supressão aparecerá no código-fonte ou no arquivo de supressão global. Alguns supressões devem ser colocados no arquivo de supressão global. Se esse for o caso, o **na origem** opção será desabilitada.  
  
### <a name="to-suppress-a-warning-by-using-menu-item"></a>Para suprimir um aviso usando o item de menu  
  
1. Sobre o **Analyze** menu, escolha **Windows** e, em seguida, escolha **análise de código**.  
  
2. No **análise de código** janela, selecione suprimir o aviso.  
  
3. Escolha ações e, em seguida, escolha **suprimir mensagem (NS)** e, em seguida, escolha **no código-fonte** ou **no arquivo de supressão do projeto**.  
  
     O aviso específico é suprimido e o aviso é exibido na janela análise de código com um tachado.  
  
> [!NOTE]
>  Supressões que não têm um destino aparecem no arquivo de supressão global.
