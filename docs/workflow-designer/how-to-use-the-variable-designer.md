---
title: 'Designer de fluxo de trabalho - como: Usar a variável do designer'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- System.Activities.Presentation.View.DesignTimeVariable.UI
ms.assetid: 0318dfb0-bf8f-4f92-9b86-ae4c1b2161ad
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f90cbb58406df2410361bf9409c843b5c35b4331
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60051463"
---
# <a name="how-to-use-the-variable-designer"></a>Como: Usar a variável do designer

O designer variável é usado para criar variáveis para uso em cenários e em instruções condicionais de associação de dados. O designer é acessado clicando o **variáveis** botão no canto inferior esquerdo da tela de design. O designer contém uma lista de variáveis que aparecem em um formulário tabular e podem ser classificados por cada um dos cabeçalhos de coluna, exceto para o **padrão** coluna. Cada variável contém um nome, um tipo de variável, um escopo, e um valor padrão (se houver). O nome e o valor padrão são campos editáveis de texto, e o tipo e escopo são gota- suspensa. O escopo é a atividade que foi selecionada quando o designer variável foi chamado. Se uma variável não pode ser criado no escopo de seleção, então o escopo usará padrão a atividade a mais próxima de ancestral de seleção que permite variáveis criado em seu escopo. Para obter mais informações, consulte [variáveis e argumentos (.NET)](/dotnet/framework/windows-workflow-foundation/variables-and-arguments).

 A ordem de classificação não é aplicado até que o usuário explicitamente use um dos controles de classificação, feche e reabra o designer variável, ou cria outra variável.

## <a name="to-create-a-new-variable"></a>Para criar uma nova variável

1. Abra uma solução de fluxo de trabalho ou atividade no Visual Studio.

2. Na tela de design, selecione uma atividade no fluxo de trabalho.

3. Abra o designer variável clicando o **variáveis** botão no canto inferior esquerdo da tela de design. O designer variável aparece.

4. Clique na linha vazia rotulada **criar variável**. Isso adicionará uma nova linha com uma nova variável usando os seguintes valores padrão: variablex para o **nome** onde x é um inteiro com um valor inicial de 1, que é incrementado automaticamente para criar nomes de variável exclusivos,  **Cadeia de caracteres** para o **tipo de variável**, e **sequência** para o **escopo**. Nenhum valor é adicionado para **padrão**. Você pode alterar esses valores a qualquer momento durante o processo de design de fluxo de trabalho.

    > [!NOTE]
    > Para excluir uma variável, selecione a variável clicando nele e, em seguida, pressione a **excluir** chave.

## <a name="see-also"></a>Consulte também

- [Usando o Designer de Fluxo de Trabalho](developing-applications-with-the-workflow-designer.md)
- [Variables and Arguments](/dotnet/framework/windows-workflow-foundation/variables-and-arguments) (Variáveis e argumentos)
- [Como: usar o designer de argumento](../workflow-designer/how-to-use-the-argument-designer.md)