---
title: 'Como: Adicionar texto e formatação a células em tabelas do Word programaticamente'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- cells, adding text and formatting
- text [Office development in Visual Studio], adding to Word tables
- formatting [Office development in Visual Studio]
- tables [Office development in Visual Studio], adding text and formatting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a415e55c263534ee4b29e5b45e24ad471d68fe0e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60063862"
---
# <a name="how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables"></a>Como: Adicionar texto e formatação a células em tabelas do Word programaticamente
  Cada tabela consiste em uma coleção de células. Cada indivíduo <xref:Microsoft.Office.Interop.Word.Cell> objeto representa uma célula na tabela. Você pode se referir a cada célula de acordo com seu local na tabela. Este exemplo refere-se para a célula localizada na primeira linha e primeira coluna da tabela; adiciona texto à célula; e se aplica a formatação.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-add-text-and-formatting-to-cells"></a>Para adicionar texto e formatação a células

1. Fazer referência à célula por seu local na tabela, adicionar texto à célula e aplicar a formatação.

     O exemplo de código a seguir pode ser usado em uma personalização no nível de documento. Para usar este exemplo, executá-la na `ThisDocument` classe em seu projeto.

     [!code-vb[Trin_VstcoreWordAutomation#97](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#97)]
     [!code-csharp[Trin_VstcoreWordAutomation#97](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#97)]

     O exemplo de código a seguir pode ser usado em um suplemento do VSTO. Este exemplo usa o documento ativo. Para usar o exemplo, executá-la na `ThisAddIn` classe em seu projeto.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#97](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#97)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#97](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#97)]

## <a name="see-also"></a>Consulte também
- [Como: Criar tabelas do Word de forma programática](../vsto/how-to-programmatically-create-word-tables.md)
- [Como: Adicionar linhas e colunas de forma programática a tabelas do Word](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)
- [Como: Por meio de programação popular tabelas do Word com propriedades do documento](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)
