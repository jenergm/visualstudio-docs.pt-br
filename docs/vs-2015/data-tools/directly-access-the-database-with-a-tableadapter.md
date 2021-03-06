---
title: Acessar diretamente o banco de dados com um TableAdapter | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- databases [Visual Basic], accessing with a TableAdapter
- DBDirect methods
- datasets [Visual Basic], adding to projects
- data [Visual Studio], saving
- TableAdapter.Delete method
- GenerateDbDirectMethods property
- TableAdapter.Insert method
- TableAdapter.GenerateDBDirectMethods property
- TableAdapter.Update method
- saving data
- TableAdapters
ms.assetid: 012c5924-91f7-4790-b2a6-f51402b7014b
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 079264d2687d382aa79e526d829687f2a60f6882
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60106625"
---
# <a name="directly-access-the-database-with-a-tableadapter"></a>Acessar o banco de dados diretamente com um TableAdapter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Além de `InsertCommand`, `UpdateCommand`, e `DeleteCommand`, TableAdapters são criados com métodos que podem ser executados diretamente no banco de dados. Esses métodos (`TableAdapter.Insert`, `TableAdapter.Update`, e `TableAdapter.Delete`) pode ser chamado para manipular os dados diretamente no banco de dados.  
  
 Se você não quiser criar esses métodos diretos, defina o TableAdapter `GenerateDbDirectMethods` propriedade para `false` na **propriedades** janela. Se todas as consultas forem adicionadas a um TableAdapter, além da consulta principal do TableAdapter, eles são consultas autônomas que não geram esses métodos DbDirect.  
  
## <a name="sendcommandsdirectly-to-a-database"></a>Sendcommandsdirectly para um banco de dados  
 Chame o método TableAdapter DbDirect que executa a tarefa que você está tentando realizar.  
  
#### <a name="to-insert-new-records-directly-into-a-database"></a>Para inserir novos registros diretamente em um banco de dados  
  
- Chame o TableAdapter `Insert` método, passando os valores para cada coluna como parâmetros. O procedimento a seguir usa o `Region` um exemplo de tabela no databaseas a Northwind.  
  
    > [!NOTE]
    >  Se você não tiver uma instância disponível, crie uma instância do TableAdapter que você deseja usar.  
  
     [!code-csharp[VbRaddataSaving#15](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#15)]
     [!code-vb[VbRaddataSaving#15](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#15)]  
  
#### <a name="to-update-records-directly-in-a-database"></a>Para atualizar registros diretamente em um banco de dados  
  
- Chame o TableAdapter `Update` método, passando os valores novos e originais para cada coluna como parâmetros.  
  
    > [!NOTE]
    >  Se você não tiver uma instância disponível, crie uma instância do TableAdapter que você deseja usar.  
  
     [!code-csharp[VbRaddataSaving#18](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#18)]
     [!code-vb[VbRaddataSaving#18](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#18)]  
  
#### <a name="to-delete-records-directly-from-a-database"></a>Para excluir registros diretamente de um banco de dados  
  
- Chame o TableAdapter `Delete` método, passando os valores para cada coluna como parâmetros do `Delete` método. O procedimento a seguir usa o `Region` um exemplo de tabela no databaseas a Northwind.  
  
    > [!NOTE]
    >  Se você não tiver uma instância disponível, crie uma instância do TableAdapter que você deseja usar.  
  
     [!code-csharp[VbRaddataSaving#21](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#21)]
     [!code-vb[VbRaddataSaving#21](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Consulte também  
 [Preencher conjuntos de dados usando TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)
