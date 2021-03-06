---
title: Suplemento de exemplo do Excel para testes de IU codificados| Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, Excel Add-in sample
ms.assetid: 2cd52d1a-4c35-43ca-8a84-9c79dabd907f
caps.latest.revision: 18
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 30ba0d48676438f19581e93a3af3c900569f5d5d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60112197"
---
# <a name="sample-excel-add-in-for-coded-ui-testing"></a>Complemento do Excel de amostra para testes de IU codificado
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Este suplemento de exemplo para [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] foi projetado especificamente para dar suporte a testes de IU codificados de planilhas do Excel que são registrados e executados no Visual Studio Enterprise. O suplemento é criado usando o Visual Studio Tools para Office.  
  
 Para obter mais informações sobre como criar um suplemento do Excel, consulte [passo a passo: Criação do suplemento do VSTO primeiro seu para Excel](http://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f) ou pesquise no MSDN para "Excel Add-In".  
  
 Embora o suplemento do Excel não seja o assunto principal desta documentação da extensão de teste de IU codificado para Excel, alguns comentários podem ser úteis.  
  
 As partes importantes deste suplemento:  
  
- Classe `ThisAddIn` – gerencia o canal de comunicação remota do .NET entre o `ExcelUICommunicator` e a [Extensão de teste de IU codificado de exemplo para Excel](../test/sample-coded-ui-test-extension-for-excel.md).  
  
- `ExcelCodedUIAddinHelper_TemporaryKey.pfx` – um certificado de segurança para testar o suplemento.  
  
- Classe `ExcelUICommunicator` – essa classe implementa a interface `IExcelUICommunication`.  
  
## <a name="thisaddin-class"></a>Classe ThisAddIn  
 A maior parte dessa classe, na verdade, é gerada pelo Visual Studio Tools para Office no arquivo `ThisAddIn.Designer.cs` quando você cria o projeto de suplemento do Excel.  
  
 Os membros que você deve implementar são os manipuladores de eventos: `ThisAddIn_Startup()` e `ThisAddIn_Shutdown()`. Sua finalidade é inicializar ou fechar o canal de comunicação remota do .NET que é usado pelo `ExcelUICommunicator`.  
  
## <a name="excelcodeduiaddinhelpertemporarykeypfx"></a>ExcelCodedUIAddinHelper_TemporaryKey.pfx  
 Esse arquivo contém um certificado de segurança temporário que é gerado pelo Visual Studio Tools para Office e concederá permissão ao assembly do suplemento para operar no processo do Excel para testar o suplemento e a extensão. Você deve excluir esse certificado e crie um novo na guia **Assinatura** da janela **Propriedades** do projeto ou anexe seu próprio certificado de teste.  
  
## <a name="exceluicommunicator-class"></a>Classe ExcelUICommunicator  
 Essa classe implementa a interface `IExcelUITestCommunication` e obtém as informações de interface do usuário solicitadas do modelo de objeto do Excel. Para obter mais informações, consulte [Interface de comunicador do Excel de amostra](../test/sample-excel-communicator-interface.md).  
  
## <a name="see-also"></a>Consulte também  
 [Estendendo testes de IU codificados e gravações da ação para dar suporte ao Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)   
 [Passo a passo: Criando seu primeiro suplemento VSTO para Excel](http://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)   
 [Desenvolvimento do Office e do SharePoint](http://msdn.microsoft.com/library/2ddec047-263a-4901-a54c-a15fc8472329)
