---
title: 'Como: Copiar planilhas programaticamente'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, copying
- Excel [Office development in Visual Studio], copying worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 305f24204c1be7186b2d2d49fa61a0c32c52c8cb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60104389"
---
# <a name="how-to-programmatically-copy-worksheets"></a>Como: Copiar planilhas programaticamente
  Você pode criar uma cópia de uma planilha e inserir essa planilha antes ou depois de uma planilha existente na pasta de trabalho. Se você não especificar onde inserir a planilha, o Excel cria uma nova pasta de trabalho para conter a nova planilha.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

> [!NOTE]
>  Se você copiar a planilha programaticamente, ou o usuário final copia a planilha manualmente, não há nenhum code-behind a nova planilha e controles na nova planilha não funcionam. Isso ocorre porque a planilha copiada recentemente é um <xref:Microsoft.Office.Interop.Excel.Worksheet> objeto e não um <xref:Microsoft.Office.Tools.Excel.Worksheet> item de host. Controles dos Windows Forms e controles de host só podem ser adicionados aos itens de host. Para obter mais informações, consulte [limitações programáticas de itens de host e controles de host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).

## <a name="to-add-a-copied-worksheet-to-a-workbook-in-a-document-level-customization"></a>Para adicionar uma planilha copiada para uma pasta de trabalho em uma personalização no nível de documento

1. Use o <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> método para copiar a primeira planilha na pasta de trabalho atual e coloque a cópia após a terceira planilha.

     [!code-csharp[Trin_VstcoreExcelAutomation#16](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomation#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#16)]

## <a name="to-add-a-copied-worksheet-to-a-workbook-in-a-vsto-add-in"></a>Para adicionar uma planilha copiada para uma pasta de trabalho em um suplemento do VSTO

1. Use o <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> método para copiar a primeira planilha na pasta de trabalho atual e coloque a cópia após a terceira planilha.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#12](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#12)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#12](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#12)]

## <a name="see-also"></a>Consulte também
- [Trabalhar com planilhas](../vsto/working-with-worksheets.md)
- [Visão geral dos controles de host e de itens de host](../vsto/host-items-and-host-controls-overview.md)
- [Como: Adicionar novas planilhas a pastas de trabalho programaticamente](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)
- [Como: Excluir planilhas de pastas de trabalho de forma programática](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)
- [Como: Selecionar planilhas programaticamente](../vsto/how-to-programmatically-select-worksheets.md)
- [Automatizar o Excel usando objetos estendidos](../vsto/automating-excel-by-using-extended-objects.md)
- [Acesso global a objetos em projetos do Office](../vsto/global-access-to-objects-in-office-projects.md)
- [Limitações programáticas de itens de host e controles de host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Parâmetros opcionais em soluções do Office](../vsto/optional-parameters-in-office-solutions.md)
