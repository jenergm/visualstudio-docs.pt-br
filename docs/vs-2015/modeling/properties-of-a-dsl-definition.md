---
title: Propriedades de uma definição de DSL | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, definition file
ms.assetid: 38debcfe-e1a6-4a3f-9d69-3ab07520f2b6
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 804236cadf97dda0b21cf145a4cd4c932e08b097
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58928913"
---
# <a name="properties-of-a-dsl-definition"></a>Propriedades de uma definição de DSL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Definem propriedades de DslDefinition *linguagem específica do domínio* propriedades de definição, como numeração de versão. As propriedades de DslDefinition aparecem na **propriedades** janela quando você clica em uma área aberta do diagrama na *Designer de linguagem específica do domínio*.  
  
 Para obter mais informações, consulte [como definir uma linguagem específica do domínio](../modeling/how-to-define-a-domain-specific-language.md). Para obter mais informações sobre como usar essas propriedades, consulte [personalizando e estendendo uma linguagem específica do domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 DslDefinition tem as propriedades na tabela a seguir:  
  
|Propriedade|Descrição|Padrão|  
|--------------|-----------------|-------------|  
|Modificador de acesso|Determina se o modificador de acesso para a classe de domínio é público ou interno.|públicos|  
|Atributos personalizados|Personalizadas definidas atributos para a classe de domínio.<br /><br /> **Observação** Use o botão Procurar para adicionar um atributo.|\<nenhum>|  
|Nome da empresa|O nome do nome da empresa no registro do sistema.|Nome da empresa atual|  
|Nome|O nome dessa classe de domínio.|Nome atual|  
|Namespace|O namespace afiliado a essa classe de domínio.|Namespace atual|  
|Guid do pacote|O guid para o [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pacote gerado para esta DSL.|\<nenhum>|  
|Namespace do pacote|O namespace para o [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pacote gerado para esta DSL.|\<nenhum>|  
|Nome do produto|O nome do produto que será registrado para o [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pacote gerado para esta DSL.|\<nenhum>|  
|Observações|Anotações associadas a essa classe de domínio.|\<nenhum>|  
|Descrição|Descrição para essa classe de domínio.|\<nenhum>|  
|Nome de Exibição|O nome que será exibido no designer gerado para essa classe de domínio.|\<nenhum>|  
|Palavra-chave de ajuda|A palavra-chave ajuda associada a essa classe de domínio.|\<nenhum>|  
|Build|O número de build incremental para essa definição de linguagem específica do domínio.|0|  
|Versão principal|O número de compilação principal incrementais para esta definição de linguagem específica do domínio.|1|  
|Versão secundária|O número de compilação secundária incrementais para esta definição de linguagem específica do domínio.|0|  
|Revisão|A versão incremental build número para essa definição de linguagem específica do domínio.|0|  
  
## <a name="see-also"></a>Consulte também  
 [Glossário das Ferramentas de Linguagem Específica de Domínio](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
