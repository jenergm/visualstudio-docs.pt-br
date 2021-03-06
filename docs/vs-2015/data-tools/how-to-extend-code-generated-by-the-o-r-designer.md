---
title: 'Como: Estender o código gerado pelo Designer Relational | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: d6d1122e-2f55-4607-8d8b-48c3c22600fb
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d8aa3ecd29180e01a7d6f254303d42ac328aceaa
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085214"
---
# <a name="how-to-extend-code-generated-by-the-or-designer"></a>Como: Estender o código gerado pelo Designer Relacional de Objetos
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O código gerado por [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] é regenerado quando alterações são feitas a classes de entidade e outros objetos ocorrem no designer. Devido a essa regeneração de código, qualquer código que você adicionar ao código gerado seja substituído normalmente quando o código de regenerados de designer. [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] fornece a capacidade de gerar os arquivos parciais da classe em que você pode adicionar código que não será substituído. Um exemplo de adicionar seu próprio código para o código gerado por [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] está adicionando validação de dados para as classes LINQ to SQL (entidade). Para obter mais informações, veja [Como: Adicionar validação a classes de entidade](../data-tools/how-to-add-validation-to-entity-classes.md).  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="adding-code-to-an-entity-class"></a>Adicionando código para uma classe de entidade  
  
#### <a name="to-create-a-partial-class-and-add-code-to-an-entity-class"></a>Para criar uma classe parcial e adicione o código para uma classe de entidade  
  
1. Abra ou crie um novo arquivo LINQ to SQL Classes (**dbml** arquivo) no [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. (Clique duas vezes o **. dbml** arquivo no **Gerenciador de soluções**/**Database Explorer**.)  
  
2. No [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], a classe para o qual você deseja adicionar validação e, em seguida, clique com o botão direito **Exibir código**.  
  
     O editor de códigos abre com uma classe parcial para a classe de entidade selecionada.  
  
3. Adicione o código na declaração de classe parcial para a classe de entidade.  
  
## <a name="adding-code-to-a-datacontext"></a>Adicionando código para um DataContext  
  
#### <a name="to-create-a-partial-class-and-add-code-to-a-datacontext"></a>Para criar uma classe parcial e adicione o código a um DataContext  
  
1. Abra ou crie um novo arquivo LINQ to SQL Classes (**dbml** arquivo) no [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. (Clique duas vezes o **. dbml** arquivo no **Gerenciador de soluções**/**Database Explorer**.)  
  
2. No [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], uma área vazia no designer com o botão direito e, em seguida, clique em **Exibir código**.  
  
     O editor de códigos abre com uma classe parcial para o DataContext.  
  
3. Adicione o código na declaração de classe parcial para o DataContext.  
  
## <a name="see-also"></a>Consulte também  
 [Ferramentas LINQ to SQL no Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [Passo a passo: Criando Classes LINQ to SQL (Object Relational Designer)](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Passo a passo: Adicionando validação a Classes de entidade](http://msdn.microsoft.com/library/85b06a02-b2e3-4534-95b8-d077c8d4c1d7)
