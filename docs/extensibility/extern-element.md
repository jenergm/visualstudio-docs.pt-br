---
title: Elemento extern | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Extern
helpviewer_keywords:
- VSCT XML schema elements, Extern
- Extern element (VSCT XML schema)
ms.assetid: db6c3ddd-a1ba-450a-897a-bb568a5377fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1d62d52d490994889f7e9186fb74ea148cb52a06
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56690533"
---
# <a name="extern-element"></a>Elemento extern
O elemento Extern faz referência a qualquer cabeçalho externo (*. h*) arquivos para mesclar com o *VSCT* arquivo em tempo de compilação. Os arquivos a serem mescladas devem estar no caminho de inclusão fornecido ao compilador VSCT ou referenciado por um [elemento Include](../extensibility/include-element.md). Os arquivos podem ser outros *VSCT* arquivos ou arquivos de cabeçalho C++.

 As definições em arquivos de cabeçalho devem estar no formato "#define [Symbol] [valor]" o valor pode ser outro símbolo, caso ele seja definido anteriormente. Definições podem ser usadas em instruções condicionais de itens de comando. Qualquer símbolo, na verdade não usado será descartado.

 Elemento do elemento CommandTable Extern

## <a name="syntax"></a>Sintaxe

```xml
<Extern href="stdidcmd.h" />
```

## <a name="attributes-and-elements"></a>Atributos e elementos
 As seções a seguir descrevem atributos, elementos filho e elementos pai.

### <a name="attributes"></a>Atributos

|Atributo|Descrição|
|---------------|-----------------|
|{1&gt;href&lt;1}|Necessário. O caminho para o arquivo de cabeçalho:<br /><br /> href="stdidcmd.h"|
|Condição|Opcional. Ver [atributos condicionais](../extensibility/vsct-xml-schema-conditional-attributes.md).|
|linguagem|Opcional. O idioma padrão de todos os [ \<cadeias de caracteres >](../extensibility/strings-element.md) elementos na tabela de comandos:<br /><br /> language="en-us"|

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|nenhuma.|nenhuma.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CommandTable](../extensibility/commandtable-element.md)|Define todos os elementos que representam comandos — ou seja, itens de menu, menus, barras de ferramentas e caixas de combinação — que um VSPackage fornece ao IDE.|

## <a name="example"></a>Exemplo

```xml
<?xml version="1.0" encoding="utf-8"?>
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-
  18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <Extern href="C:\VSCore\vscommon\inc\vsshlids.h"/>
    ...
  <Commands package="guidMyPackage">
</CommandTable>
```

## <a name="see-also"></a>Consulte também
- [Arquivos de tabela (. VSCT) de comando do Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [Como os VSPackages adicionam elementos da interface do usuário](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Comandos, menus e barras de ferramentas](../extensibility/internals/commands-menus-and-toolbars.md)