---
title: 'Como: Preencher planilhas com dados de um banco de dados'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets [Office development in Visual Studio], populating
- databases [Office development in Visual Studio], populating worksheets
- data [Office development in Visual Studio], adding to worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 67c12843d00bf8d5af51fa7af3175077527afa58
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60079130"
---
# <a name="how-to-populate-worksheets-with-data-from-a-database"></a>Como: Preencher planilhas com dados de um banco de dados

Você pode acessar dados em projetos do Office em nível de documento da mesma forma que você acessar dados em projetos do Windows Forms. Usar as mesmas ferramentas e código para trazer os dados para sua solução, e você pode até mesmo usar controles dos Windows Forms para exibir os dados. Além disso, você pode tirar proveito dos controles, chamados de controles de host, que são objetos nativos no Microsoft Office Excel que foram aprimorados com eventos e a capacidade de associação de dados. Para obter mais informações, consulte [hospedam itens e visão geral dos controles](../vsto/host-items-and-host-controls-overview.md).

[!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

O exemplo a seguir mostra como adicionar controles ligados a dados em projetos de nível de documento usando um designer. Para obter um exemplo de como adicionar controles ligados a dados em projetos de nível de aplicativo em tempo de execução, consulte [passo a passo: Associação de dados complexos no projeto do suplemento do VSTO](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md).

![link para vídeo](../vsto/media/playvideo.gif "link para vídeo") para uma demonstração em vídeo relacionada, consulte [como fazer: Transferir dados para uma planilha do Excel? ](http://go.microsoft.com/fwlink/?LinkID=130277), e [como fazer: Consumir dados do banco de dados no Excel? ](http://go.microsoft.com/fwlink/?LinkID=130287).

## <a name="add-a-data-bound-control-to-a-worksheet-at-design-time"></a>Adicione um controle associado a dados para uma planilha em tempo de design

### <a name="to-populate-a-worksheet-with-data-from-a-database"></a>Para popular uma planilha com os dados de um banco de dados

1. Abra um projeto de nível de documento do Excel no Visual Studio, com o planilha aberto no designer.

2. Abra o **fontes de dados** janela e criar uma fonte de dados para seu projeto. Para obter mais informações, consulte [adicionar novas conexões](../data-tools/add-new-connections.md).

3. Arraste o campo ou uma tabela que você deseja a partir de **fontes de dados** janela à sua planilha.

Um dos seguintes controles é criado na planilha:

- Se você arrastar um campo, um <xref:Microsoft.Office.Tools.Excel.NamedRange> controle é criado na planilha. Para obter mais informações, consulte [controle NamedRange](../vsto/namedrange-control.md).

- Se você arrastar uma tabela, um <xref:Microsoft.Office.Tools.Excel.ListObject> controle é criado na planilha. Para obter mais informações, consulte [controle ListObject](../vsto/listobject-control.md).

Você pode adicionar um controle diferente, selecionando a tabela ou campo na **fontes de dados** janela e, em seguida, escolhendo um controle diferente na lista suspensa.

## <a name="objects-in-the-project"></a>Objetos do projeto

Além do controle, os seguintes objetos de dados são automaticamente adicionados ao seu projeto:

- Um dataset tipado que encapsula as tabelas de dados para o qual você se conectou no banco de dados. Para obter mais informações, consulte [ferramentas de conjunto de dados no Visual Studio](../data-tools/dataset-tools-in-visual-studio.md).

- Um <xref:System.Windows.Forms.BindingSource> que conecta-se com o controle para o conjunto de dados tipado. Para obter mais informações, consulte [visão geral do componente BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-overview).

- Um TableAdapter que conecta-se o conjunto de dados tipado para o banco de dados. Para obter mais informações, consulte [visão geral de TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).

- Um TableAdapterManager, que é usado para coordenar a adaptadores de tabela no conjunto de dados para habilitar as atualizações hierárquicas. Para obter mais informações, consulte [atualização hierárquica](../data-tools/hierarchical-update.md) e [TableAdapterManager reference](../data-tools/fill-datasets-by-using-tableadapters.md#tableadaptermanager-reference).

Quando você executa o projeto, o controle exibe o primeiro registro na fonte de dados. Você pode usar o <xref:System.Windows.Forms.BindingSource> para permitir aos usuários percorrer os registros.

### <a name="to-scroll-through-the-records"></a>Para percorrer os registros

- Use <xref:System.Windows.Forms.BindingSource> métodos como <xref:System.Windows.Forms.BindingSource.MoveNext%2A> e <xref:System.Windows.Forms.BindingSource.MovePrevious%2A>.

Para obter informações sobre como enviar atualizações para o conjunto de dados tipado e o banco de dados, consulte [como: Atualizar uma fonte de dados com dados de um controle de host](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).

## <a name="see-also"></a>Consulte também

- [Associar dados a controles em soluções do Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Adicionar novas fontes de dados](../data-tools/add-new-data-sources.md)
- [Associando controles do Windows Forms a dados no Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Como: Preencher documentos com dados de objetos](../vsto/how-to-populate-documents-with-data-from-objects.md)
- [Como: Preencher documentos com dados de um banco de dados](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [Como: Preencher documentos com dados de serviços](../vsto/how-to-populate-documents-with-data-from-services.md)
- [Como: Atualizar uma fonte de dados com dados de um controle de host](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Como faço Transferir dados para uma planilha do Excel](http://go.microsoft.com/fwlink/?LinkID=130277)
- [Como faço Consumir dados do banco de dados no Excel?](http://go.microsoft.com/fwlink/?LinkID=130287)