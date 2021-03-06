﻿---
title: Inspecionar variáveis - janelas Autos e locais | Microsoft Docs
ms.custom: seodec18
ms.date: 10/18/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.autos
- vs.debug.locals
helpviewer_keywords:
- debugger, variable windows
- debugging [Visual Studio], variable windows
ms.assetid: bb6291e1-596d-4af0-9f22-5fd713d6b84b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 60bb98644c1905b030176b28b97575b379bed38d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60103089"
---
# <a name="inspect-variables-in-the-autos-and-locals-windows"></a>Inspecionar variáveis nas janelas Autos e locais

O **Autos** e **Locals** windows mostram valores de variáveis durante a depuração. Os windows estão disponíveis somente durante uma sessão de depuração. O **Autos** janela mostra as variáveis usadas em torno do ponto de interrupção atual. A janela **Locals** mostra as variáveis definidas no escopo local, que geralmente é o método ou a função atual. Se essa for a primeira vez que você tentou depurar o código, você talvez queira ler [depuração para iniciantes absolutos](../debugger/debugging-absolute-beginners.md) e [técnicas e ferramentas de depuração](../debugger/write-better-code-with-visual-studio.md) antes de prosseguir com este artigo.

 O **Autos** janela está disponível para C#, código do Visual Basic, C++ e Python, mas não para JavaScript ou F#.

Para abrir o **Autos** janela, durante a depuração, selecione **Debug** > **Windows** > **Autos**, ou pressione **Ctrl**+**Alt**+**V** > **um**.

Para abrir a janela **Locals**, durante a depuração, selecione **Debug** > **Windows** > **Locals**, ou pressione **Alt**+**4**.

> [!NOTE]
> Este tópico aplica-se ao Visual Studio no Windows. Para o Visual Studio para Mac, consulte [visualizações de dados no Visual Studio para Mac](/visualstudio/mac/data-visualizations).

## <a name="use-the-autos-and-locals-windows"></a>Usar as janelas Autos e locais

Matrizes e objetos mostram na **Autos** e **locais** windows como controles de árvore. Selecione a seta à esquerda de um nome de variável para expandir a exibição para mostrar os campos e propriedades. Aqui está um exemplo de uma <xref:System.IO.FileStream?displayProperty=fullName> do objeto na janela **Locals**:

![Locals-FileStream](../debugger/media/locals-filestream.png "Locals-FileStream")

Um valor de vermelho na janela **Locals** ou **Autos** significa que o valor foi alterado desde a última avaliação. A alteração pode ser proveniente de uma sessão de depuração anterior, ou porque você alterou o valor na janela.

O formato numérico de padrão nas janelas do depurador é decimal. Para alterá-la em hexadecimal, clique com botão direito na janela **Locals** ou **Autos** e selecione **exibição Hexadecimal**. Essa alteração afeta todas as janelas do depurador.

## <a name="edit-variable-values-in-the-autos-or-locals-window"></a>Editar valores de variáveis na janela Autos ou locais

Para editar os valores da maioria das variáveis na **Autos** ou **Locals** windows, clique duas vezes o valor e digite o novo valor.

Você pode inserir uma expressão para um valor, por exemplo `a + b`. O depurador aceita expressões de linguagem mais válidas.

No código C++ nativo, talvez você precise qualificar o contexto de um nome de variável. Para obter mais informações, consulte [operador de contexto (C++)](../debugger/context-operator-cpp.md).

>[!CAUTION]
> Certifique-se de compreender as consequências antes de alterar valores e expressões. Alguns problemas possíveis são:
>
> - Avaliar algumas expressões pode alterar o valor de uma variável ou, de outra forma, afetar o estado do programa. Por exemplo, a avaliação de `var1 = ++var2` altera o valor de ambos `var1` e `var2`. Essas expressões são consideradas como tendo [efeitos colaterais](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\)). Efeitos colaterais podem causar resultados inesperados se você não estiver ciente deles.
>
> - Editar valores de ponto flutuante pode resultar em imprecisões secundárias devido à conversão decimal-binária de componentes fracionários. Até mesmo uma edição aparentemente inofensiva pode resultar em alterações para alguns dos bits na variável de ponto flutuante.

::: moniker range=">= vs-2019" 
## <a name="search-in-the-autos-or-locals-window"></a>Pesquisar na janela Autos ou locais

Você pode pesquisar por palavras-chave nas colunas de nome, valor e tipo de **Autos** ou **Locals** janela usando a barra de pesquisa acima de cada janela. Pressionar ENTER, ou selecione uma das setas para executar uma pesquisa. Para cancelar uma pesquisa em andamento, selecione o ícone "x" na barra de pesquisa.

Use as setas à esquerda e direita (Shift + F3 e F3, respectivamente) navegar entre encontradas correspondências.

![Pesquisa na janela locais](../debugger/media/ee-search-locals.png "pesquisa na janela locais")

Para tornar sua pesquisa mais ou menos completo, use o **pesquisa mais profunda** lista suspensa na parte superior das **Autos** ou **locais** janela para selecionar quantos níveis de profundidade que você deseja pesquisar em objetos aninhados. 

::: moniker-end

## <a name="change-the-context-for-the-autos-or-locals-window"></a>Alterar o contexto para a janela Autos ou locais

Você pode usar a barra de ferramentas **Local de Depuração** para selecionar uma função desejada, thread ou processo, que altera o contexto para as janelas **Autos** e **Locals**.

Para habilitar a barra de ferramentas **local de depuração**, clique em uma parte vazia da área da barra de ferramentas e selecione **local de depuração** da lista suspensa ou selecione **exibição** > **Barras de ferramentas** > **local de depuração**.

Definir um ponto de interrupção e iniciar a depuração. Quando o ponto de interrupção é atingido, a execução para e você pode ver o local na barra de ferramentas **local de depuração**.

![Barra de ferramentas local de depuração](../debugger/media/debuglocationtoolbar.png "barra de ferramentas Depurar local")

## <a name="bkmk_whatvariables"></a> As variáveis na janela Autos (C#, C++, Visual Basic, Python)

Linguagens de código diferentes exibem variáveis diferentes nos **Autos** janela.

- No C# e Visual Basic, a janela **Autos** exibirá qualquer variável usada na linha atual ou anterior. Por exemplo, em C# ou Visual Basic de código, declare as quatro variáveis a seguir:

   ```csharp
       public static void Main()
       {
          int a, b, c, d;
          a = 1;
          b = 2;
          c = 3;
          d = 4;
       }
   ```

   Defina um ponto de interrupção na linha `c = 3;`, e inicie o depurador. Quando a execução pausa, o **Autos** janela será exibida:

   ![Autos-CSharp](../debugger/media/autos-csharp.png "Autos-CSharp")

   O valor de `c` é 0, porque a linha `c = 3` ainda não foi executada.

- No C++, o **Autos** janela exibe as variáveis usadas em pelo menos três linhas antes da linha atual em que a execução está em pausa. Por exemplo, no código C++, declare seis variáveis:

   ```C++
       void main() {
           int a, b, c, d, e, f;
           a = 1;
           b = 2;
           c = 3;
           d = 4;
           e = 5;
           f = 6;
       }
   ```

    Defina um ponto de interrupção na linha `e = 5;` e execute o depurador. Quando a execução for interrompida, o **Autos** janela será exibida:

    ![Autos-C++](../debugger/media/autos-cplus.png "Autos-C++")

    A variável `e` não foi inicializada, porque a linha `e = 5` ainda não foi executada.

## <a name="bkmk_returnValue"></a> Modo de exibição de valores de retorno de chamadas de método
 No código .NET e C++, você pode examinar os valores de retorno na **Autos** janela ao passar sobre ou fora de uma chamada de método. Pode ser útil exibir valores de retornor de chamadas de método quando eles não são armazenados em variáveis locais. Um método pode ser usado como um parâmetro ou como o valor retornado de outro método.

 Por exemplo, a seguinte C# código adiciona os valores de retorno das duas funções:

```csharp
static void Main(string[] args)
{
    int a, b, c, d;
    a = 1;
    b = 2;
    c = 3;
    d = 4;
    int x = sumVars(a, b) + subtractVars(c, d);
}

private static int sumVars(int i, int j)
{
    return i + j;
}

private static int subtractVars(int i, int j)
{
    return j - i;
}
```

Para ver os valores de retorno de `sumVars()` e `subtractVars()` chamadas de método na janela Autos:

1. Defina um ponto de interrupção a `int x = sumVars(a, b) + subtractVars(c, d);` linha.

1. Inicie a depuração e, quando a execução parar no ponto de interrupção, selecione **Step Over** ou pressione **F10**. Você deve ver os seguintes valores de retornados na **Autos** janela:

  ![Valor de retorno de Autos C# ](../debugger/media/autosreturnvaluecsharp2.png "Autos retornam valorC#")

## <a name="see-also"></a>Consulte também

- [O que é depuração?](../debugger/what-is-debugging.md)
- [Ferramentas e técnicas de depuração](../debugger/write-better-code-with-visual-studio.md)
- [Primeira olhada na depuração](../debugger/debugger-feature-tour.md)
- [Janelas do depurador](../debugger/debugger-windows.md)
