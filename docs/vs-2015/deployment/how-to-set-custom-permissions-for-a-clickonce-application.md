---
title: 'Como: Definir permissões personalizadas para um aplicativo ClickOnce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, permissions
- permissions, ClickOnce applications
ms.assetid: 660459ca-ef73-44a8-b323-610001f63b93
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6fa16f3587e0d70d8604aeadb33ee7807f6a22ea
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085656"
---
# <a name="how-to-set-custom-permissions-for-a-clickonce-application"></a>Como: Definir permissões personalizadas para um aplicativo ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode implantar um [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicativo que usa as permissões padrão para as zonas de Internet ou Intranet Local. Como alternativa, você pode criar uma zona personalizada para as permissões específicas que o aplicativo precisa. Você pode fazer isso ao personalizar as permissões de segurança na **segurança** página do **Designer de projeto**.  
  
### <a name="to-customize-a-permission"></a>Para personalizar uma permissão  
  
1. Com um projeto selecionado no **Gerenciador de Soluções**, no menu **Projeto**, clique em **Propriedades**.  
  
2. Clique na guia **Segurança**.  
  
3. Selecione o **Habilitar configurações de segurança do ClickOnce** caixa de seleção.  
  
4. Selecione o **este é um aplicativo de confiança parcial** botão de opção.  
  
     Os controles na **permissões de segurança do ClickOnce** seção estão habilitados.  
  
5. Dos **seu aplicativo será instalado a partir de zona** lista suspensa, clique em **(personalizada)**.  
  
6. Clique em **Editar XML de permissões**.  
  
     O arquivo App. manifest é aberto no Editor de XML.  
  
7. Antes do `</applicationRequestMinimum>` elemento, adicione o código XML para as permissões que seu aplicativo requer.  
  
    > [!NOTE]
    >  Você pode usar o `ToXml` método de uma permissão definida para gerar o código XML para o manifesto do aplicativo. Por exemplo, para gerar o XML para o <xref:System.Security.Permissions.EnvironmentPermission> conjunto de permissões, chame o <xref:System.Security.Permissions.EnvironmentPermission.ToXml%2A> método. Para obter mais informações sobre a estrutura da permissão do conjunto de XML, consulte [NIB: Como: Importar um conjunto de permissões usando um arquivo XML](http://msdn.microsoft.com/dea16b54-c108-408a-ac36-cdc05f746236).  
  
## <a name="see-also"></a>Consulte também  
 [Protegendo aplicativos ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Segurança de acesso do código para aplicativos ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Protegendo aplicativos ClickOnce](../deployment/securing-clickonce-applications.md)
