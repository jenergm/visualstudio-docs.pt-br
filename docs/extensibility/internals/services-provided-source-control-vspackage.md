---
title: Os serviços fornecidos (VSPackage de controle do código-fonte) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4f9a4a873f2b6b3f41bd86d046bc187c17f063f1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56601147"
---
# <a name="services-provided-source-control-vspackage"></a>Serviços fornecidos (VSPackage de controle do código-fonte)
Os serviços são o mecanismo principal por meio do qual funcionalidade é compartilhada entre os VSPackages e entre o ambiente de desenvolvimento integrado (IDE) do Visual Studio e seu VSPackages instalado. Para obter uma descrição detalhada dos serviços e sua importância no IDE do Visual Studio, consulte[Using e fornecendo serviços](../../extensibility/using-and-providing-services.md).

## <a name="the-source-control-service"></a>O serviço de controle do código-fonte
 O Visual Studio fornece duas camadas de serviços, serviços de nível de IDE e serviços de nível de pacote. Modo nativo, o IDE do Visual Studio fornece serviços de nível de IDE. O pacote de controle de origem consome alguns desses serviços. O pacote de controle do código-fonte como um VSPackage compartilha sua funcionalidade de controle do código-fonte, fornecendo um serviço de controle de origem particular do seu próprio. O pacote de controle do código-fonte encapsula o conjunto de interfaces relacionadas ao controle de origem implementada por ele na forma de um contrato que pode ser usado pelo IDE do Visual Studio.

## <a name="see-also"></a>Consulte também
- [Elementos de design](../../extensibility/internals/source-control-vspackage-design-elements.md)