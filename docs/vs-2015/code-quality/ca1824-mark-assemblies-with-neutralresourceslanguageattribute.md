---
title: 'CA1824: Marcar assemblies com NeutralResourcesLanguageAttribute | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 795d48b96392057a3f96cf3a67f3c49de8aee9b9
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60052162"
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: Marque assemblies com NeutralResourcesLanguageAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|Categoria|Microsoft.Performance|
|Alteração Significativa|Não são significativas|

## <a name="cause"></a>Causa
 Um assembly contém um **ResX**-com base em recursos, mas não tem o <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> aplicado a ele.

## <a name="rule-description"></a>Descrição da Regra
 O **NeutralResourcesLanguage** atributo informa o **ResourceManager** da linguagem que foi usada para exibir os recursos de cultura neutra para um assembly. Quando ele procura recursos na mesma cultura que o idioma de recursos neutros, o **ResourceManager** usa automaticamente os recursos que estão localizados no assembly principal. Ele faz isso em vez de procurar por um assembly satélite que tem a cultura de interface do usuário atual do thread atual. Isso melhora o desempenho da pesquisa para o primeiro recurso carregado e pode reduzir o conjunto de trabalho.

## <a name="fixing-violations"></a>Corrigir violações
 Para corrigir uma violação dessa regra, adicione o atributo ao assembly e especificar o idioma dos recursos de cultura neutra.

## <a name="specifying-the-language"></a>Especificando o idioma

#### <a name="to-specify-the-language-of-the-resource-of-the-neutral-culture"></a>Para especificar o idioma do recurso de cultura neutra

1. Na **Gerenciador de soluções**, clique em seu projeto e, em seguida, clique em **propriedades**.

2. Na barra de navegação à esquerda, selecione **Application**e, em seguida, clique em **informações de Assembly**.

3. No **informações do Assembly** diálogo caixa, selecione o idioma do **linguagem neutra** lista suspensa.

4. Clique em **OK**.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 É permitido para suprimir um aviso nessa regra. No entanto, pode diminuir o desempenho da inicialização.
