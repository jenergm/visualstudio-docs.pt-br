---
title: Conectar a dados em um banco de dados do Access (Windows Forms) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- databases, connecting to
- databases, Access
- data [Visual Studio], connecting
- connecting to data, from Access databases
- Access databases, connecting
ms.assetid: 4159e815-d430-4ad0-a234-e4125fcbef18
caps.latest.revision: 32
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 10b4efd574dd5829e4717b168dc4e565476e9b52
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60102936"
---
# <a name="connect-to-data-in-an-access-database-windows-forms"></a>Conectar-se a dados em um banco de dados do Access (Windows Forms)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode se conectar a um banco de dados do Access (um arquivo. mdf ou um arquivo. accdb) usando o Visual Studio. Depois de definir a conexão, os dados são exibidos na janela **Fontes de Dados**. Nela, é possível arrastar tabelas ou exibições para os formulários.  
  
## <a name="prerequisites"></a>Pré-requisitos  
 Para usar esses procedimentos, você precisa de um projeto de aplicativo do Windows Forms e um banco de dados do Access (arquivo. accdb) ou um banco de dados do Access 2000-2003 (arquivo. mdb). Siga o procedimento correspondente ao tipo de arquivo.  
  
## <a name="creating-the-dataset-for-an-accdb-file"></a>Criando o Conjunto de Dados para um arquivo .accdb  
 Você pode se conectar aos bancos de dados criados por meio de Access 2013, Office 365, Access 2010 ou Access 2007 usando o procedimento a seguir.  
  
#### <a name="to-create-the-dataset"></a>Para criar o conjunto de dados  
  
1. Abra o aplicativo do Windows Forms ao qual você deseja conectar dados.  
  
2. Sobre o **modo de exibição** menu, selecione **Other Windows** > **fontes de dados**.  
  
     ![Exibir outras fontes de dados do Windows](../data-tools/media/viewdatasources.png "ViewDataSources")  
  
3. Na janela **Fontes de Dados**, clique em **Adicionar Nova Fonte de Dados**.  
  
     ![Adicionar nova fonte de dados](../data-tools/media/dataaddnewdatasource.png "dataAddNewDataSource")  
  
4. Selecione **banco de dados** sobre o **escolher um tipo de fonte de dados** página e, em seguida, selecione **próxima**.  
  
5. Selecione **conjunto de dados** sobre o **escolha um modelo de banco de dados** página e, em seguida, selecione **próxima**.  
  
6. Na página **Escolha a Conexão de Dados**, selecione **Nova Conexão** para configurar uma nova conexão de dados.  
  
7. Alterar o **fonte de dados** à **.NET Framework Data Provider para OLE DB**.  
  
     ![Alterar o provedor de dados para o banco de dados OLE](../data-tools/media/datachangedatasourceoledb.png "dataChangeDataSourceOLEDB")  
  
    > [!IMPORTANT]
    >  Embora uma fonte de dados do **arquivo de banco de dados do Microsoft Access (OLE DB)** parece ser a escolha certa, você usar esse tipo de fonte de dados somente para arquivos de banco de dados. mdb.  
  
8. Na **OLE DB Provider**, selecione **Microsoft Office 12.0 Access Database Engine OLE DB Provider**.  
  
     ![OLE DB Provider do Microsoft Office 12.0 Access](../data-tools/media/dataoledbprovideroffice12access.png "dataOLEDBProviderOffice12Access")  
  
9. Na **nome do servidor ou o arquivo**, especifique o caminho e nome do arquivo. accdb ao qual você deseja se conectar e, em seguida, selecione **Okey**.  
  
    > [!NOTE]
    >  Se o arquivo de banco de dados tem um nome de usuário e senha, especifique-os antes de selecionar **Okey**.  
  
10. Selecione **próxima** sobre o **escolha sua Conexão de dados** página.  
  
11. Selecione **próxima** sobre o **salvar a cadeia de caracteres de conexão para o arquivo de configuração de aplicativo** página.  
  
12. Expanda o nó **Tabelas** na página **Escolher Objetos do Banco de Dados**.  
  
13. Selecione quaisquer tabelas ou exibições que você deseja em seu conjunto de dados e, em seguida, selecione **concluir**.  
  
     O Conjunto de Dados é adicionado ao projeto e as tabelas e as exibições são mostradas na janela **Fontes de Dados**.  
  
## <a name="creating-the-dataset-for-an-mdb-file"></a>Criando o conjunto de dados para um arquivo. mdb  
 Você cria o conjunto de dados executando o **Assistente de Configuração de Fonte de Dados**.  
  
#### <a name="to-create-the-dataset"></a>Para criar o conjunto de dados  
  
1. Abra o aplicativo do Windows Forms ao qual você deseja conectar dados.  
  
2. Sobre o **modo de exibição** menu, selecione **Other Windows** > **fontes de dados**.  
  
     ![Exibir outras fontes de dados do Windows](../data-tools/media/viewdatasources.png "ViewDataSources")  
  
3. Na janela **Fontes de Dados**, clique em **Adicionar Nova Fonte de Dados**.  
  
4. Selecione **banco de dados** sobre o **escolher um tipo de fonte de dados** página e, em seguida, selecione **próxima**.  
  
5. Selecione **conjunto de dados** sobre o **escolha um modelo de banco de dados** página e, em seguida, selecione **próxima**.  
  
6. Na página **Escolha a Conexão de Dados**, selecione **Nova Conexão** para configurar uma nova conexão de dados.  
  
7. Se a fonte de dados não for **arquivo de banco de dados do Microsoft Access (OLE DB)**, selecione **alteração** para abrir o **alterar fonte de dados** caixa de diálogo e selecione **Microsoft Acessar o arquivo de banco de dados**e, em seguida, selecione **Okey**.  
  
8. No **nome do arquivo de banco de dados**, especifique o caminho e nome do arquivo. mdb ao qual você deseja se conectar e, em seguida, selecione **Okey**.  
  
     ![Adicionar o arquivo de banco de dados de acesso de Conexão](../data-tools/media/dataaddconnectionaccessmdb.png "dataAddConnectionAccessMDB")  
  
9. Selecione **próxima** sobre o **escolha sua Conexão de dados** página.  
  
10. Selecione **próxima** sobre o **salvar a cadeia de caracteres de conexão para o arquivo de configuração de aplicativo** página.  
  
11. Expanda o nó **Tabelas** na página **Escolher Objetos do Banco de Dados**.  
  
12. Selecione quaisquer tabelas ou exibições que você deseja em seu conjunto de dados e, em seguida, selecione **concluir**.  
  
     O Conjunto de Dados é adicionado ao projeto e as tabelas e as exibições são mostradas na janela **Fontes de Dados**.  
  
## <a name="security"></a>Segurança  
 O armazenamento das informações confidenciais (como uma senha) pode afetar a segurança do aplicativo. O uso da Autenticação do Windows (também conhecida como segurança integrada) é uma maneira mais segura de controlar o acesso a um banco de dados. Para obter mais informações, consulte [Protegendo informações de conexão](http://msdn.microsoft.com/library/1471f580-bcd4-4046-bdaf-d2541ecda2f4).  
  
## <a name="next-steps"></a>Próximas etapas  
 O conjunto de dados que você acabou de criar agora está disponível na **fontes de dados** janela. Agora é possível realizar qualquer uma das seguintes tarefas:  
  
- Selecione os itens na **fontes de dados** janela e arrastá-los para seu formulário (consulte [controla a associar o Windows Forms a dados no Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)).  
  
- Abra a fonte de dados no Dataset Designer para adicionar ou editar os objetos que compõem o conjunto de dados.  
  
- Adicionar lógica de validação para o <xref:System.Data.DataTable.ColumnChanging> ou <xref:System.Data.DataTable.RowChanging> eventos das tabelas de dados no conjunto de dados (consulte [validar dados em conjuntos de dados](../data-tools/validate-data-in-datasets.md)).  
  
## <a name="see-also"></a>Consulte também

 [Preparando o aplicativo para receber dados](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [Associar controles a dados no Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [Validando dados](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [Instruções passo a passo de dados](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)