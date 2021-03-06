---
title: A conexão selecionada usa um provedor de base de dados sem suporte
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: e6ebdca67dd87f25111ba48c3d9baa346d00e4db
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55923805"
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>A conexão selecionada usa um provedor de base de dados sem suporte

Esta mensagem aparece quando você arrasta itens que não usam o .NET Framework Data Provider para SQL Server a partir **Gerenciador de servidores** ou **Database Explorer** até o [LINQ to SQL das ferramentas no Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md).

O **Relational Designer** dá suporte a apenas as conexões de dados que usam o provedor .NET Framework para SQL Server. Somente as conexões a Microsoft SQL Server ou o Arquivo base de dados do Microsoft SQL Server são válidos.

Para corrigir esse erro, adicionar itens somente as conexões de dados que usam o .NET Framework Data Provider para SQL Server para o **Relational Designer**.

## <a name="see-also"></a>Consulte também

- <xref:System.Data.SqlClient>
- [Mensagens do O/R Designer](../data-tools/o-r-designer-messages.md)
- [Ferramentas do LINQ to SQL no Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
