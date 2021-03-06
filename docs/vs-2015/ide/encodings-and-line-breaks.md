---
title: Codificações e quebras de linha | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.Encoding
helpviewer_keywords:
- line breaks
- encoding
- Visual Studio, encoding
- editors, line breaks
- line break characters
- Visual Studio, line break characters
ms.assetid: 8f9b3ffc-7b8d-44f4-87cb-dc29105be12d
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 88f04720610bad5064f7f9d7a43beef2410b045f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54787460"
---
# <a name="encodings-and-line-breaks"></a>Codificações e quebras de linha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

No Visual Studio, é possível usar os configurações **Arquivo/Opções avançadas de salvamento** configurações para determinar o tipo de quebra de linha caracteres que você deseja. Também é possível alterar a codificação de um arquivo com as mesmas configurações.  
  
> [!NOTE]
>  Se você tiver determinados tipos de configurações de desenvolvimento (Visual Basic, F#, Desenvolvimento para a Web), talvez você não veja **Opções avançadas de salvamento** no menu. Para alterar suas configurações (por exemplo para Geral), abra **Ferramentas/Importar e Exportar Configurações**. Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 No Visual Studio, os seguintes caracteres são interpretados como quebras de linha:  
  
- CRLF: retorno de carro + alimentação de linha, caracteres Unicode 000D + 000A  
  
- LF: alimentação de linha, caractere Unicode 000A  
  
- NEL: próxima linha, caractere Unicode 0085  
  
- LS: separador de linha, caractere Unicode 2028  
  
- PS: separador de parágrafo, caractere Unicode 2029  
  
  O texto copiado de outros aplicativos mantém a codificação original e os caracteres de quebra de linha. Por exemplo, quando você copia texto do Bloco de notas e o cola em um arquivo de texto no Visual Studio, o texto tem as mesmas configurações que ele tinha no Bloco de notas.  
  
  Quando você abre um arquivo que caracteres com uma quebra de linha diferente, talvez você veja uma caixa de diálogo que pergunta se os caracteres de quebra de linha inconsistentes devem ser normalizados e quais os tipo de quebras de linha você deseja escolher.
