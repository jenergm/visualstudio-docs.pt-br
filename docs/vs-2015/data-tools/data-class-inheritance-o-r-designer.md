---
title: Herança (Object Relational Designer) de classe de dados | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: af32653c-f4e6-4217-8c5a-e32b322b4918
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 37cc40651056b634deb9e81fc7407472485cb72b
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59670154"
---
# <a name="data-class-inheritance-or-designer"></a>Herança de classe de dados (Designer Relacional de Objetos)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Como outros objetos, classes de [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] podem usar a herança e ser derivadas de outras classes. Em código, você pode especificar relações de herança entre objetos declarando uma classe que herda de outra. Em uma base de dados, as relações de herança são criadas de várias maneiras. [!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]) suporta o conceito de herança de tabela única como geralmente é implementado em sistemas relacionais.  
  
 A herança de tabela única, há uma única tabela de base de dados que contém colunas para ambos base e classes derivadas. Com dados relacionais, uma coluna de discriminador contém o valor que determina qual classe qualquer determinado registro pertence. Por exemplo, considere pessoas a tabela que contém todos empregado por uma empresa. Algumas pessoas são funcionários e algumas pessoas são gerentes. A tabela de pessoas contém uma coluna denominada o tipo que possui um valor de 1 para gerentes e um valor de 2 para funcionários. A coluna tipo é a coluna de discriminador. Nesse cenário, você pode criar uma subclasse de funcionários e preencher a classe com apenas os registros que têm um valor de tipo de 2.  
  
 Quando você configura a herança na classe entidade usando [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], arraste a única tabela que contém os dados de herança no designer duas vezes: uma vez para cada classe na hierarquia de herança. Após adicionar tabelas ao designer, conectar-las com um item de herança da caixa de ferramentas de **Object Relational Designer** e então defina as quatro propriedades de herança na janela **Propriedades**.  
  
## <a name="inheritance-properties"></a>Propriedades de herança  
 A seguinte tabela lista as propriedades de herança e suas descrições:  
  
|Propriedade|Descrição|  
|--------------|-----------------|  
|Propriedade Discriminatória|A propriedade (mapeado para a coluna) que determina qual classe ao registro atual pertence.|  
|Valor Discriminador de Classe Base|O valor (na coluna desejada como a propriedade de discriminador) que determina que um registro é a classe base.|  
|Valor Discriminatório da Classe Derivada|O valor (na propriedade designada como a propriedade de discriminador) que determina que um registro é derivada da classe.|  
|Padrão de Herança|A classe que deve ser preenchida quando o valor na propriedade designada como o **propriedade discriminatória** não corresponder a **valor Discriminatório da classe Base** ou o **classe derivada Valor Discriminatório**.|  
  
 Criar um modelo de objeto que usar herança e corresponde a dados relacionais pode ser um pouco confuso. Este tópico fornece informações sobre os conceitos básicos e as propriedades individuais que são necessários configurando a herança. Os tópicos a seguir fornecem uma explicação mais claro de como configurar a herança com [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
|Tópico|Descrição|  
|-----------|-----------------|  
|[Como: Configurar a herança usando o Designer Relacional de Objetos](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)|Descreve como configurar classes de entidade que usam herança de tabela única usando [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].|  
|[Passo a passo: Criando classes LINQ to SQL usando a herança de tabela única (Designer Relacional de Objetos)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)|Fornece instruções passo a passo sobre como configurar classes de entidade que usam herança de tabela única usando [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].|  
  
## <a name="see-also"></a>Consulte também  
 [Ferramentas LINQ to SQL no Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [Passo a passo: Criando Classes LINQ to SQL (Object Relational Designer)](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [Passo a passo: Criando Classes LINQ to SQL, usando a herança de tabela única (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)   
 [Introdução](http://msdn.microsoft.com/library/db8a557a-fef8-4f4f-bb91-8cff7250ee25)
