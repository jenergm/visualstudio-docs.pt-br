---
title: 'Como: Fechar documentos do Visio programaticamente'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], closing Visio documents
- Visio [Office development in Visual Studio], closing Visio documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 474efcb62cf7cadd9de82e41ff2ad36cebc046cb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60067649"
---
# <a name="how-to-programmatically-close-visio-documents"></a>Como: Fechar documentos do Visio programaticamente
  Você pode fechar o documento ativo do Microsoft Office Visio usando a `Microsoft.Office.Interop.Visio.Document.Close` método.

 Para obter detalhes sobre esse método, consulte a documentação de referência do VBA para o [Microsoft.Office.Interop.Visio.Document.Close](/office/vba/api/Visio.Document.Close) método.

## <a name="close-the-active-document"></a>Fechar o documento ativo

### <a name="to-close-the-active-document"></a>Para fechar o documento ativo

- Chamar o `Microsoft.Office.Interop.Visio.Document.Close` método para fechar o documento ativo.

     Para usar o exemplo de código a seguir, execute-o `ThisAddIn` classe em um projeto de suplemento do VSTO para Visio.

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#7)]

## <a name="see-also"></a>Consulte também
- [Soluções do Visio](../vsto/visio-solutions.md)
- [Visão geral do modelo de objeto do Visio](../vsto/visio-object-model-overview.md)
- [Como: Criar novos documentos do Visio programaticamente](../vsto/how-to-programmatically-create-new-visio-documents.md)
- [Como: Abrir documentos do Visio de forma programática](../vsto/how-to-programmatically-open-visio-documents.md)
- [Como: Salvar documentos do Visio programaticamente](../vsto/how-to-programmatically-save-visio-documents.md)
- [Como: Imprimir documentos do Visio de forma programática](../vsto/how-to-programmatically-print-visio-documents.md)
