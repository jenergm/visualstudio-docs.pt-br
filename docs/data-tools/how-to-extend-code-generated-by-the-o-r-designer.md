---
title: 'Como: Estender o código gerado pelo Designer Relacional de Objetos'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d6d1122e-2f55-4607-8d8b-48c3c22600fb
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: e82166ab336023812c63045c031b81d94dea67e0
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60066240"
---
# <a name="how-to-extend-code-generated-by-the-or-designer"></a>Como: Estender o código gerado pelo Designer Relacional de Objetos
Código gerado pelo **Relational Designer** é regenerado quando alterações são feitas para as classes de entidade e outros objetos na superfície do designer. Devido a essa regeneração de código, qualquer código que você adicionar ao código gerado seja substituído normalmente quando o código de regenerados de designer. O **Relational Designer** fornece a capacidade de gerar arquivos de classe parcial na qual você pode adicionar código que não será substituído. Um exemplo de como adicionar seu próprio código para o código gerado pelo **Relational Designer** está adicionando validação de dados a LINQ para classes SQL (entidade). Para obter mais informações, confira [Como: Adicionar validação a classes de entidade](../data-tools/how-to-add-validation-to-entity-classes.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="add-code-to-an-entity-class"></a>Adicione código para uma classe de entidade

### <a name="to-create-a-partial-class-and-add-code-to-an-entity-class"></a>Para criar uma classe parcial e adicione o código para uma classe de entidade

1. Abra ou crie um novo arquivo LINQ to SQL Classes (**dbml** arquivo) na **Relational Designer**. (Clique duas vezes o **. dbml** arquivo no **Gerenciador de soluções** ou **Database Explorer**.)

2. No **Designer Relacional de Objetos**, clique com o botão direito do mouse na classe para qual você deseja adicionar validação e clique em **Exibir Código**.

     O editor de códigos abre com uma classe parcial para a classe de entidade selecionada.

3. Adicione o código na declaração de classe parcial para a classe de entidade.

## <a name="add-code-to-a-datacontext"></a>Adicione código para um DataContext

### <a name="to-create-a-partial-class-and-add-code-to-a-datacontext"></a>Para criar uma classe parcial e adicione o código a um DataContext

1. Abra ou crie um novo arquivo LINQ to SQL Classes (**dbml** arquivo) na **Relational Designer**. (Clique duas vezes o **. dbml** arquivo no **Gerenciador de soluções** ou **Database Explorer**.)

2. No **Relational Designer**, uma área vazia no designer com o botão direito e, em seguida, clique em **Exibir código**.

     O editor de códigos abre com uma classe parcial para o DataContext.

3. Adicione o código na declaração de classe parcial para o DataContext.

## <a name="see-also"></a>Consulte também

- [Ferramentas do LINQ to SQL no Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Passo a passo: Criando o LINQ para SQL classes (Object Relational Designer)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)