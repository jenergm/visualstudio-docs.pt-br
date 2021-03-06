---
title: Estendendo um serviço de linguagem para dar suporte ao EditorConfig no Visual Studio | Microsoft Docs
ms.date: 11/22/2017
ms.topic: conceptual
helpviewer_keywords:
- editorconfig [extensibility]
- editorconfig, supporting in a language service
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3c29c22ae4539d874ffc08c9ce5adf94ab33d404
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56696968"
---
# <a name="supporting-editorconfig-for-your-language-service"></a>Dando suporte ao EditorConfig para o seu serviço de linguagem

[EditorConfig](http://editorconfig.org/) arquivos permitem que você descrevem opções de editor de texto comuns, como o tamanho do recuo, em uma base por projeto. Para saber mais sobre o suporte do Visual Studio para arquivos EditorConfig, consulte [criar configurações do editor portátil usando EditorConfig](../ide/create-portable-custom-editor-options.md).

Na maioria dos casos, ao implementar um serviço de linguagem do Visual Studio, nenhum trabalho adicional é necessário para dar suporte às propriedades universais do EditorConfig. O editor básico detecta automaticamente e lê o arquivo .editorconfig quando os usuários abrem arquivos e define as opções de buffer e exibição de texto apropriadas. No entanto, para as edições, como tabulações e espaços, alguns serviços de linguagem optar por usar uma opção de exibição de texto contextual apropriada em vez de usar configurações globais. Nesses casos, o serviço de linguagem deve ser atualizado para dar suporte aos arquivos do EditorConfig.

A seguir estão as alterações que são necessárias para atualizar um serviço de linguagem para dar suporte a arquivos de EditorConfig, substituindo um global _específico do idioma_ a opção com um _contextual_ opção:

## <a name="indent-style"></a>Estilo de recuo

Opções específicas de idioma | Opções contextuais
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs|!textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)<br/>!textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)

## <a name="indent-size"></a>Tamanho do recuo

Opções específicas de idioma | Opções contextuais
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize|textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)

## <a name="tab-size"></a>A guia tamanho

Opções específicas de idioma | Opções contextuais
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize|textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)

## <a name="see-also"></a>Consulte também

- [Criar configurações do editor portátil usando EditorConfig](../ide/create-portable-custom-editor-options.md)
- [Estendendo os serviços do editor e linguagem](../extensibility/extending-the-editor-and-language-services.md)