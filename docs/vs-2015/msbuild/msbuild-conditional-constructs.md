---
title: Constructos condicionais do MSBuild | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Choose> Element [MSBuild]
- Choose Element [MSBuild]
- conditional constructs [MSBuild]
- MSBuild, conditional constructs
- <When> Element [MSBuild]
- <Otherwise> Element [MSBuild]
- Otherwise Element [MSBuild]
- When Element [MSBuild]
ms.assetid: dd54258e-f4fb-448f-9da4-d1817e0cbaf2
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b7b22f63d5d3d6e0b1f7789561029bbfbfb4cdf4
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59667502"
---
# <a name="msbuild-conditional-constructs"></a>Constructos condicionais do MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] fornece um mecanismo para processamento de um/ou outro com os elementos [Choose](../msbuild/choose-element-msbuild.md), [When](../msbuild/when-element-msbuild.md) e [Otherwise](../msbuild/otherwise-element-msbuild.md).  
  
## <a name="using-the-choose-element"></a>Usando o elemento Choose  
 O elemento `Choose` contém uma série de elementos de `When` com atributos `Condition` que são testados na ordem de cima para baixo até que um seja avaliado como `true`. Se mais de um elemento `When` for avaliado como `true`, somente o primeiro será usado. Um elemento `Otherwise`, se presente, será avaliado se nenhuma condição em um elemento `When` for avaliada como `true`.  
  
 Os elementos `Choose` podem ser usados como elementos filhos dos elementos `Project`, `When` e `Otherwise`. Os elementos `When` e `Otherwise` podem ter elementos filho `ItemGroup`, `PropertyGroup` ou `Choose`.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa os elementos `Choose` e `When` para processamento de um/ou outro. As propriedades e os itens do projeto são definidos dependendo do valor da propriedade `Configuration`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>ConsoleApplication1</RootNamespace>  
        <AssemblyName>ConsoleApplication1</AssemblyName>  
        <WarningLevel>4</WarningLevel>  
    </PropertyGroup>  
    <Choose>  
        <When Condition=" '$(Configuration)'=='Debug' ">  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <DebugType>full</DebugType>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\Debug\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
            <ItemGroup>  
                <Compile Include="UnitTesting\*.cs" />  
                <Reference Include="NUnit.dll" />  
            </ItemGroup>  
        </When>  
        <When Condition=" '$(Configuration)'=='retail' ">  
            <PropertyGroup>  
                <DebugSymbols>false</DebugSymbols>  
                <Optimize>true</Optimize>  
                <OutputPath>.\bin\Release\</OutputPath>  
                <DefineConstants>TRACE</DefineConstants>  
            </PropertyGroup>  
        </When>  
    </Choose>  
    <!-- Rest of Project -->  
</Project>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Elemento Choose (MSBuild)](../msbuild/choose-element-msbuild.md)   
 [Elemento When (MSBuild)](../msbuild/when-element-msbuild.md)   
 [Elemento Otherwise (MSBuild)](../msbuild/otherwise-element-msbuild.md)   
 [Referência do MSBuild](../msbuild/msbuild-reference.md)
