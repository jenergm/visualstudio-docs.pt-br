---
title: Referencia o elemento (modelos do Visual Studio) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#References
helpviewer_keywords:
- <References> element [Visual Studio Templates]
- References element [Visual Studio Templates]
ms.assetid: 1969146d-46bf-422d-8d46-0e9493925003
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3ae0ee308af1502a7c07766e790b79e51f692a96
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56691053"
---
# <a name="references-element-visual-studio-templates"></a>Elemento References (modelos do Visual Studio)
Agrupa as referências de assembly que o modelo adiciona aos projetos.

 \<VSTemplate> \<TemplateContent> \<References>

## <a name="syntax"></a>Sintaxe

```xml
<References>
    <Reference>... </Reference>
    <Reference>... </Reference>
    ...
</References>
```

## <a name="attributes-and-elements"></a>Atributos e elementos
 As seções a seguir descrevem atributos, elementos filho e elementos pai.

### <a name="attributes"></a>Atributos
 nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Referência](../extensibility/reference-element-visual-studio-templates.md)|Elemento obrigatório.<br /><br /> Especifica a referência de assembly a ser adicionada quando o item for adicionado a um projeto. Deve haver um ou mais `Reference` elementos em um `References` elemento.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Especifica o conteúdo do modelo.|

## <a name="remarks"></a>Comentários
 O `References` é um elemento filho opcional de `TemplateContent`.

 O `Reference` e `References` elementos só podem ser usados na *. vstemplate* arquivos que têm uma `Type` valor de atributo `Item`.

## <a name="example"></a>Exemplo
 O exemplo a seguir ilustra o `TemplateContent` elemento de um modelo de item. Esse XML adiciona as referências para o *System. dll* e *dll* assemblies.

```xml
<TemplateContent>
    <References>
        <Reference>
            <Assembly>
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089
            </Assembly>
        </Reference>
        <Reference>
            <Assembly>
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089
            </Assembly>
        </Reference>
    </References>
    ...
</TemplateContent>
```

## <a name="see-also"></a>Consulte também
- [Referência de esquema de modelo do Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Criando modelos de projeto e de item](../ide/creating-project-and-item-templates.md)
