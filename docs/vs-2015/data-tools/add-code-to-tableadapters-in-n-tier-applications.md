---
title: Adicionar código a TableAdapters em aplicativos de n camadas | Microsoft Docs
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
- TableAdapters, n-tier applications
- n-tier applications, extending TableAdapters
ms.assetid: dafac00e-df9d-4d4a-95a6-e34b4d099425
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3c3ddcb99163fe3548f020094647566c1779f5d9
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60115361"
---
# <a name="add-code-to-tableadapters-in-n-tier-applications"></a>Adicionar código a TableAdapters em aplicativos de n camadas
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode estender a funcionalidade de um `TableAdapter` criando um arquivo de classe parcial para o `TableAdapter` e adicionar código a ele (em vez de adicionar código para o *DatasetName*. Arquivo do DataSet). Classes parciais permitem codificar uma classe específica a ser dividido entre vários arquivos físicos. Para obter mais informações, consulte [parcial](http://msdn.microsoft.com/library/7adaef80-f435-46e1-970a-269fff63b448) ou [partial (tipo)](http://msdn.microsoft.com/library/27320743-a22e-4c7b-b0b3-53afe3607334).  
  
 O código que define uma `TableAdapter` é gerado sempre que forem feitas alterações a `TableAdapter`. Esse código também é gerado quando as alterações são feitas durante a execução de qualquer assistente que modifica a configuração do `TableAdapter`. Para impedir que seu código seja excluído durante a regeneração de um `TableAdapter`, adicione código ao arquivo de classe parcial do `TableAdapter`.  
  
 Por padrão, após você separar o conjunto de dados e `TableAdapter` código, o resultado é um arquivo de classe distintas em cada projeto. O projeto original tem um arquivo chamado *DatasetName*. VB (ou *DatasetName*. Designer.cs) que contém o `TableAdapter` código. O projeto que é designado na **projeto Dataset** propriedade tem um arquivo chamado *DatasetName*. DataSet.Designer.vb (ou *DatasetName*. DataSet.Designer.cs) que contém o código do conjunto de dados.  
  
> [!NOTE]
> Quando você separa os conjuntos de dados e `TableAdapter`s (definindo o **projeto DataSet** propriedade), classes parciais do conjunto de dados existentes no projeto não serão movidas automaticamente. Classes parciais do conjunto de dados existente devem ser movidas manualmente para o projeto de conjunto de dados.  
  
> [!NOTE]
> O Designer de conjunto de dados fornece funcionalidade para gerar <xref:System.Data.DataTable.ColumnChanging> e <xref:System.Data.DataTable.RowChanging> manipuladores de eventos quando a validação é necessária. Para obter mais informações, consulte [adicionar validação a um conjunto de dados de n camadas](../data-tools/add-validation-to-an-n-tier-dataset.md).  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-add-user-code-to-a-tableadapter-in-an-n-tier-application"></a>Para adicionar o código do usuário a um TableAdapter em um aplicativo de n camadas  
  
1. Localize o projeto que contém o arquivo. xsd (o conjunto de dados).  
  
2. Clique duas vezes o **. xsd** arquivo para abrir o conjunto de dados.  
  
3. Clique com botão direito do `TableAdapter` que você deseja adicionar código para e, em seguida, selecione**Exibir código**.  
  
     Uma classe parcial é criada e é aberto no Editor de códigos.  
  
4. Adicione o código dentro da declaração de classe parcial.  
  
5. O exemplo a seguir mostra onde adicionar código para o `CustomersTableAdapter` no `NorthwindDataSet`:  
  
    ```vb  
    Partial Public Class CustomersTableAdapter  
        ' Add code here to add functionality   
        ' to the CustomersTableAdapter.  
    End Class  
    ```  
  
    ```csharp  
    public partial class CustomersTableAdapter  
    {  
        // Add code here to add functionality  
        // to the CustomersTableAdapter.  
    }  
    ```  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral dos aplicativos de dados de N camadas](../data-tools/n-tier-data-applications-overview.md)   
 [Adicione o código a conjuntos de dados em aplicativos de n camadas](../data-tools/add-code-to-datasets-in-n-tier-applications.md)   
 [TableAdapters](http://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364)   
 [Visão geral de TableAdapterManager](http://msdn.microsoft.com/library/33076d42-6b41-491a-ac11-6c6339aea650)   
 [Visão geral de atualização hierárquica](http://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6)