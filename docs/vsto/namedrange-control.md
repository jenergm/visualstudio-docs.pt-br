---
title: Controle NamedRange
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.Range
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, named
- NamedRange control, events
- NamedRange control, data binding
- NamedRange control
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f5d6c78f7d5c931272bb66b2706d3b5e531785cc
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60062632"
---
# <a name="namedrange-control"></a>Controle NamedRange
  O <xref:Microsoft.Office.Tools.Excel.NamedRange> controle é um intervalo que tem um nome exclusivo, expõe eventos e pode ser associado a dados. Para obter mais informações, consulte [visão geral do modelo de objeto do Excel](../vsto/excel-object-model-overview.md).

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="create-the-control"></a>Criar o controle
 Você pode adicionar <xref:Microsoft.Office.Tools.Excel.NamedRange> controles a uma planilha do Microsoft Office Excel em tempo de design ou em tempo de execução no nível de documento.

 Você pode adicionar <xref:Microsoft.Office.Tools.Excel.NamedRange> controles a uma planilha em tempo de execução em um suplemento do VSTO. Para obter mais informações, confira [Como: Adicionar controles NamedRange a planilhas](../vsto/how-to-add-namedrange-controls-to-worksheets.md).

> [!NOTE]
>  Por padrão, criados dinamicamente intervalos nomeados não são mantidos na planilha que os controles de host quando a planilha é fechada. Para obter mais informações, consulte [adicionar controles a documentos do Office em tempo de execução](../vsto/adding-controls-to-office-documents-at-run-time.md).

 <xref:Microsoft.Office.Tools.Excel.NamedRange> controles somente podem consistir em intervalos de planilhas específicas. <xref:Microsoft.Office.Tools.Excel.NamedRange> controles não podem ter nomes relativos que se aplicam a todas as planilhas, e eles não podem consistir em intervalos que abrangem duas ou mais planilhas em uma pasta de trabalho (intervalos 3D).

## <a name="bind-data-to-the-control"></a>Associar dados ao controle
 Um intervalo nomeado parece ser um bom candidato para a associação de dados complexos, pois ele pode ter muitas células; No entanto, um intervalo é simplesmente uma coleção de células que não pode ser facilmente mapeados para uma determinada coluna de um conjunto de dados. Portanto, <xref:Microsoft.Office.Tools.Excel.NamedRange> controles dão suporte apenas a associação de dados simples. O <xref:Microsoft.Office.Tools.Excel.ListObject> controle pode ser usado para associação de dados complexos. Para obter mais informações, consulte [controle ListObject](../vsto/listobject-control.md).

 O <xref:Microsoft.Office.Tools.Excel.NamedRange> controle pode ser associado a uma fonte de dados usando o <xref:System.Windows.Forms.Control.DataBindings%2A> propriedades. A propriedade de associação de dados padrão do <xref:Microsoft.Office.Tools.Excel.NamedRange> controle é <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A>.

 Se os dados no conjunto de dados associado são atualizados por meio de qualquer mecanismo, o <xref:Microsoft.Office.Tools.Excel.NamedRange> controle reflete as alterações.

## <a name="formatting"></a>Formatação
 Formatação que pode ser aplicado a um <xref:Microsoft.Office.Interop.Excel.Range> pode ser aplicado a um <xref:Microsoft.Office.Tools.Excel.NamedRange> controle. Isso inclui as bordas, fontes, formatos de número e estilos.

## <a name="rename-the-control"></a>Renomeie o controle
 Quando você adiciona uma <xref:Microsoft.Office.Tools.Excel.NamedRange> controle à sua planilha do **caixa de ferramentas**, Visual Studio gera automaticamente um nome para o controle. Você pode alterar o nome na **propriedades** janela.

## <a name="events"></a>Eventos
 Os eventos a seguir estão disponíveis para o <xref:Microsoft.Office.Tools.Excel.NamedRange> controle:

- <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeRightClick>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.BindingContextChanged>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.Change>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.Deselected>

- <xref:System.ComponentModel.Component.Disposed>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.Selected>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange>

## <a name="see-also"></a>Consulte também
- [Automatizar o Excel usando objetos estendidos](../vsto/automating-excel-by-using-extended-objects.md)
- [Instruções passo a passo e exemplos de desenvolvimento do office](../vsto/office-development-samples-and-walkthroughs.md)
- [Associar dados a controles em soluções do Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Estender documentos do Word e pastas de trabalho do Excel em suplementos do VSTO em tempo de execução](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Controles em documentos do Office](../vsto/controls-on-office-documents.md)
- [Adicionar controles a documentos do Office em tempo de execução](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Como: Adicionar controles NamedRange a planilhas](../vsto/how-to-add-namedrange-controls-to-worksheets.md)
- [Como: Redimensionar controles NamedRange](../vsto/how-to-resize-namedrange-controls.md)
- [Associar dados a controles em soluções do Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Passo a passo: Programe em eventos de um controle NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)
- [Limitações programáticas de itens de host e controles de host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
