---
title: Gerar uma substituição de método
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: afb32a7ddb9a53ac6585cc690a3ba8fd1098b080
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55947023"
---
# <a name="generate-an-override-in-visual-studio"></a>Gerar uma substituição no Visual Studio

Esta geração de código aplica-se a:

- C#

- Visual Basic

**O quê:** Permite gerar imediatamente o código para qualquer método que possa ser substituído em uma classe base.

**Quando:** Você deseja substituir um método de classe base e gerar a assinatura automaticamente.

**Por que:** Você mesmo pode escrever a assinatura do método; no entanto, essa funcionalidade gerará a assinatura automaticamente.

## <a name="how-to"></a>Como fazer

1. Digite `override` em C# ou `Overrides` em Visual Basic, seguido por um espaço, em que você deseja inserir um método de substituição.

   - C#:

      ![Substituição do IntelliSense em C#](media/override-intellisense-cs.png)

   - Visual Basic:

      ![Substituição do IntelliSense em VB](media/override-intellisense-vb.png)

2. Selecione o método que você deseja substituir da classe base.

   > [!TIP]
   > - Use o ícone de propriedade ![Ícone de propriedade](media/override-property-cs.png) para mostrar ou ocultar propriedades na lista.
   > - Use o ícone de método ![Ícone de método](media/override-method-cs.png) para mostrar ou ocultar métodos na lista.

   A propriedade ou o método selecionado será adicionado à classe como uma substituição, pronta para ser implementada.

   - C#:

       ![Resultado da substituição em C#](media/override-result-cs.png)

   - Visual Basic:

       ![Resultado da substituição em VB](media/override-result-vb.png)

## <a name="see-also"></a>Consulte também

- [Geração de código](../code-generation-in-visual-studio.md)