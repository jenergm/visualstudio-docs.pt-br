---
title: Comutador&lt;T&gt; Designer de atividade | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.ModelItemKeyValuePair.UI
- System.Activities.Statements.Switch`1.UI
ms.assetid: 18a6c96e-49a9-4356-ab61-fbd7e3ab44bb
caps.latest.revision: 3
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7e2baacdfb35e2360a0e9dcc56891cadbe7d3ff3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58927718"
---
# <a name="switchlttgt-activity-designer"></a>Comutador&lt;T&gt; Designer de atividade
A atividade de <xref:System.Activities.Statements.Switch%601> avalia uma expressão especificada e executa a atividade de uma coleção de atividades cuja chave associado corresponde ao valor obtido de avaliação.  
  
 O **comutador\<T >** designer de atividade é usado para criar e configurar um <xref:System.Activities.Statements.Switch%601> atividade no [!INCLUDE[wfd1](../includes/wfd1-md.md)].  
  
## <a name="the-switchtactivity"></a>O comutador\<T > atividade  
 Uma atividade de <xref:System.Activities.Statements.Switch%601> contém <xref:System.Activities.Statements.Switch%601.Expression%2A> e um dicionário de <xref:System.Activities.Statements.Switch%601.Cases%2A>. Cada caso o dicionário consiste em um par que contém um *chave* e uma atividade que serve como correspondente *valor*. A atividade de <xref:System.Activities.Statements.Switch%601> avalia <xref:System.Activities.Statements.Switch%601.Expression%2A> e o compara com cada uma das chaves. Se uma correspondência for encontrada, a atividade correspondente é executada. Somente uma correspondência é possível porque as chaves de dicionário devem ser exclusivos de acordo com o tipo de igualdade definido pelo comparer de igualdade de dicionário. Se nenhuma correspondência for encontrada, a atividade de <xref:System.Activities.Statements.Switch%601.Default%2A> é executada.  
  
## <a name="how-to-use-the-switcht-activity-designer"></a>Como usar a opção\<T > Designer de atividade  
 O **comutador\<T >** designer de atividade pode ser encontrado no **fluxo de controle** categoria do **caixa de ferramentas**, que é acessado clicando-se a **Caixa de ferramentas** guia o [!INCLUDE[wfd2](../includes/wfd2-md.md)] (como alternativa, selecione **barra de ferramentas** do **exibição** menu, ou CTRL + ALT + X.) Após solto na [!INCLUDE[wfd2](../includes/wfd2-md.md)], ele exibe a **selecionar tipos** caixa de diálogo para permitir que o usuário especifique o tipo genérico *T* usados em <xref:System.Activities.Statements.Switch%601> atividade. O valor padrão é **Int32**. Uma vez para o tipo genérico *T* tiver sido selecionado, um **Switch\<T >** designer é adicionado ao designer de fluxo de trabalho.  
  
 A seguir estão as propriedades de **comutador\<T >** designer. Todas essas propriedades podem ser editadas na grade de propriedade. Alguns deless também podem ser editados na superfície de designer.  
  
 A tabela a seguir mostra as propriedades mais úteis de <xref:System.Activities.Statements.Switch%601> e descreve como elas são usadas no designer.  
  
|Nome da Propriedade|Necessária|Uso|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Especifica o nome amigável do designer de atividade de <xref:System.Activities.Statements.Switch%601> . O valor padrão é o comutador\<Int32 >. O valor pode ser editado na **propriedades** janela ou diretamente no cabeçalho de designer.<br /><br /> Embora não seja necessário <xref:System.Activities.Activity.DisplayName%2A> restrita, é uma prática recomendada usar um.|  
|<xref:System.Activities.Statements.Switch%601.Expression%2A>|verdadeiro|Especifica a expressão usada para comparar as chaves na coleção dos casos para determinar que casos a executar.|  
|<xref:System.Activities.Statements.Switch%601.Default%2A>||Especifica a atividade executada se nenhuma correspondência for encontrada. Clique o **adicionar uma atividade** botão no designer para abrir o **padrão** caixa em que a atividade pode ser descartada.|  
|<xref:System.Activities.Statements.Switch%601.Cases%2A>||Especifica os casos a ser avaliado. Para adicionar um caso, clique o **adicionar novo caso** botão na parte inferior da **Switch\<T >** designer. O botão muda para uma caixa de texto (caixa de combinação se o tipo genérico selecionado quando o acréscimo da opção\<T > é a cadeia de caracteres ou Enum). Depois de adicionar uma chave na **caso o valor** caixa, a área dos casos expande e uma atividade pode ser descartada onde o texto de dica "Soltar atividade aqui" para definir a lógica de execução para o caso.|  
  
 Vários casos podem ser adicionados como as chaves dos casos não são duplicadas. Se não, uma caixa de diálogo de erro exibe relatar a chave especificada dos casos já existe e que você deve escolher uma chave diferente. No **comutador\<T >** designer, apenas uma área dos casos pode ser no modo de exibição expandido por vez. Se uma área dos casos está na visualização recolhida, clique na área dos casos para expandi-la. Observe que para casos, recolhidos de designer mostra o nome para exibição de atividade dentro dos casos no lado direito se houver. Caso contrário, ele mostra a **adicionar uma atividade** botão que expande o caso se você clicar nele e permite que você adicione uma atividade.  
  
 Clique na chave de casos existentes altera a chave de um rótulo em uma caixa de texto para que você possa editar a chave dos casos.  
  
 Existem 2 maneiras de excluir casos:  
  
1. Selecione os casos e excluir-los.  
  
2. Selecione o botão direito do mouse nesse caso, para exibir o menu de contexto e selecione **excluir**.  
  
   Observe que você deve selecionar os casos os próprios para excluir. Selecionando e excluindo a atividade dentro de um caso exclui somente a atividade não os casos.  
  
## <a name="see-also"></a>Consulte também  
 [Fluxo de Controle](../workflow-designer/control-flow-activity-designers.md)