---
title: '&lt;Descrição&gt; elemento (desenvolvimento do Office no Visual Studio)'
titleSuffix: ''
ms.custom: secdec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- description element
- <description> element
- application manifests [Office development in Visual Studio], <description> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ede5ac920c1d40402504544a13f8a00905b82e80
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54871319"
---
# <a name="ltdescriptiongt-element-office-development-in-visual-studio"></a>&lt;Descrição&gt; elemento (desenvolvimento do Office no Visual Studio)
  O `description` elemento o `vstov4` namespace armazena a descrição para a solução do Office que aparece na caixa de diálogo COM os suplementos de aplicativos do Microsoft Office.

## <a name="syntax"></a>Sintaxe

```xml
<description>
</description>
```

## <a name="elements-and-attributes"></a>Elementos e atributos
 Opcional. O `description` elemento está na `vstov4` namespace. Ele contém a descrição do que o suplemento que aparece na caixa de diálogo COM os suplementos de aplicativos do Microsoft Office.

 O `description` elemento não tem atributos ou elementos.

## <a name="vsto-add-in-example"></a>Exemplo de suplemento do VSTO

### <a name="description"></a>Descrição
 O exemplo de código a seguir ilustra a `description` elemento para uma solução de nível de aplicativo implantado usando [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Este exemplo de código é parte de um exemplo maior fornecido no [manifestos de aplicativo para soluções do Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Código

```xml
<vstov4:description>
  ContosoOutlookAddIn - Outlook add-in
  created with Visual Studio Tools for Office
</vstov4:description>
```

## <a name="see-also"></a>Consulte também

- [Manifestos de aplicativo para soluções do Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifestos de implantação para soluções do Office](../vsto/deployment-manifests-for-office-solutions.md)
- [Manifesto do aplicativo ClickOnce](../deployment/clickonce-application-manifest.md)