---
title: 'Como: Exportar uma faixa de opções do Designer da faixa de opções para o XML da faixa de opções'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, XML
- customizing the Ribbon, XML
- Ribbon [Office development in Visual Studio], XML
- Ribbon [Office development in Visual Studio], exporting
- XML [Office development in Visual Studio], Ribbon
- Ribbon Designer [Office development in Visual Studio]
- exporting Ribbon
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b36c149022849dd6a788bcb5ee8f58cc12ae4417
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60110993"
---
# <a name="how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Como: Exportar uma faixa de opções do Designer da faixa de opções para o XML da faixa de opções
  O **faixa de opções (Visual Designer)** item não oferece suporte a todos os tipos possíveis de personalização da faixa de opções. Para personalizar a faixa de opções de maneiras avançadas, você pode exportar a faixa de opções do designer para o XML da faixa de opções e editar o XML diretamente.

> [!NOTE]
>  Nem todos os valores de propriedade aparecem no arquivo XML de faixa de opções. Para obter mais informações, consulte [visão geral da faixa de opções](../vsto/ribbon-overview.md).

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Para exportar uma faixa de opções do Designer da faixa de opções para XML da faixa de opções

1. O arquivo de código da faixa de opções no botão direito do mouse **Gerenciador de soluções**e, em seguida, clique em **View Designer**.

2. O Designer de faixa de opções com o botão direito e, em seguida, clique em **faixa de opções de exportação para XML**.

     Visual Studio adiciona um arquivo XML de faixa de opções e um arquivo de código XML da faixa de opções ao seu projeto.

3. Na classe de código da faixa de opções, localize os comentários que começam com `TODO:`.

4. Copie o bloco de código nesses comentários para o **ThisAddin**, **ThisWorkbook**, ou **ThisDocument** classe, dependendo de qual tipo de solução que você está desenvolvendo.

     Esse código permite que o aplicativo do Microsoft Office descobrir e carregar sua faixa de opções personalizada. Para obter mais informações, consulte [XML da faixa de opções](../vsto/ribbon-xml.md).

5. No **ThisAddin**, **ThisWorkbook**, ou **ThisDocument** de classe, remova o bloco de código.

     Depois que você remova os comentários de código, ele deve se parecer com o exemplo a seguir. Neste exemplo, a classe de faixa de opções é chamada `MyRibbon`.

     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]

6. Alterne para o arquivo de código XML da faixa de opções e encontre o `Ribbon Callbacks` região.

     Isso é onde você pode escrever métodos de retorno de chamada para manipular ações do usuário, como clicar em um botão.

7. Crie um método de retorno de chamada para cada manipulador de eventos que você escreveu o código do Designer de faixa de opções.

8. Mover todo o código de manipulador de eventos de manipuladores de eventos para os métodos de retorno de chamada e modifique o código para trabalhar com a extensibilidade da faixa de opções (RibbonX) modelo de programação.

     Para obter informações sobre como escrever métodos de retorno de chamada e usar o modelo de programação do RibbonX, consulte [XML da faixa de opções](../vsto/ribbon-xml.md).

## <a name="see-also"></a>Consulte também
- [Visão geral da faixa de opções](../vsto/ribbon-overview.md)
- [Designer da faixa de opções](../vsto/ribbon-designer.md)
- [XML da faixa de opções](../vsto/ribbon-xml.md)
- [Passo a passo: Criar uma guia personalizada usando o Designer de faixa de opções](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [Passo a passo: Criar uma guia personalizada usando o XML da faixa de opções](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)
