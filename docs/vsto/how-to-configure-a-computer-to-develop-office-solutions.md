---
title: 'Como: Configurar um computador para desenvolver soluções do Office'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- prerequisites [Office development in Visual Studio]
- Office development in Visual Studio, installing tools
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b1f87b9548aceab58e1a8e1c6178a1dca759c312
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60052839"
---
# <a name="how-to-configure-a-computer-to-develop-office-solutions"></a>Como: Configurar um computador para desenvolver soluções do Office
  Para configurar um computador de desenvolvimento para que você pode usar o Microsoft Office developer tools no Visual Studio, siga as instruções neste tópico. Você deve ter privilégios administrativos no computador de desenvolvimento para executar essas etapas.

### <a name="to-configure-the-development-computer"></a>Para configurar o computador de desenvolvimento

1. Instale uma versão do Visual Studio que inclui o Office developer tools. As ferramentas de desenvolvedor do Office são instaladas por padrão. Se você personalizar a instalação do Visual Studio, selecionando quais recursos serão instalados, verifique se **Microsoft Office Developer Tools** é selecionada durante a instalação. Para obter mais informações sobre as versões do Visual Studio que incluem o Office developer tools, consulte [configurar um computador para desenvolver soluções do Office](../vsto/configuring-a-computer-to-develop-office-solutions.md).

2. Instale uma versão do Office que é compatível com o Office developer tools no Visual Studio. Para obter mais informações, consulte [configurar um computador para desenvolver soluções do Office](../vsto/configuring-a-computer-to-develop-office-solutions.md).

     Certifique-se de que você também pode instalar os PIAs para a versão do Office que você instalar. Por padrão, os PIAs são instalados com o Office. Se você modificar a instalação do Office, verifique se o **suporte à programação do .NET** está selecionado para os aplicativos de destino.

3. Se você tiver uma versão em inglês do Visual Studio, mas usa configurações diferentes do inglês para Windows, você pode instalar o [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] pacote de idiomas para ver [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] mensagens no mesmo idioma do Windows. Essas versões do Visual Studio instalam automaticamente o pacote de idiomas. O pacote de idiomas está disponível na [Centro de download da Microsoft](http://go.microsoft.com/fwlink/?LinkId=140386).

## <a name="see-also"></a>Consulte também

- [Introdução ao &#40;desenvolvimento do Office no Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Como: Instalar o Visual Studio Tools for Office runtime redistribuível](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)
- [Como: Instalar assemblies de interoperabilidade primários do Office](../vsto/how-to-install-office-primary-interop-assemblies.md)
