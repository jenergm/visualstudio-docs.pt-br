---
title: Guia classe, caixa de diálogo de propriedades de janela | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Window Properties dialog box, Class Tab
ms.assetid: eaec9f07-d580-436d-934d-76c4e59439aa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0917c9a038b42e6302ec1f1782f095ca397a92ef
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56628345"
---
# <a name="class-tab-window-properties-dialog-box"></a>Guia Classe, Caixa de diálogo Propriedades da Janela
Use o **classe** guia para exibir informações sobre a classe da janela selecionada. Para exibir o [janela caixa de diálogo de propriedades](../debugger/window-properties-dialog-box.md), mova o foco para o [modo de exibição do Windows](../debugger/windows-view.md) janela. Selecione qualquer nó de janela na árvore e escolha **propriedades** da **exibição** menu.

 As seguintes configurações estão disponíveis sobre o **classe** guia:

|Entrada|Descrição|
|-----------|-----------------|
|**Nome de Classe**|O nome (ou um número ordinal) dessa classe de janela.|
|**Estilos de Classe**|Uma combinação de códigos de estilo de classe.|
|**Bytes da Classe**|Dados de específicos do aplicativo associados a essa classe de janela.|
|**Átomo da Classe**|O atom para a classe retornada pela **RegisterClass** chamar.|
|**Identificador de Instância**|O identificador da instância do módulo que registrou a classe. Identificadores de instância não são exclusivos.|
|**Bytes da Janela**|O número de bytes adicionais associados a cada janela dessa classe. O significado desses bytes é determinado pelo aplicativo. Expanda a caixa de lista para ver os valores de byte em formato DWORD.|
|**Procedimento de Janela**|O endereço atual do **WndProc** função para o windows dessa classe. Isso difere da **procedimento de janela** sobre o **geral** guia se a janela é uma subclasse.|
|**Nome do Menu**|O nome do menu principal que está associado com o windows dessa classe ("none" se não houver nenhum menu).|
|**Identificador de Ícone**|O identificador para o ícone que está associado com o windows dessa classe ("none" se não houver nenhum ícone).|
|**Identificador de Cursor**|O identificador para o cursor que está associado com o windows dessa classe ("none" se não houver nenhum cursor).|
|**Pincel da Tela de Fundo**|O identificador para o pincel de plano de fundo que está associado com o windows dessa classe ou uma das COLOR_ * cores predefinidas para pintar a tela de fundo de janela ("none" se não houver nenhum pincel).|