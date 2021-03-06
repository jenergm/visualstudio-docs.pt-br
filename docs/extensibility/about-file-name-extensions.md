---
title: Sobre extensões de nome de arquivo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9998a8a07995f866b1833736b96e2884c5cba091
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678391"
---
# <a name="about-file-name-extensions"></a>Sobre extensões de nome de arquivo
Quando você registra uma extensão de arquivo de um VSPackage, associá-la com uma versão do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Isso é importante se mais de uma versão de [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] é instalado em um computador.

 Extensões de arquivo para os VSPackages são registradas em **HKEY_CLASSES_ROOT** chave com um valor padrão que aponta para o identificador associado programático (ProgID).

 O exemplo a seguir mostra informações de registro para o *vcproj* extensão de arquivo:

```
HKEY_CLASSES_ROOT\
   .vcproj\
      (default)=" VisualStudio.vcproj.8.0"
```

 Arquivos associados [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] devem ter um ProgID com controle de versão, como `VisualStudio.vcproj.8.0`. Um ProgID com controle de versão permite instalações lado a lado do produto para manter as associações de extensão de arquivo entre as versões do produto. Um ProgID específico da versão também permite que você use verbos padrão, como abrir, editar e assim por diante, sem a preocupação de substituir ou ser substituído por outros aplicativos ou versões do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

 Em alguns casos, o ProgID associado com uma extensão de arquivo não deve ser alterado. Por exemplo, o ProgID para o *. htm* extensão de arquivo (progid = htmlfile) é embutido no código em vários locais no sistema operacional e é amplamente conhecida e usada em associação com *. htm* e *. HTML* arquivos.

## <a name="see-also"></a>Consulte também
- [Registrar as extensões de nome de arquivo para implantações lado a lado](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)
- [Especificar identificadores de arquivo para extensões de nome de arquivo](../extensibility/specifying-file-handlers-for-file-name-extensions.md)