---
title: Depuração de aplicativos de modo misto | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging, property evaluation
- Call Stack window
- mixed-mode debugging
- Call Stack window, mixed-mode debugging
- debugging managed code, mixed code
- mixed-mode debugging, call stack
ms.assetid: 60e34477-ae4e-48c7-9093-3e37f72e1bc3
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 079ea874e316ede55a489f6f926fd947bd6628fe
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60051421"
---
# <a name="debugging-mixed-mode-applications"></a>Depurando aplicativos de modo misto
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Um aplicativo no modo misto é qualquer aplicativo que combine código nativo (C++) com código gerenciado (como o Visual Basic, Visual C# ou C++ que é executado no Common Language Runtime). A depuração de aplicativos no modo misto é totalmente transparente no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]; não é muito diferente da depuração de um aplicativo no modo único. No entanto, há algumas considerações especiais a serem feitas.  
  
## <a name="enable-c-edit-and-continue-in-mixed-mode-debugging"></a>Habilitar o recurso Editar e Continuar do C++ na depuração em modo misto  
  
- Para usar o recurso Editar e Continuar do C++ no Visual Studio 2013, você precisa reverter para o mecanismo de depuração herdado. Veja [Alternando para o Modo de Compatibilidade Gerenciado no Visual Studio 2013](http://blogs.msdn.com/b/visualstudioalm/archive/2013/10/16/switching-to-managed-compatibility-mode-in-visual-studio-2013.aspx) no blog de gerenciamento do ciclo de vida de aplicativos da Microsoft.  
  
## <a name="property-evaluation-in-mixed-mode-applications"></a>Avaliação da propriedade em aplicativos no modo misto  
 Em um aplicativo no modo misto, a avaliação das propriedades pelo depurador é uma operação cara. Consequentemente, as operações de depuração em etapas pode parecer lenta. Para obter mais informações, confira [Em etapas](http://msdn.microsoft.com/8791dac9-64d1-4bb9-b59e-8d59af1833f9). Se o desempenho for baixo na depuração em modo misto, você poderá desativar a avaliação da propriedade nas janelas do depurador.  
  
> [!NOTE]
>  As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas. Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**. Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
#### <a name="to-turn-off-property-evaluation"></a>Para desativar a avaliação da propriedade  
  
1. No menu **Ferramentas**, escolha **Opções**.  
  
2. Na caixa de diálogo **Opções**, abra a pasta **Depuração** e selecione a categoria **Geral**.  
  
3. Desmarque a caixa de seleção **Habilitar a avaliação da propriedade e outras chamadas de função implícitas**.  
  
   Como as pilhas de chamadas nativas e as pilhas de chamadas gerenciadas são diferentes, o depurador nem sempre pode fornecer a pilha de chamadas completa para código combinado. Quando o código nativo chamar o código gerenciado, você poderá observar algumas discrepâncias. Para obter mais informações, confira [Código misto e informações ausentes na janela Pilha de Chamadas](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md).  
  
## <a name="see-also"></a>Consulte também  
 [Depurando código gerenciado](../debugger/debugging-managed-code.md)
