---
title: Suporte para persistência de estado | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- state persistence, managed package framework support
- managed package framework, state persistence support
- state, persistence
ms.assetid: d25866f2-8d1f-477f-8aa5-3af3fbbf6e97
caps.latest.revision: 15
manager: jillfra
ms.openlocfilehash: 6dc542d2e410b79a21e436a1881c06bd3cc4eef8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58929527"
---
# <a name="support-for-state-persistence"></a>Suporte para persistência de estado
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pode manter o estado dos objetos comuns. Por exemplo, propriedades de solução e projeto são salvos e restauradas a partir de arquivos de projeto e solução. As configurações do usuário podem ser exportadas para e importadas de arquivos de configurações.  
  
 Os VSPackages normalmente se baseiam no armazenamento local, no registro do sistema ou na pasta de dados do aplicativo para o usuário atual ou o computador. Valores que exigem uma pequena quantidade de espaço de armazenamento, como inteiros e cadeias de caracteres, normalmente são armazenadas no registro do sistema. Os valores que exigem muito espaço para armazenamento, como bitmaps, são salvos em um arquivo. Se o caminho do arquivo pode ser salvos no registro do sistema. O mecanismo de persistência deve ter permissão para acessar o armazenamento local.  
  
## <a name="support-for-locating-local-storage"></a>Suporte para a localização de armazenamento Local  
 O <xref:Microsoft.VisualStudio.Shell.Package> classe oferece suporte para a localização de informações de estado na pasta do sistema do registro ou o aplicativo de dados para o usuário atual ou o computador.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>  
 Retorna o caminho da raiz do registro do computador local para [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], por exemplo, HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0Exp.  
  
 A raiz do Registro local é obtida a <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell> service. Se isso não estiver disponível, ele é obtido do <xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute> atributo do VSPackage.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>  
 Retorna o caminho do usuário atual (por computador) raiz do registro para [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], por exemplo, HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp.  
  
 A raiz do Registro local é obtida a <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell> service. Se isso não estiver disponível, ele é obtido do atributo DefaultLocalRegistryRoot do VSPackage.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserDataPath%2A>  
 Retorna o caminho do diretório que serve como um repositório comum para [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] dados para o usuário móvel atual, por exemplo, C:\Documents and Settings\\*YourAccountName*\Application Data\Microsoft\ VisualStudio\8.0Exp.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserLocalDataPath%2A>  
 Retorna o caminho do diretório que serve como um repositório comum para [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] dados não roaming usuário atual, por exemplo, C:\Documents and Settings\\*YourAccountName*\Local Data\Microsoft\VisualStudio\8.0Exp.  
  
## <a name="see-also"></a>Consulte também  
 [Estado de VSPackage](../misc/vspackage-state.md)