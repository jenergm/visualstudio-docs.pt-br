---
title: 'Como: Criar modelos de projeto | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- Visual Studio templates, creating project templates
- project templates, metadata files
- Visual Studio templates, project templates
- project templates, custom template locations
- project templates, creating
ms.assetid: a1a6999d-a34c-48a8-b1cf-027eb5c76398
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 918462bff3c2ac8dc57cb9c2c55a7d901707683c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60051538"
---
# <a name="how-to-create-project-templates"></a>Como: Criar modelos de projeto
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Este procedimento permite criar um modelo usando o assistente de **Exportação de Modelo**, que empacota seu modelo em um arquivo .zip. Também é possível criar modelos no formato de arquivo VSIX para implantação aprimorada usando a extensão do Assistente para Exportação de Modelo, usando modelos incluídos no [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)], ou você pode, ainda, criar modelos manualmente.  
  
### <a name="to-create-a-custom-project-template-with-the-standard-export-template-wizard"></a>Para criar um modelo de projeto personalizado com o Assistente de Exportação de Modelo padrão  
  
1. Criar um projeto.  
  
    > [!NOTE]
    >  Use apenas caracteres identificadores válidos para nomear um projeto que será a origem de um modelo. Um modelo exportado de um projeto nomeado com caracteres inválidos pode causar erros de compilação em projetos futuros baseados no modelo. Para obter mais informações sobre caracteres identificadores válidos, consulte [Nomes de Elementos Declarados](http://msdn.microsoft.com/library/09d8843b-c0dc-4afe-9dab-87c439a69e66).  
  
2. Edite o projeto até que ele esteja pronto para ser exportado como um modelo.  
  
3. Conforme apropriado, edite os arquivos de código para indicar em que ponto a substituição de parâmetro deve ocorrer. Para obter mais informações sobre substituição de parâmetro, consulte [como: Substituir parâmetros em um modelo](../ide/how-to-substitute-parameters-in-a-template.md).  
  
4. No menu **Arquivo**, clique em **Exportar Modelo**. O assistente de **Exportação de Modelo** é aberto.  
  
5. Clique em **Modelo de Projeto**.  
  
6. Se você tiver mais de um projeto em sua solução atual, selecione os projetos que deseja exportar como um modelo.  
  
7. Clique em **Avançar**.  
  
8. Selecione um ícone e uma imagem de visualização para o modelo. Eles aparecerão na caixa de diálogo **Novo Projeto**.  
  
9. Insira um nome e uma descrição para o modelo.  
  
10. Clique em **Finalizar**. Seu projeto é exportado para um arquivo .zip e colocado no local de saída especificado e, se selecionado, é importado para [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
     Se tiver o [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] instalado, você poderá encapsular o modelo concluído em um arquivo .vsix para implantação usando o modelo **VSIX Project**. Para obter mais informações, consulte [Introdução ao modelo de projeto do VSIX](../extensibility/getting-started-with-the-vsix-project-template.md).  
  
## <a name="see-also"></a>Consulte também  
 [Criando modelos de projeto e de item](../ide/creating-project-and-item-templates.md)   
 [Como: Criar modelos de item](../ide/how-to-create-item-templates.md)
