---
title: 'Como: Especificar o binário para iniciar | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a03bf203e5078bdbdf6327ec7bda186613a25c03
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56622651"
---
# <a name="how-to-specify-the-binary-to-start"></a>Como: Especificar o binário a ser iniciado

Para analisar binários, como DLLs, você deve inserir informações na caixa de diálogo **\<Destino> Páginas de Propriedade**. Essa informação indica onde o projeto DLL pode localizar o aplicativo de chamada.

1. No **Gerenciador de Desempenho**, clique com o botão direito do mouse no binário de destino e, em seguida, clique em **Propriedades**.

2. Na caixa de diálogo **Páginas de Propriedades**, clique nas propriedades de **Inicialização**.

3. Selecione a caixa de seleção **Substituir as propriedades de projeto**.

4. Na caixa de texto **Executável a Ser Iniciado**, especifique o local do arquivo.

5. Na caixa de texto **Argumentos**, especifique os argumentos que são necessários para iniciar o aplicativo.

6. Na caixa de texto **Diretório de Trabalho**, especifique o local do diretório.

7. Clique em **OK**.

## <a name="see-also"></a>Consulte também

[Configurar sessões de desempenho](../profiling/configuring-performance-sessions.md)