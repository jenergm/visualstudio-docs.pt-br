---
title: 'Etapa 5: Adicionar referências de rótulo | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: d418350c-0396-494e-8149-71fa61b395c5
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3f062b48edfbe87fb97d94b3ea852486f66a19d1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60041865"
---
# <a name="step-5-add-label-references"></a>Etapa 5: Adicionar referências de rótulo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O programa precisa rastrear quais controles de rótulo o jogador escolhe. Atualmente, o programa mostra todos os rótulos escolhidos pelo jogador. Mas isso será alterado. Depois que o primeiro rótulo é escolhido, o programa deve mostrar o ícone do rótulo. Depois que o segundo rótulo é escolhido, o programa deve exibir ambos os ícones por um breve momento e depois ocultá-los novamente. Agora seu programa rastreará qual controle de rótulo será escolhido primeiro e qual será escolhido em segundo usando *variáveis de referência*.  
  
### <a name="to-add-label-references"></a>Para adicionar referências de rótulo  
  
1. Adicione referências de rótulo ao seu formulário usando o código a seguir.  
  
     [!code-csharp[VbExpressTutorial4Step5#5](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step5/cs/form1.cs#5)]
     [!code-vb[VbExpressTutorial4Step5#5](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step5/vb/form1.vb#5)]  
  
     Essas variáveis de referência parecem semelhantes às instruções que você usou anteriormente para adicionar objetos (como os objetos `Timer`, `List` e `Random`) ao formulário. No entanto, essas instruções não fazem com que os dois controles de rótulo extras apareçam no formulário, pois a palavra-chave `new` não foi usada em nenhuma das duas instruções. Sem a palavra-chave `new`, nenhum objeto é criado. É por isso que `firstClicked` e `secondClicked` são chamadas de variáveis de referência: Eles apenas manter o controle (ou consultar) `Label` objetos.  
  
     Quando uma variável não estiver rastreando um objeto, ela será definida para um valor reservado especial: `null` no Visual C# e `Nothing` no Visual Basic. Desse modo, quando o programa for iniciado, `firstClicked` e `secondClicked` serão definidas como `null` ou `Nothing`, o que significa que as variáveis não estão rastreando nada.  
  
2. Modifique o manipulador de eventos Click para usar a nova variável de referência `firstClicked`. Remova a última instrução no método do manipulador de eventos `label_Click()` (`clickedLabel.ForeColor = Color.Black;`) e substitua-a pela instrução `if` que se segue. (Não se esqueça de incluir o comentário e a instrução `if` inteira.)  
  
     [!code-csharp[VbExpressTutorial4Step5#6](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step5/cs/form1.cs#6)]
     [!code-vb[VbExpressTutorial4Step5#6](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step5/vb/form1.vb#6)]  
  
3. Salve e execute seu programa. Escolha um dos controles de rótulo e seu ícone é exibido.  
  
4. Escolha o próximo controle de rótulo e observe que nada acontece. O programa já está rastreando o primeiro rótulo que o jogador escolheu, de modo que `firstClicked` não é igual a `null` no Visual C# ou `Nothing` no Visual Basic. Quando sua instrução `if` verifica `firstClicked` para determinar se ele é igual a `null` ou `Nothing`, ela descobre que não é e não executa as instruções na instrução `if`. Desse modo, somente o primeiro ícone que é escolhido torna-se preto e os outros ícones ficam invisíveis, conforme mostrado na imagem a seguir.  
  
     ![Jogo da memória mostrando um ícone](../ide/media/express-tut4step5.png "Express_Tut4Step5")  
Jogo da memória mostrando um ícone  
  
     Essa situação será corrigida na primeira etapa do tutorial adicionando um controle **Temporizador**.  
  
### <a name="to-continue-or-review"></a>Para continuar ou revisar  
  
- Para ir para a próxima etapa do tutorial, confira [Etapa 6: Adicionar um temporizador](../ide/step-6-add-a-timer.md).  
  
- Para retornar à etapa anterior do tutorial, confira [Etapa 4: Adicionar um manipulador de eventos Click a cada rótulo](../ide/step-4-add-a-click-event-handler-to-each-label.md).
