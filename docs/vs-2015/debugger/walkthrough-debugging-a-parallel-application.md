---
title: 'Passo a passo: Depurando um aplicativo paralelo | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, parallel tasks walkthrough
- parallel stacks toolwindow
- parallel tasks toolwindow
- parallel applications, debugging [C++]
- debugging, parallel applications
- parallel applications, debugging [Visual Basic]
- parallel applications, debugging [C#]
ms.assetid: 2820ac4c-c893-4d87-8c62-83981d561493
caps.latest.revision: 31
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3e2140f15000b3ba270605af29ee36665c0137ee
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60092963"
---
# <a name="walkthrough-debugging-a-parallel-application"></a>Passo a passo: Depurando um aplicativo paralelo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Este passo a passo descreve como usar as janelas **Tarefas Paralelas** e **Pilhas Paralelas** para depurar um aplicativo paralelo. Essas janelas ajudarão-lo a compreender e verificar o comportamento de tempo de execução do código que usa o [tarefa TPL (biblioteca paralela)](http://msdn.microsoft.com/library/b8f99f43-9104-45fd-9bff-385a20488a23) ou o [tempo de execução de simultaneidade](http://msdn.microsoft.com/library/874bc58f-8dce-483e-a3a1-4dcc9e52ed2c). Este passo a passo fornece código de exemplo que tem pontos de interrupção internos. Após a interrupção do código, este passo a passo mostra como usar as janelas **Tarefas Paralelas** e **Pilhas Paralelas** para examiná-lo.  
  
 Este passo a passo ensina estas tarefas:  
  
- Como exibir as chamadas de pilhas de todos os threads em uma exibição.  
  
- Como exibir a lista de instâncias de `System.Threading.Tasks.Task` que são criadas no seu aplicativo.  
  
- Como exibir as chamadas de pilhas de tarefas reais em vez de threads.  
  
- Como navegar até o código das janelas **Tarefas Paralelas** e **Pilhas Paralelas**.  
  
- Como as janelas lidam com a escala por agrupamento, zoom e outros recursos relacionados.  
  
## <a name="prerequisites"></a>Pré-requisitos  
 Este passo a passo pressupõe que **Just My Code** está habilitado. No menu **Ferramentas**, clique em **Opções**, expanda o nó **Depuração**, selecione **Geral** e **Habilitar Apenas Meu Código (somente Gerenciado)**. Se você não definir esse recurso, ainda poderá usar este passo a passo, mas os resultados poderão ser diferentes das ilustrações.  
  
## <a name="c-sample"></a>Exemplo do C#  
 Se você usar o exemplo do C#, este passo a passo também pressuporá que o código externo está oculto. Para ativar ou desativar a exibição do código externo, clique com o botão direito do mouse no cabeçalho de tabela **Nome** da janela **Pilha de Chamadas** e, depois, marque ou desmarque **Mostrar Código Externo**. Se você não definir esse recurso, ainda poderá usar este passo a passo, mas os resultados poderão ser diferentes das ilustrações.  
  
## <a name="c-sample"></a>Exemplo do C++  
 Se você usar o exemplo do C++, poderá ignorar referências ao código externo neste tópico. O código externo aplica-se somente ao exemplo do C#.  
  
## <a name="illustrations"></a>Ilustrações  
 As ilustrações neste tópico foram gravadas em um computador de quatro núcleos executando o exemplo do C#. Embora você possa usar outras configurações para concluir este passo a passo, as ilustrações poderão diferir do que é exibido em seu computador.  
  
## <a name="creating-the-sample-project"></a>Criando o projeto de exemplo  
 O código de exemplo neste passo a passo é para um aplicativo que não faça nada. O objetivo é apenas entender como usar as janelas de ferramenta para depurar um aplicativo paralelo.  
  
#### <a name="to-create-the-sample-project"></a>Para criar o projeto de exemplo  
  
1. No Visual Studio, no menu **Arquivo**, aponte para **Novo** e clique em **Projeto**.  
  
2. No **modelos instalados** painel, selecione Visual c#, Visual Basic ou Visual C++. Para as linguagens gerenciadas, certifique-se de que [!INCLUDE[net_v40_short](../includes/net-v40-short-md.md)] seja exibido na caixa da estrutura.  
  
3. Selecione **aplicativo de Console** e, em seguida, clique em **Okey**. Permaneça na configuração de depuração, que é o padrão.  
  
4. No projeto, abra o arquivo de código .cpp, .cs ou .vb. Exclua o conteúdo para criar um arquivo de código vazio.  
  
5. Cole o código a seguir para seu idioma escolhido no arquivo de código vazio.  
  
   [!code-cpp[Debugger#1](../snippets/cpp/VS_Snippets_Misc/debugger/cpp/beta2_native.cpp#1)]
   [!code-csharp[Debugger#1](../snippets/csharp/VS_Snippets_Misc/debugger/cs/s.cs#1)]
   [!code-vb[Debugger#1](../snippets/visualbasic/VS_Snippets_Misc/debugger/vb/module1.vb#1)]  
  
6. No menu **Arquivo**, clique em **Salvar tudo**.  
  
7. No menu **Compilar**, clique em **Recompilar Solução**.  
  
    Observe que há quatro chamadas a `Debugger.Break` (`DebugBreak` no exemplo do C++). Em virtude disso, você não precisa inserir pontos de interrupção; a execução do aplicativo causará sua interrupção no depurador até quatro vezes.  
  
## <a name="using-the-parallel-stacks-window-threads-view"></a>Usando a janela Pilhas Paralelas: Modo de Exibição de Threads  
 No menu **Depuração**, clique em **Iniciar Depuração**. Aguarde até que o primeiro ponto de interrupção seja atingido.  
  
#### <a name="to-view-the-call-stack-of-a-single-thread"></a>Para exibir a pilha de chamadas de um único thread  
  
1. No menu **Depurar**, aponte para **Janelas** e, em seguida, clique em **Threads**. Encaixe a janela **Threads** na parte inferior do Visual Studio.  
  
2. No menu **Depurar**, aponte para **Janelas** e, em seguida, clique em **Pilha de Chamadas**. Encaixe a janela **Pilha de Chamadas** na parte inferior do Visual Studio.  
  
3. Clique duas vezes em um thread na janela **Threads** para torná-lo atual. Os threads atuais têm uma seta amarela. Quando você altera o thread atual, a pilha de chamadas é exibida na janela **Pilha de Chamadas**.  
  
#### <a name="to-examine-the-parallel-stacks-window"></a>Para examinar a janela Pilhas Paralelas  
  
1. No menu **Depurar**, aponte para **Windows** e, em seguida, clique em **Pilhas Paralelas**. Verifique se **Threads** está selecionado na caixa no canto superior esquerdo.  
  
     Usando o **pilhas paralelas** janela, você pode exibir várias pilhas de chamadas ao mesmo tempo em uma exibição. A ilustração a seguir mostra a **pilhas paralelas** acima da janela do **pilha de chamadas** janela.  
  
     ![Exibição na janela pilhas paralelas de threads](../debugger/media/pdb-walkthrough-1.png "PDB_Walkthrough_1")  
  
     A pilha de chamadas do thread principal é exibida em uma caixa e as pilhas de chamadas dos outros quatro threads são agrupadas em outra caixa. Quatro threads são agrupados porque os quadros de pilhas compartilham os mesmos contextos do método; isto é, estão nos mesmos métodos: `A`, `B`, e `C`. Para exibir as IDs de thread e os nomes dos threads que compartilham a mesma caixa, passe o mouse sobre o cabeçalho (**4 Threads**). O thread atual é exibido em negrito, como mostra a ilustração a seguir.  
  
     ![Dica de ferramenta que mostra os nomes e IDs de thread](../debugger/media/pdb-walkthrough-1a.png "PDB_Walkthrough_1A")  
  
     A seta amarela indica o quadro de pilhas do thread atual. Para obter mais informações, passe o mouse sobre ela  
  
     ![Dica de ferramenta no quadro de pilhas ativas](../debugger/media/pdb-walkthrough-1b.png "PDB_Walkthrough_1B")  
  
     Você pode definir a quantidade de detalhes a ser mostrada para os quadros de pilha (**Nomes de Módulo**, **Tipos de Parâmetro**, **Nomes de Parâmetro**, **Valores de Parâmetro**, **Números de Linha** e **Deslocamentos de Byte**) clicando com o botão direito do mouse na janela **Pilha de Chamadas**.  
  
     Um realce azul ao redor de uma caixa indica que o thread atual é parte dessa caixa. O thread atual também é indicado pelo registro de ativação em negrito na dica de ferramenta. Se você clicar duas vezes no thread principal na janela Threads, poderá observar que o realce azul na janela **Pilhas Paralelas** se move adequadamente.  
  
     ![Realçado thread principal na janela pilhas paralelas](../debugger/media/pdb-walkthrough-1c.png "PDB_Walkthrough_1C")  
  
#### <a name="to-resume-execution-until-the-second-breakpoint"></a>Para retomar a execução até o segundo ponto de interrupção  
  
1. Para retomar a execução até que o segundo ponto de interrupção seja atingido, no menu **Depurar**, clique em **Continuar**. A ilustração a seguir mostra a árvore do thread no segundo ponto de interrupção.  
  
     ![Janela pilhas paralelas que mostra muitas ramificações](../debugger/media/pdb-walkthrough-2.png "PDB_Walkthrough_2")  
  
     No primeiro ponto de interrupção, quatro threads foram de S.A para S.B até o método S.C. Essas informações ainda estão visíveis na janela **Pilhas Paralelas**, mas os quatro threads progrediram mais. Um deles continuou até S.D e depois S.E. Outro continuou até S.F, S.G e S.H. Dois outros continuaram até S.I e S.J, e um deles foi até S.K e o outro continuou até o código externo de não usuário.  
  
     Você pode passar o mouse sobre o cabeçalho da caixa, por exemplo, **1 Thread** ou **2 Threads**, para ver as IDs dos threads. Você pode passar o mouse sobre registros de ativação para consultar as IDs de thread e outros detalhes do registro. O realce azul indica o thread atual e a seta amarela indica o registro de ativação ativo do thread atual.  
  
     O ícone de pano-threads (sobrepondo linhas onduladas azuis e vermelhas) indica os registros de ativação ativos dos threads não atuais. Na janela **Pilha de Chamadas**, clique duas vezes em S.B para mudar de registros. A janela **Pilhas Paralelas** indica o registro de ativação atual do thread atual usando um ícone de seta curva verde.  
  
     Na janela **Threads**, alterne entre threads e observe que a exibição na janela **Pilhas Paralelas** é atualizada.  
  
     Você pode alternar para outro thread ou para outro registro de outro thread usando o menu de atalho na janela **Pilhas Paralelas**. Por exemplo, clique com o botão direito do mouse em S.J, aponte para **Alternar para Quadro** e clique em um comando.  
  
     ![Caminho de execução de pilhas paralelas](../debugger/media/pdb-walkthrough-2b.png "PDB_Walkthrough_2B")  
  
     Clique com o botão direito do mouse em S.C e aponte para **Alternar para Quadro**. Um dos comandos tem uma marca de seleção que indica o registro de ativação do thread atual. Você pode alternar para esse registro do mesmo thread (apenas a seta verde se moverá) ou pode alternar para o outro thread (o realce azul também se moverá). A ilustração a seguir mostra o submenu.  
  
     ![Menu de pilhas com 2 opções em C, embora J seja o atual](../debugger/media/pdb-walkthrough-3.png "PDB_Walkthrough_3")  
  
     Quando um contexto de método estiver associado a apenas um registro de ativação, o cabeçalho da caixa exibirá **1 Thread** e você poderá mudar para ele clicando duas vezes nele. Se você clicar duas vezes em um contexto de método que tenha mais de 1 registro associado a ele, o menu será exibido automaticamente. Enquanto você passa o mouse sobre os contextos de método, observe o triângulo preto no lado direito. Um clique nesse triângulo também exibe o menu de atalho.  
  
     Para os aplicativos grandes que têm muitos threads, talvez seja conveniente se concentrar apenas em um subconjunto de threads. A janela **Pilhas Paralelas** pode exibir pilhas de chamadas apenas para threads sinalizados. Na barra de ferramentas, clique no botão **Mostrar Somente Sinalizados** ao lado da caixa de listagem.  
  
     ![Janela pilhas paralelas e dica de ferramenta vazias](../debugger/media/pdb-walkthrough-3a.png "PDB_Walkthrough_3A")  
  
     Em seguida, nos **Threads** janela, sinalize threads individualmente para ver a aparecem de suas pilhas de chamadas na **pilhas paralelas** janela. Para sinalizar threads, use o menu de atalho ou a primeira célula de um thread. Clique o **Mostrar somente sinalizados** botão de barra de ferramentas novamente para mostrar todos os threads.  
  
#### <a name="to-resume-execution-until-the-third-breakpoint"></a>Para retomar a execução até o terceiro ponto de interrupção  
  
1. Para retomar a execução até que o terceiro ponto de interrupção seja atingido, no menu **Depurar**, clique em **Continuar**.  
  
    Quando vários threads estão no mesmo método, mas o método não estava no início da pilha de chamadas, ele é exibido em caixas diferentes. Um exemplo no ponto de interrupção atual é S.L, que tem três threads e aparece em três caixas. Clique duas vezes em S.L.  
  
    ![Caminho de execução na janela pilhas paralelas](../debugger/media/pdb-walkthrough-3b.png "PDB_Walkthrough_3B")  
  
    Observe que S.L está em negrito nas outras duas caixas para que você possa ver onde mais ele aparece. Para saber quais registros chamam S.L e quais registros ele chama, clique no botão **Ativar/Desativar Exibição de Método** na barra de ferramentas. A ilustração a seguir mostra o modo de exibição do método as **pilhas paralelas** janela.  
  
    ![Exibição do método na janela pilhas paralelas](../debugger/media/pdw-walkthrough-4.png "PDW_Walkthrough_4")  
  
    Observe como o diagrama girou no método selecionado e o posicionou em sua própria caixa no meio da exibição. Os receptores e os chamadores aparecem nas partes superior e inferior. Clique no botão **Ativar/Desativar exibição de método** novamente para sair desse modo.  
  
    O menu de atalho da janela **Pilhas Paralelas** também tem os seguintes itens.  
  
   - **Exibição hexadecimal** alterna os números nas dicas de ferramenta entre decimais e hexadecimais.  
  
   - **Informações de carregamento de símbolo** e **configurações de símbolo** abrir as caixas de diálogo correspondente.  
  
   - **Ir para código-fonte** e **ir para desmontagem** navegar no editor para o método selecionado.  
  
   - **Mostrar Código Externo** exibe todos os registros, mesmo quando eles não estão no código do usuário. Tente verificar o diagrama se expande para acomodar os registros adicionais (que podem ser escurecidos porque você não tem símbolos para eles).  
  
     Quando houver diagramas grandes e você for para o próximo ponto de interrupção, talvez seja conveniente que o modo de exibição role até o registro de ativação ativo do thread atual; isto é, o thread que atingiu o ponto de interrupção primeiro. Na janela **Pilhas Paralelas**, verifique se a **Autorrolagem para Quadro de Pilha Atual** na barra de ferramentas está habilitada.  
  
     ![Rolagem automática na janela pilhas paralelas](../debugger/media/pdb-walkthrough-4a.png "PDB_Walkthrough_4A")  
  
2. Antes de continuar, na janela **Pilhas Paralelas**, role totalmente para a esquerda e para baixo.  
  
#### <a name="to-resume-execution-until-the-fourth-breakpoint"></a>Para retomar a execução até o quarto ponto de interrupção  
  
1. Para retomar a execução até que o quarto ponto de interrupção seja atingido, no menu **Depurar**, clique em **Continuar**.  
  
     Observe como o modo de exibição rolou automaticamente até o local certo. Alterne os threads na janela **Threads** ou alterne registros de ativação na janela **Pilha de Chamadas** e observe como a exibição sempre rola automaticamente até o registro correto. Desabilite a opção **Autorrolagem para Quadro de Ferramenta Atual** e veja a diferença.  
  
     A **Exibição Panorâmica** também é útil com diagramas grandes na janela **Pilhas Paralelas**. Você pode ver os **panorama** clicando no botão entre as barras de rolagem no canto inferior direito da janela, conforme mostrado na ilustração a seguir.  
  
     ![Vista de pássaro&#45;modo de exibição na janela pilhas paralelas de olho](../debugger/media/pdb-walkthrough-5.png "PDB_Walkthrough_5")  
  
     Você pode mover o retângulo para ver uma rápida panorâmica do diagrama.  
  
     Outra maneira de mover o diagrama em qualquer direção é clicar em uma área em branco do diagrama e arrastá-la até onde desejar.  
  
     Para ampliar ou reduzir o diagrama, mantenha pressionada a tecla CTRL enquanto move a roda do mouse. Como alternativa, clique no botão Aplicar Zoom na barra de ferramentas e use a ferramenta Zoom.  
  
     ![Ampliado pilhas na janela pilhas paralelas](../debugger/media/pdb-walkthrough-5a.png "PDB_Walkthrough_5A")  
  
     Você também pode exibir as pilhas na direção de cima para baixo em vez de na direção de baixo para cima clicando no menu **Ferramentas** e em **Opções** e selecionando ou desmarcando a opção no nó **Depuração**.  
  
2. Antes de continuar no menu **Depurar**, clique em **Parar Depuração** para terminar a execução.  
  
## <a name="using-the-parallel-tasks-window-and-the-tasks-view-of-the-parallel-stacks-window"></a>Usando a janela Tarefas Paralelas e o Modo de Exibição Tarefas na janela Pilhas Paralelas  
 Recomendamos que você conclua os procedimentos anteriores antes de continuar.  
  
#### <a name="to-restart-the-application-until-the-first-breakpoint-is-hit"></a>Para reiniciar o aplicativo até atingir o primeiro ponto de interrupção  
  
1. No menu **Depurar**, clique em **Iniciar Depuração** e aguarde até que o primeiro ponto de interrupção seja atingido.  
  
2. No menu **Depurar**, aponte para **Janelas** e, em seguida, clique em **Threads**. Encaixe a janela **Threads** na parte inferior do Visual Studio.  
  
3. No menu **Depurar**, aponte para **Janelas** e clique em **Pilha de Chamadas**. Encaixe a janela **Pilha de Chamadas** na parte inferior do Visual Studio.  
  
4. Clique duas vezes em um thread na janela **Threads** para torná-lo atual. Os threads atuais têm a seta amarela. Quando você altera o thread atual, as outras janelas são atualizadas. Em seguida, examinaremos tarefas.  
  
5. Sobre o **Debug** , aponte para **Windows** e, em seguida, clique em **tarefas paralelas**. A ilustração a seguir mostra a **tarefas paralelas** janela.  
  
     ![Quatro executando tarefas na janela tarefas paralelas](../debugger/media/pdw-walkthrough-6.png "PDW_Walkthrough_6")  
  
     Para cada tarefa em execução, você pode ler a ID, que é retornada pela propriedade do mesmo nome, a ID e o nome do thread que a executa, seu local (passar o mouse sobre ele exibe uma dica de ferramenta que tem a pilha de chamadas inteira). Além disso, na coluna **Tarefa**, você pode ver o método que foi passado na tarefa, em outras palavras, o ponto de partida.  
  
     Você pode classificar qualquer coluna. Observe o glifo de classificação que indica a coluna e a direção de classificação. Também é possível reorganizar as colunas arrastando-as para a esquerda ou a direita.  
  
     A seta amarela indica a tarefa atual. Você pode alternar tarefas clicando duas vezes em uma tarefa ou usando o menu de atalho. Quando você alterna tarefas, o thread subjacente se torna o atual e as outras janelas são atualizadas.  
  
     Quando você alterna manualmente de uma tarefa para outra, a seta amarela se move, mas uma seta branca ainda mostra a tarefa que causou a interrupção do depurador.  
  
#### <a name="to-resume-execution-until-the-second-breakpoint"></a>Para retomar a execução até o segundo ponto de interrupção  
  
1. Para retomar a execução até que o segundo ponto de interrupção seja atingido, no menu **Depurar**, clique em **Continuar**.  
  
     Anteriormente, o **Status** coluna mostrou todas as tarefas como em execução, mas agora duas tarefas estão aguardando. As tarefas podem ser bloqueadas por diversos motivos diferentes. Na coluna **Status**, passe o mouse sobre uma tarefa em espera para saber por que ela está bloqueada. Por exemplo, na ilustração, a tarefa 3 está aguardando a tarefa 4.  
  
     ![Duas tarefas em espera na janela tarefas paralelas](../debugger/media/pdb-walkthrough-7.png "PDB_Walkthrough_7")  
  
     A tarefa 4, por sua vez, está aguardando um monitor de propriedade do thread atribuído à tarefa 2.  
  
     ![Aguardando a tarefa e a dica de ferramenta na janela de tarefas](../debugger/media/pdb-walkthrough-7a.png "PDB_Walkthrough_7A")  
  
     Você pode sinalizar uma tarefa clicando no sinalizador na primeira coluna do **tarefas paralelas** janela.  
  
     Você pode usar a sinalização para controlar tarefas entre pontos de interrupção diferentes na mesma sessão de depuração ou para filtrar as tarefas cujas pilhas de chamadas são mostradas na janela **Pilhas Paralelas**.  
  
     Quando você usou a janela **Pilhas Paralelas** antes, os threads do aplicativo foram exibidos. Exiba a janela **Pilhas Paralelas** novamente, mas desta vez exiba as tarefas do aplicativo. Faça isso selecionando **Tarefas** na caixa no canto superior esquerdo. A ilustração a seguir mostra o Modo de Exibição de Tarefas.  
  
     ![Exibição na janela pilhas paralelas de threads](../debugger/media/pdb-walkthrough-8.png "PDB_Walkthrough_8")  
  
     Os threads que não estão executando tarefas no momento não são mostrados na Exibição de Tarefas da janela **Pilhas Paralelas**. Além disso, para os threads que executam tarefas, alguns registros de ativação que não são relevantes para tarefas são filtrados das partes superior e inferior da pilha.  
  
     Modo de exibição de **tarefas paralelas** janela novamente. Clique com o botão direito do mouse em qualquer cabeçalho de coluna para ver um menu de atalho da coluna.  
  
     ![Menu de exibição de atalho na janela tarefas paralelas](../debugger/media/pdb-walkthrough-8a.png "PDB_Walkthrough_8A")  
  
     Você pode usar o menu de atalho para adicionar ou remover colunas. Por exemplo, a coluna Appdomain não está selecionada; consequentemente, não é exibida na lista. Clique em **Pai**. A coluna **Pai** aparece sem valores para as quatro tarefas.  
  
#### <a name="to-resume-execution-until-the-third-breakpoint"></a>Para retomar a execução até o terceiro ponto de interrupção  
  
1. Para retomar a execução até que o terceiro ponto de interrupção seja atingido, no menu **Depurar**, clique em **Continuar**.  
  
     Uma nova tarefa, tarefa 5, está sendo executada e a tarefa 4 está aguardando. Veja o motivo passando o mouse sobre a tarefa em espera na janela **Status**. No **pai** coluna, observe que a tarefa 4 é o pai da tarefa 5.  
  
     Para visualizar melhor a relação pai-filho, clique com botão direito do **pai** cabeçalho de coluna e clique **exibição de pai-filho**. Você verá a ilustração a seguir.  
  
     ![Pai&#45;exibição-filho na janela tarefas paralelas](../debugger/media/pdb-walkthrough-9.png "PDB_Walkthrough_9")  
  
     Observe que as tarefas 4 e 5 estão em execução no mesmo thread. Essas informações não são exibidas na **Threads** janela; vendo aqui é outro benefício da **tarefas paralelas** janela. Para confirmar isso, exiba a janela **Pilhas Paralelas**. Verifique se você está exibindo **Tarefas**. Localize as tarefas 4 e 5 clicando duas vezes na **tarefas paralelas** janela. Quando você fizer isso, o realce azul na janela **Pilhas Paralelas** será atualizado. Você também pode localizar as tarefas 4 e 5 examinando as dicas de ferramenta na janela **Pilhas Paralelas**.  
  
     ![Modo de exibição na janela pilhas paralelas de tarefas](../debugger/media/pdb-walkthrough-9a.png "PDB_Walkthrough_9A")  
  
     Na janela **Pilhas Paralelas**, clique com o botão direito do mouse em S.P e clique em **Ir para Thread**. A janela alterna para o Modo de Exibição de Threads e o registro correspondente está na exibição. Você pode ver as duas tarefas no mesmo thread.  
  
     ![Realçado thread na exibição de threads](../debugger/media/pdb-walkthrough-9b.png "PDB_Walkthrough_9B")  
  
     Esse é outro benefício da Exibição de Tarefas na janela **Pilhas Paralelas**, em comparação com a janela **Threads**.  
  
#### <a name="to-resume-execution-until-the-fourth-breakpoint"></a>Para retomar a execução até o quarto ponto de interrupção  
  
1. Para retomar a execução até que o terceiro ponto de interrupção seja atingido, no menu **Depurar**, clique em **Continuar**. Clique no cabeçalho de coluna **ID** para classificar por ID. Você verá a ilustração a seguir.  
  
     ![Quatro estados na janela pilhas paralelas de tarefas](../debugger/media/pdb-walkthrough-10.png "PDB_Walkthrough_10")  
  
     Como a tarefa 5 foi concluída, ele não é mais exibida. Se esse não for o caso no seu computador e o deadlock não for mostrado, volte uma etapa pressionando F11.  
  
     As tarefas 3 e 4 estão aguardando uma pela outra e estão bloqueadas. Também há 5 novas tarefas que são filhos da tarefa 2 e estão agendadas agora. As tarefas agendadas são aquelas iniciadas no código mas que ainda não foram executadas. Portanto, as colunas **Local** e **Atribuição de Thread** estão vazias.  
  
     Exiba a janela **Pilhas Paralelas** novamente. O cabeçalho de cada caixa tem uma dica de ferramenta que mostra as IDs e os nomes de thread. Alterne para a Exibição de Tarefas na janela **Pilhas Paralelas**. Passe o mouse sobre um cabeçalho para ver o nome, a ID e o status da tarefa, como mostra a ilustração a seguir.  
  
     ![Dica de ferramenta de cabeçalho na janela pilhas paralelas](../debugger/media/pdb-walkthrough-11.png "PDB_Walkthrough_11")  
  
     Você pode agrupar as tarefas por coluna. No **tarefas paralelas** janela, com o botão direito do **Status** cabeçalho de coluna e clique **Agrupar por Status**. A ilustração a seguir mostra a **tarefas paralelas** janela agrupados por status.  
  
     ![Agrupados tarefas na janela tarefas paralelas](../debugger/media/pdb-walkthrough-12.png "PDB_Walkthrough_12")  
  
     Também é possível agrupar por qualquer outra coluna. Agrupando tarefas, você pode se concentrar em um subconjunto de tarefas. Cada grupo recolhível tem uma contagem de itens que são agrupados. Você também pode sinalizar rapidamente todos os itens no grupo clicando o **sinalizador** botão à direita do **Collapse** botão.  
  
     ![Agrupados pilhas na janela pilhas paralelas](../debugger/media/pdb-walkthrough-12a.png "PDB_Walkthrough_12A")  
  
     O último recurso do **tarefas paralelas** janela examinar é o menu de atalho é exibido quando o botão direito do mouse uma tarefa.  
  
     ![Menu de atalho na janela tarefas paralelas](../debugger/media/pdb-walkthrough-12b.png "PDB_Walkthrough_12B")  
  
     O menu de atalho exibe comandos diferentes, dependendo do status da tarefa. Os comandos podem incluir **Copiar**, **Selecionar Tudo**, **Exibição Hexadecimal**, **Mudar para tarefas**, **Congelar Thread Atribuído**, **Congelar Todos os Threads Menos Este**, **Descongelar Thread Atribuído** e **Sinalizador**.  
  
     Você pode congelar o thread subjacente de uma tarefa, ou tarefas, ou pode congelar todos os threads exceto o atribuído. Um thread congelado é representado na **tarefas paralelas** janela como ela está a **Threads** janela, por um azul *pausar* ícone.  
  
## <a name="summary"></a>Resumo  
 Este passo a passo demonstrou as janelas do depurador **Tarefas Paralelas** e **Pilhas Paralelas**. Use essas janelas em projetos reais que utilizam código multi-threaded. Você pode examinar o código paralelo escrito no C++, no C# ou no Visual Basic.  
  
## <a name="see-also"></a>Consulte também  
 [Depurar aplicativos multithread](../debugger/walkthrough-debugging-a-parallel-application.md)   
 [Noções básicas do depurador](../debugger/debugger-basics.md)   
 [Depurando código gerenciado](../debugger/debugging-managed-code.md)   
 [Programação paralela](http://msdn.microsoft.com/library/4d83c690-ad2d-489e-a2e0-b85b898a672d)   
 [Tempo de Execução de Simultaneidade](http://msdn.microsoft.com/library/874bc58f-8dce-483e-a3a1-4dcc9e52ed2c)   
 [Usando a janela Pilhas Paralelas](../debugger/using-the-parallel-stacks-window.md)   
 [Usando a janela Tarefas](../debugger/using-the-tasks-window.md)
