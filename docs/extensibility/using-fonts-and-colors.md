---
title: Usando fontes e cores | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- fonts, controlling in IDE
- IDE, controlling text color and fonts
- Fonts and Colors property page
- font and color control [Visual Studio SDK]
- text, IDE
ms.assetid: d1a9b99f-fbdc-45ed-920a-e08c3d931ac9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 96abe68838d028c5de9d6d9418e94ba5b46c0f76
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56693406"
---
# <a name="using-fonts-and-colors"></a>Usando fontes e cores
O [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] fornece suporte ao uso de fontes e cores para exibir o texto.

## <a name="in-this-section"></a>Nesta seção
- [Visão geral de cor e de fonte](../extensibility/font-and-color-overview.md) discute as configurações de fonte e cor do texto no [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] o ambiente de desenvolvimento integrado (IDE). Também apresenta os conceitos de categorias e itens de exibição e descreve como os VSPackages e o editor principal usam atributos de texto.

- [Obtendo informações de cores e fontes para texto colorização](../extensibility/getting-font-and-color-information-for-text-colorization.md) fornece diretrizes para implementar a colorização do texto em VSPackages que gerenciam **categorias** diferente de **Editor de texto**.

- [Acessando configurações de cor e a fonte armazenado](../extensibility/accessing-stored-font-and-color-settings.md) Explains como configurações de fonte e cor atuais podem ser armazenadas, recuperadas e aplicadas.

- [Implementação de categorias personalizadas e exibir itens](../extensibility/implementing-custom-categories-and-display-items.md) descreve as etapas básicas pelas quais uma janela pode criar e usar seu próprio de **exibir itens** e **categorias** para dar suporte à exibição de texto.

 Essa abordagem exige um VSPackage implementar o <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> interface e interfaces relacionadas.

- [Como: Acessar o esquema de cores e fontes internas](../extensibility/how-to-access-the-built-in-fonts-and-color-scheme.md) aborda como definir e registrar uma categoria, usando cores e fontes internas e iniciar o uso de cores e fontes fornecidas pelo sistema.

## <a name="reference"></a>Referência
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> Fornece uma instância do `IVsFontAndColorDefaults` ou o <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> que corresponde a um item específico listado na interface a **Mostrar configurações para** listar no **fontes e cores** página do **Opções de** caixa de diálogo.

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> Permite que um VSPackage dar suporte ao IDE **fontes e cores** página definindo fontes padrão e cores para uma janela ou um componente de interface do usuário.

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> Fornece um mecanismo pelo qual um VSPackage que fornece suporte de fonte e cor pode especificar um grupo de Item de exibição - uma categoria de superusuários que representa a união de duas ou mais categorias.

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> Permite que um VSPackage recuperar dados de fontes e cores, ou salvá-lo no registro.

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> Notifica os VSPackages que estão usando fontes e cores informações sobre as alterações nas configurações de fonte e cor.

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorUtilities> Fornece ferramentas para trabalhar com os dados de entrada e saídos que são usados pelos métodos das [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **fontes e cores** mecanismo.

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> Controla o cache das configurações de fonte e cor.

## <a name="related-sections"></a>Seções relacionadas
- [Desenvolver um serviço de linguagem herdado](../extensibility/internals/developing-a-legacy-language-service.md) discute como os VSPackages pode usar os serviços de linguagem para personalizar o [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] editor.

- [Coloração de sintaxe em editores personalizados](../extensibility/syntax-coloring-in-custom-editors.md) Descries como o [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] editor usa serviços de linguagem para implementar a coloração de sintaxe.

- [Estender outras partes do Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md) explica como usar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] services para criar elementos de interface do usuário que correspondem ao restante do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].