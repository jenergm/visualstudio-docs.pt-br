---
title: JIT otimização e depuração | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7346b6fd8fbd483021437638f9e134ead88a0b93
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56699139"
---
# <a name="jit-optimization-and-debugging"></a>Otimização e depuração JIT
**Funcionam otimizações no .NET:** se você estiver tentando depurar o código, é mais fácil quando que o código está **não** otimizado. Isso ocorre porque quando o código é otimizado, o compilador e o tempo de execução fazer alterações para o código emitido de CPU para que ele é executado mais rapidamente, mas tem um mapeamento menos direto ao código-fonte original. Isso significa que os depuradores são geralmente não é possível informar o valor de variáveis locais e revisão de código e os pontos de interrupção podem não funcionar conforme o esperado.

Normalmente, a configuração de build de lançamento cria código otimizado e a configuração de build de depuração não. O `Optimize` propriedade do MSBuild controla se o compilador é instruído para otimizar o código.

No ecossistema do .NET, código será transformado da fonte em instruções de CPU em um processo em duas etapas: primeiro, o compilador c# converte o texto digitado em um formato binário intermediário chamado MSIL e isso grava em arquivos. dll. Posteriormente, o tempo de execução do .NET converte essa MSIL para instruções de CPU. As duas etapas podem otimizar até certo ponto, mas a segunda etapa executada pelo tempo de execução .NET executa otimizações mais significativas.

**A opção 'Suprimir Otimização JIT no carregamento do módulo (somente gerenciado)':** o depurador expõe uma opção que controla o que acontece quando uma DLL que é compilada com otimizações habilitadas carrega dentro do processo de destino. Se essa opção estiver marcada (o estado padrão), em seguida, quando o tempo de execução do .NET compila o código MSIL em código de CPU, ele deixa as otimizações habilitadas. Se a opção estiver marcada, o depurador solicita que as otimizações desabilitado.

Para localizar o **suprimir Otimização JIT no carregamento do módulo (somente gerenciado)** opção, selecione **ferramentas** > **opções**e, em seguida, selecione o  **Gerais** página sob o **depuração** nó.

**Quando você marca essa opção:** Marque esta opção quando você baixou as DLLs de outra origem, como um pacote do nuget, e você deseja depurar o código nessa DLL. Para que isso funcione, você também deve encontrar o arquivo de símbolo (. PDB) para essa DLL.

Se você só estiver interessado em depurar o código que você está criando localmente, é melhor deixar essa opção estiver desmarcada, pois, em alguns casos, a habilitação dessa opção será significativamente mais lenta de depuração. Há dois motivos para isso lento:

* O código otimizado é executado mais rapidamente. Se você está desativando otimizações para vários códigos, o impacto no desempenho pode adicionar até.
* Se você tiver apenas meu código habilitado, o depurador nem mesmo tentar e carregar símbolos para DLLs que são otimizadas. Localizar símbolos pode demorar muito.

**Limitações dessa opção:** há duas situações em que essa opção será **não** funcionam:

1. Em situações em que você está anexando o depurador a um processo já está em execução, essa opção não terá efeito sobre os módulos que já foram carregados no momento em que o depurador foi anexado.
2. Essa opção não tem nenhum efeito sobre DLLs que foram previamente compilado (também conhecidas como NGen) para código nativo. No entanto, você pode desabilitar o uso de um código pré-compilado iniciando o processo com o ambiente de que variável 'COMPlus_ZapDisable' definido como '1'.

## <a name="see-also"></a>Consulte também
- [Depurando código gerenciado](../debugger/debugging-managed-code.md)
- [Navegar pelo Código com o Depurador](../debugger/navigating-through-code-with-the-debugger.md)
- [Anexar a processos em execução](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [Processo de execução gerenciada](/dotnet/standard/managed-execution-process)
