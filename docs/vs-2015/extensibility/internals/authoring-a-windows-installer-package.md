---
title: Criação de um pacote do Windows Installer | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- .msi files, VSPackages
- msi files, VSPackages
ms.assetid: 0ce7c21d-0d3f-47fe-a0bb-eed506e32609
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 30c941fd4f3c281dfe363d284a559bafe055451c
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "59000097"
---
# <a name="authoring-a-windows-installer-package"></a>Criação de um pacote do Windows Installer
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

O modelo do Windows Installer unidades de dados. Em vez de escrever um script de procedimento para copiar arquivos e gravar as entradas do registro, por exemplo, você cria linhas e colunas em tabelas de banco de dados que contêm dados de arquivo e registro.  
  
## <a name="database-entries"></a>Entradas de banco de dados  
 Para instalar um VSPackage, um pacote do Windows Installer deve conter entradas de banco de dados para executar as seguintes tarefas:  
  
- Pesquisar para localizar as versões do sistema [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] o VSPackage dá suporte a (usando tabelas do Windows Installer que incluem AppSearch, CompLocator, RegLocator, DrLocator e assinatura).  
  
- Cancelar a instalação, se nenhuma versão com suporte do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] está instalado ou se outro requisito de sistema do VSPackage não for atendido (usando a tabela de LaunchCondition).  
  
- Instale o VSPackage e os arquivos dependentes (usando o diretório, componente e tabelas de arquivo).  
  
- Adicione as informações apropriadas para o VSPackage no registro (usando a tabela de registro).  
  
- Integrar o VSPackage na [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] chamando **devenv.exe /setup** (usando a tabela CustomAction).  
  
  Para obter mais informações, consulte [Windows Installer](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx).  
  
## <a name="setup-tools"></a>Ferramentas de instalação  
 Uma variedade de ferramentas de configuração de produtos de terceiros fornecem um ambiente de desenvolvimento para pacotes do Windows Installer. Duas ferramentas gratuitas são as seguintes:  
  
- InstallShield Limited Edition  
  
   Você pode obter uma versão limitada do InstallShield por meio do Visual Studio **novo projeto** caixa de diálogo. Expandir **Other Project Types** e, em seguida, selecione **instalação e implantação**. Selecione o modelo do InstallShield.  
  
- Conjunto de Ferramentas XML do Windows Installer  
  
   O conjunto de ferramentas cria pacotes do Windows Installer XML dos arquivos de origem. O conjunto de ferramentas é um projeto de código-fonte aberto da Microsoft. Você pode baixar o código-fonte e os executáveis do [ http://sourceforge.net/projects/wix ](http://sourceforge.net/projects/wix).  
  
  Para os produtos comerciais que se integram [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] usando o [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)], consulte [ https://marketplace.visualstudio.com/ ](https://marketplace.visualstudio.com/).  
  
## <a name="see-also"></a>Consulte também  
 [Instalar VSPackages com o Windows Installer](../../extensibility/internals/installing-vspackages-with-windows-installer.md)
