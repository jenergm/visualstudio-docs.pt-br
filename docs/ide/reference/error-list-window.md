---
title: Janela Lista de Erros
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ErrorList
helpviewer_keywords:
- Task List
- build errors
- Error List window
- errors [Visual Studio], Error List window
ms.assetid: b7f6d45a-733b-4ad8-bc2f-737a37509e56
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 603faab80e185e7d22cba1ee544502d790afcdc0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62790853"
---
# <a name="error-list-window"></a>Janela Lista de Erros

> [!NOTE]
> A **Lista de Erros** exibe informações sobre uma mensagem de erro específica. Copie o número do erro ou o texto da cadeia de caracteres de erro da Janela de **Saída**. Para exibir a Janela de **Saída**, pressione **Ctrl**+**Alt**+**O**. Confira [Janela de Saída](../../ide/reference/output-window.md).

A janela **Lista de Erros** permite que você execute as seguintes tarefas:

- Exibir os erros, os avisos e as mensagens produzidas durante a escrita do código.

- Localizar erros de sintaxe observados pelo IntelliSense.

- Localizar erros de implantação, determinados erros da Análise Estática e erros detectados durante a aplicação de políticas de Modelo Empresarial.

- Clicar duas vezes em uma entrada de mensagem de erro para abrir o arquivo em que ocorre o problema e ir até o local do erro.

- Filtrar quais entradas são exibidas e quais colunas de informações são exibidas para cada entrada.

- Pesquisar termos específicos e definir o escopo da pesquisa para apenas o projeto ou o documento atual.

Para exibir a **Lista de Erros**, escolha **Exibir** > **Lista de Erros** ou pressione **Ctrl**+**\\**+**E**.

É possível escolher as guias **Erros**, **Avisos** e **Mensagens** para ver níveis diferentes de informações.

Para classificar a lista, clique em um cabeçalho de coluna. Para classificar novamente por uma coluna adicional, mantenha pressionada a tecla **Shift** e clique em outro cabeçalho de coluna. Para selecionar quais colunas são exibidas e ocultadas, escolha **Mostrar Colunas** no menu de atalho. Para alterar a ordem na qual as colunas são exibidas, arraste um cabeçalho de coluna para a esquerda ou direita.

## <a name="error-list-filters"></a>Filtros da Lista de Erros

Há dois tipos de filtro em duas caixas suspensas, uma do lado direito da barra de ferramentas e outra à esquerda da barra de ferramentas. A lista suspensa do lado esquerdo da barra de ferramentas especifica o conjunto de arquivos de código a ser usado (**Solução Inteira**, **Documentos Abertos**, **Projeto Atual**, **Documento Atual**).

É possível restringir o escopo da pesquisa para analisar e tomar decisões sobre grupos de erros. Por exemplo, talvez você deseje se concentrar em erros básicos que estão impedindo a compilação de um projeto. As opções de escopo incluem:

1. **Documentos Abertos**: Mostre erros, avisos e mensagens para os documentos abertos.

2. **Projeto Atual**: Mostre erros, avisos e mensagens do projeto do documento atualmente selecionado no **Editor** ou o projeto selecionado no **Gerenciador de Soluções**.

    > [!NOTE]
    > A lista filtrada de erros, avisos e mensagens será alterada se o projeto do documento selecionado atualmente for diferente do projeto selecionado no **Gerenciador de Soluções**.

3. **Documento Atual**: Mostre erros, avisos e mensagens para o documento atualmente selecionado no **Editor** ou no **Gerenciador de Soluções**.

Se um filtro estiver aplicado no momento para o resultado da pesquisa, o nome do filtro será exibido na barra de título **Lista de Erros**. Em seguida, os botões **Erros**, **Avisos** e **Mensagens** exibem o número de itens filtrados mostrados junto com o número total de itens. Por exemplo, os botões mostram "x de y Erros". Se nenhum filtro for aplicado, a barra de título indicará apenas a “Lista de Erros”.

A lista no lado direito da barra de ferramentas especifica se serão mostrados os erros do build (os erros resultantes de uma operação de build), do IntelliSense (erros detectados antes da execução de um build) ou ambos.

## <a name="search"></a>Pesquisar

Use a caixa de texto **Pesquisar Lista de Erros** no lado direito da barra de ferramentas **Lista de Erros** para encontrar erros específicos na lista de erros. É possível pesquisar em qualquer coluna visível na lista de erros e os resultados da pesquisa são sempre classificados de acordo com a coluna que tem a prioridade de classificação, em vez da consulta ou do filtro aplicado. Se você escolher a tecla **Esc** enquanto o foco estiver na **Lista de Erros**, será possível limpar o termo de pesquisa e os resultados da pesquisa filtrados. Você também pode clicar no **X** no lado direito da caixa de texto para desmarcá-la.

## <a name="save"></a>Salvar

É possível copiar a lista de erros e salvá-la em um arquivo. Selecione os erros que você deseja copiar, clique com o botão direito do mouse na seleção e, em seguida, no menu de contexto, selecione **Copiar**. Depois é possível colar os erros em um arquivo. Se você colar os erros em uma planilha do Excel, os campos serão exibidos como colunas diferentes.

## <a name="ui-element-list"></a>Lista de elementos da interface de usuário

Severidade

Exibe os diferentes tipos da entrada **Lista de Erros** (**Erro**, **Mensagem**, **Aviso**, **Aviso [ativo]**, **Aviso [inativo]**).

Código

Exibe o código de erro.

Descrição

Exibe o texto da entrada.

Projeto

Exibe o nome do projeto atual.

Arquivo

Exibe o nome do arquivo.

Linha

Exibe a linha em que ocorre o problema.