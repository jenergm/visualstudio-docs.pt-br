---
title: 'Como: Criar herança entre tipos (Designer de classe) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.inheritanceline
helpviewer_keywords:
- inheritance, relationship defining
- relationships, defining inheritance
ms.assetid: 3786a21c-8022-4bf5-9d13-740fd354e93c
caps.latest.revision: 34
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2c0e8594014848bee103c65127b5edb7ad969284
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60104688"
---
# <a name="how-to-create-inheritance-between-types-class-designer"></a>Como: Criar herança entre tipos (Designer de Classe) 
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para criar uma relação de herança entre dois tipos em um diagrama de classes usando o Designer de Classe, conecte o tipo de base ao seu tipo ou tipos derivados. Você pode ter uma relação de herança entre duas classes, entre uma classe e uma interface ou entre duas interfaces.  
  
### <a name="to-create-an-inheritance-between-types"></a>Para criar uma herança entre tipos  
  
1. No seu projeto localizado no Gerenciador de Soluções, abra um arquivo de diagrama de classes (.cd).  
  
     Se você não possuir um diagrama de classes, crie um. Confira [Como Adicionar diagramas de classe a projetos (Designer de classe)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).  
  
2. Na **Caixa de Ferramentas**, no **Designer de Classe**, clique em **Herança**.  
  
3. No diagrama de classes, desenhe uma linha de herança entre os tipos que você deseja, começando de:  
  
    - Uma classe derivada para uma classe base  
  
    - Uma classe de implementação para uma interface implementada  
  
    - Uma interface em extensão para uma interface estendida  
  
4. Se desejar, quando você tiver um tipo derivado de um tipo genérico, clique na linha de herança. Na janela **Propriedades**, defina a propriedade **Argumentos de Tipo** para corresponder ao tipo que você deseja para o tipo genérico.  
  
    > [!NOTE]
    >  Se uma classe abstrata pai contiver pelo menos um membro abstrato, todos os membros abstratos serão implementados como classes de herança não abstratas.   
    >   
    >  Embora você possa visualizar os tipos genéricos existentes, não é possível criar novos tipos genéricos. Você também não pode alterar os parâmetros de tipos genéricos existentes.  
  
## <a name="see-also"></a>Consulte também  
 [Herança](http://msdn.microsoft.com/library/81d64ee4-50f9-4d6c-a8dc-257c348d2eea)   
 [Noções básicas sobre herança](http://msdn.microsoft.com/library/dfc8deba-f5b3-4d1d-a937-7cb826446fc5)   
 [Como: Exibir herança entre tipos (Designer de classe)](../ide/how-to-view-inheritance-between-types-class-designer.md)   
 [Classes do Visual C++ no Designer de Classe](../ide/visual-cpp-classes-in-class-designer.md)
