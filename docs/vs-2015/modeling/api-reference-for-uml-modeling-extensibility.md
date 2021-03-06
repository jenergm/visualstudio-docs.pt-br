---
title: Referência da API para extensibilidade de modelagem UML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- UML - extending
- UML API
- UML model, API
ms.assetid: 2b2ffe93-c358-4d28-a5e5-3d0474629b58
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 12eadb9844df5da78b11367708fed715f1c13672
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58926375"
---
# <a name="api-reference-for-uml-modeling-extensibility"></a>Referência de API para extensibilidade de modelagem UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode escrever o código de programa para ler e modificar os modelos que você cria com o Visual Studio. A referência de API fornece informações sobre as classes específicas para ajudá-lo com isso. Para obter mais informações e orientados a tarefas, consulte os tópicos em [modelos e diagramas UML estender](../modeling/extend-uml-models-and-diagrams.md). Para ver quais versões do Visual Studio dão suporte a modelos UML, consulte [suporte de versão para a arquitetura e ferramentas de modelagem](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="assemblies"></a>Assemblies  
  
|Assembly|O que isso permite que você faça|  
|--------------|--------------------------------|  
|Microsoft.VisualStudio.Uml.Interfaces.dll|-Ler e alterar os elementos de modelo como IUseCase, IAssociation e assim por diante.<br />-Navegar em relações entre elementos.<br /><br /> Os namespaces e tipos correspondem às que são definidos na especificação de UML.|  
|Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll|-Criar novas instâncias de elementos de modelo<br />-Acessar e modificar formas e diagramas.|  
  
## <a name="see-also"></a>Consulte também  
 [Estender modelos e diagramas UML](../modeling/extend-uml-models-and-diagrams.md)   
 [Referência de API do SDK de Modelagem para Visual Studio](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)
