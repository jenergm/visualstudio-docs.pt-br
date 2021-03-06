---
title: Desativar restrições ao preencher um conjunto de dados | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
f1_keywords:
- DataRow.BeginEdit
- DataRow.EndEdit
- DataRow.CancelEdit
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- updating datasets, constraints
- constraints [Visual Basic], datasets
- datasets [Visual Basic], constraints
- constraints [Visual Basic], suspending during dataset update
ms.assetid: 553f7d0c-2faa-4c17-b226-dd02855bf1dc
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8719b893bc8cb47f8a2d7b75b43592187c198289
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60057681"
---
# <a name="turn-off-constraints-while-filling-a-dataset"></a>Desabilitar restrições ao preencher um conjunto de dados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Se um conjunto de dados contiver restrições (como restrições de chave estrangeira), theycan gerar erros relacionados a ordem de operações que são executadas com o conjunto de dados. Por exemplo, carregamento de registros filho antes de registros de pais loadingrelated pode violar uma restrição e causar um erro. Assim que você carrega um registro filho, a restrição verifica o registro pai relacionado e gera um erro.  
  
 Se não houver nenhum mecanismo para permitir a suspensão de restrição temporária, um erro seria gerado toda vez que você tentou carregar um registro na tabela filho. Outra maneira para suspender todas as restrições em um conjunto de dados é com o <xref:System.Data.DataRow.BeginEdit%2A>, e <xref:System.Data.DataRow.EndEdit%2A> propriedades.  
  
> [!NOTE]
>  Eventos de validação (por exemplo, <xref:System.Data.DataTable.ColumnChanging> e<xref:System.Data.DataTable.RowChanging>) não serão gerados quando as restrições estão desativadas.  
  
### <a name="to-suspend-update-constraints-programmatically"></a>Para suspender restrições de atualização por meio de programação  
  
- O exemplo a seguir mostra como desativar temporariamente a restrição de verificação em um conjunto de dados:  
  
     [!code-csharp[VbRaddataEditing#10](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#10)]
     [!code-vb[VbRaddataEditing#10](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#10)]  
  
### <a name="to-suspend-update-constraints-using-the-dataset-designer"></a>Para suspender restrições de atualização usando o Designer de conjunto de dados  
  
1. Abra seu conjunto de dados no Designer de conjunto de dados. Para obter mais informações, confira [Como: Abra um conjunto de dados no Designer de conjunto de dados](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3).  
  
2. No **propriedades** janela, defina as <xref:System.Data.DataSet.EnforceConstraints%2A> propriedade `false`.  
  
## <a name="see-also"></a>Consulte também  
 [Preencher conjuntos de dados usando TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [Relacionamentos em conjuntos de dados](../data-tools/relationships-in-datasets.md)
