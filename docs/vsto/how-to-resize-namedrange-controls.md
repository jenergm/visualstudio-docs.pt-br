---
title: 'Como: Redimensionar controles NamedRange'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- NamedRange control, resizing
- ranges, resizing in Excel
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ba5603fe759f55a85425bc61da0a470aa38d636c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60099588"
---
# <a name="how-to-resize-namedrange-controls"></a>Como: Redimensionar controles NamedRange
  Você pode definir o tamanho de um <xref:Microsoft.Office.Tools.Excel.NamedRange> controle quando você adiciona a um documento do Microsoft Office Excel; no entanto, você talvez queira para redimensioná-la em um momento posterior.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 Você pode redimensionar um intervalo nomeado em tempo de design ou em tempo de execução em projetos de nível de documento. Você também pode redimensionar os intervalos nomeados em tempo de execução no nível de aplicativo VSTO Add-ins.

 Este tópico descreve as seguintes tarefas:

- [Redimensionar controles NamedRange em tempo de design](#designtime)

- [Redimensionar controles NamedRange em tempo de execução em um projeto de nível de documento](#runtimedoclevel)

- [Redimensionar controles NamedRange em tempo de execução em um projeto de suplemento do VSTO](#runtimeaddin)

## <a name="designtime"></a> Redimensionar controles NamedRange em tempo de design
 Você pode redimensionar um intervalo nomeado, redefinindo seu tamanho na **definir nome** caixa de diálogo.

### <a name="to-resize-a-named-range-by-using-the-define-name-dialog-box"></a>Para redimensionar um intervalo nomeado usando a caixa de diálogo Definir nome

1. Clique com botão direito um <xref:Microsoft.Office.Tools.Excel.NamedRange> controle.

2. Clique em **intervalos nomeados de gerenciar** no menu de atalho.

     O **definir nome** caixa de diálogo é exibida.

3. Selecione o intervalo nomeado que você deseja redimensionar.

4. Desmarque a **refere-se ao** caixa.

5. Selecione as células que você deseja usar para definir o tamanho do intervalo nomeado.

6. Clique em **OK**.

## <a name="runtimedoclevel"></a> Redimensionar controles NamedRange em tempo de execução em um projeto de nível de documento
 Você pode redimensionar um intervalo nomeado programaticamente usando o <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> propriedade.

> [!NOTE]
>  No **propriedades** janela, o <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> propriedade é marcada como somente leitura.

### <a name="to-resize-a-named-range-programmatically"></a>Para redimensionar um intervalo nomeado de forma programática

1. Criar uma <xref:Microsoft.Office.Tools.Excel.NamedRange> controle na célula **A1** de `Sheet1`.

     [!code-csharp[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#4)]

2. Redimensionar o intervalo nomeado para incluir a célula **B1**.

     [!code-csharp[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#5)]

## <a name="runtimeaddin"></a> Redimensionar controles NamedRange em tempo de execução em um projeto de suplemento do VSTO
 Você pode redimensionar um <xref:Microsoft.Office.Tools.Excel.NamedRange> controle em qualquer planilha aberta em tempo de execução. Para obter mais informações sobre como adicionar um <xref:Microsoft.Office.Tools.Excel.NamedRange> de controle para uma planilha usando um suplemento do VSTO, consulte [como: Adicionar controles NamedRange a planilhas](../vsto/how-to-add-namedrange-controls-to-worksheets.md).

### <a name="to-resize-a-named-range-programmatically"></a>Para redimensionar um intervalo nomeado de forma programática

1. Criar uma <xref:Microsoft.Office.Tools.Excel.NamedRange> controle na célula **A1** de `Sheet1`.

     [!code-csharp[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#10)]
     [!code-vb[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#10)]

2. Redimensionar o intervalo nomeado para incluir a célula **B1**.

     [!code-csharp[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#11)]
     [!code-vb[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#11)]

## <a name="see-also"></a>Consulte também
- [Estender documentos do Word e pastas de trabalho do Excel em suplementos do VSTO em tempo de execução](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Adicionar controles a documentos do Office em tempo de execução](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Controles em documentos do Office](../vsto/controls-on-office-documents.md)
- [Visão geral dos controles de host e de itens de host](../vsto/host-items-and-host-controls-overview.md)
- [Automatizar o Excel usando objetos estendidos](../vsto/automating-excel-by-using-extended-objects.md)
- [Controle NamedRange](../vsto/namedrange-control.md)
- [Como: Adicionar controles NamedRange a planilhas](../vsto/how-to-add-namedrange-controls-to-worksheets.md)
- [Como: Redimensionar controles de indicador](../vsto/how-to-resize-bookmark-controls.md)
- [Como: Redimensionar controles ListObject](../vsto/how-to-resize-listobject-controls.md)
