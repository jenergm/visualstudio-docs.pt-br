---
title: Elemento WizardData (modelos do Visual Studio) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#WizardData
helpviewer_keywords:
- WizardData element [Visual Studio Templates]
- <WizardData> element [Visual Studio Templates]
ms.assetid: d0403a16-5d07-4fe5-b474-19ae3d9fd3ab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c6b61c62e8a3b69963bd56129fd3e7168271fc07
ms.sourcegitcommit: a916ce1eec19d49f060146f7dd5b65f3925158dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55231575"
---
# <a name="wizarddata-element-visual-studio-templates"></a>Elemento WizardData (modelos do Visual Studio)

Especifica o XML personalizado

```xml
\<VSTemplate>
\<WizardData>
```

## <a name="syntax"></a>Sintaxe

```xml
<WizardData>
    <!-- XML to pass to the custom wizard extension -->
    ...
</WizardData>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elementos pai.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|Elemento obrigatório.<br /><br /> Contém todos os metadados para o modelo de projeto, o modelo de item ou o starter kit para.|

## <a name="text-value"></a>Valor de texto

Um valor de texto é opcional.

Esse texto Especifica o XML personalizado para passar para a extensão de assistente personalizada especificada na [WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md) elemento.

## <a name="remarks"></a>Comentários

Qualquer XML pode ser especificado nesse elemento. O XML será ser passado como um parâmetro para a extensão de assistente personalizada, permitindo que a extensão usar o conteúdo desse elemento. Nenhuma validação é feita nesses dados.

O conteúdo a **WizardData** elemento for passado, sem alterações, como um parâmetro de dicionário de parâmetros na cadeia de caracteres a `IWizard.RunStarted` método. A chave de dicionário é nomeada `$wizarddata$`.

## <a name="example"></a>Exemplo

O exemplo a seguir ilustra os metadados para o modelo de projeto padrão para um C# aplicativo do Windows.

```xml
<VSTemplate Version="3.0.0" Type="Item"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyTemplate</Name>
        <Description>Template using IWizard extension</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
    </TemplateData>
    <TemplateContent>
        <Project File="MyTemplate.csproj">
            <ProjectItem>Form1.cs<ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
    <WizardExtension>
        <Assembly>MyWizard, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom=null</Assembly>
        <FullClassName>MyWizard.CustomWizard</FullClassName>
    </WizardExtension>
    <WizardData>
        <!-- XML to pass to the custom wizard extension -->
    </WizardData>
</VSTemplate>
```

## <a name="see-also"></a>Consulte também

- [Referência de esquema do modelo do Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Criando modelos de projeto e de item](../ide/creating-project-and-item-templates.md)
- [Elemento WizardExtension (Modelos do Visual Studio)](../extensibility/wizardextension-element-visual-studio-templates.md)
- [Como: Usar assistentes com modelos de projeto](../extensibility/how-to-use-wizards-with-project-templates.md)