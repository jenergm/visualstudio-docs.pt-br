---
title: 'Como: Introdução à personalização da faixa de opções'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, adding Ribbon to project
- Ribbon [Office development in Visual Studio], adding
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, adding Ribbon to project
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f164a8f1d1c84725530e7a3afab5e63472ae257e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60081561"
---
# <a name="how-to-get-started-customizing-the-ribbon"></a>Como: Introdução à personalização da faixa de opções
  Para personalizar a faixa de opções de um aplicativo do Microsoft Office, adicione uma **faixa de opções (Visual Designer)** ou **da faixa de opções (XML)** item a um projeto do Office.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-add-a-ribbon-to-a-project"></a>Para adicionar uma faixa de opções para um projeto

1. Sobre o **Project** Menu, clique em **Adicionar Novo Item**.

2. No **Adicionar Novo Item** caixa de diálogo, selecione **faixa de opções (Visual Designer)** ou **da faixa de opções (XML)**. Para obter mais informações sobre esses modelos, consulte [visão geral da faixa de opções](../vsto/ribbon-overview.md).

3. No **nome** , digite um nome para o item da faixa de opções.

    Nomes não podem conter os seguintes caracteres:

   - Libra (#)

   - Porcentagem (%))

   - E comercial (&)

   - Asterisco (*)

   - Barra vertical (|)

   - Barra invertida (\\)

   - Dois-pontos (:)

   - Aspas duplas (")

   - Menor que (\<)

   - Maior que (>)

   - Ponto de interrogação (?)

   - Uma barra (/)

   - Espaços iniciais ou finais (' ')

   - Nomes reservados do Windows ou DOS como ("nul", "aux", "con", "com1", "lpt1" e assim por diante)

4. Clique em **OK**.

   O item da faixa de opções aparece na **Gerenciador de soluções**. Para obter informações sobre as próximas etapas, consulte [visão geral da faixa de opções](../vsto/ribbon-overview.md).

## <a name="see-also"></a>Consulte também
- [Acesso a faixa de opções em tempo de execução](../vsto/accessing-the-ribbon-at-run-time.md)
- [Designer da faixa de opções](../vsto/ribbon-designer.md)
- [XML da faixa de opções](../vsto/ribbon-xml.md)
- [Passo a passo: Criar uma guia personalizada usando o Designer de faixa de opções](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [Passo a passo: Criar uma guia personalizada usando o XML da faixa de opções](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)
