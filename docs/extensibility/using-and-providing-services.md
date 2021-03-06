---
title: Usar e fornecer serviços | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- examples [Visual Studio SDK], services
- Visual Studio, services
- services
ms.assetid: c0b415ba-b825-4da0-9faf-8a60a663e302
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 36f49d4e1ebaa6d8e15e43b821af56204739cb07
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687777"
---
# <a name="using-and-providing-services"></a>Usando e fornecendo serviços
Um serviço é um contrato entre dois VSPackages. Um VSPackage oferece um conjunto específico de interfaces para outro VSPackage consumir. Por exemplo, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oferece o <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> de serviço a qualquer VSPackage ele carrega. Esse serviço fornece o <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> interface, que pode ser usado para gravar no log de atividade. Para obter mais informações, confira [Como: Usar o Log de atividades](../extensibility/how-to-use-the-activity-log.md).

 VSPackages podem oferecer serviços de suas próprias por usar o <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> interface...

 O Visual Studio oferece serviços importantes, como o seguinte:

|Serviço IDE|Descrição|
|-----------------|-----------------|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>|Fornece acesso ao IDE services lidar com a funcionalidade básica, os VSPackages e o registro.|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|Fornece janelas básicas e funcionalidade relacionada à interface do usuário no IDE, como a capacidade de criar ferramentas e janelas de documento.|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|Fornece a funcionalidade básica de relacionadas à solução, como a capacidade de enumerar os projetos, criar novos projetos e monitorar as alterações do projeto.|

## <a name="in-this-section"></a>Nesta seção
- [Fundamentos do serviço](../extensibility/internals/service-essentials.md) apresenta os elementos importantes de um serviço do Visual Studio.

- [Como: Obtenha um serviço](../extensibility/how-to-get-a-service.md) descreve como solicitar (consumir) um serviço.

- [Como: Fornecer um serviço](../extensibility/how-to-provide-a-service.md) discute como fornecer um serviço.

- [Como: Fornecer um serviço assíncrono do Visual Studio](../extensibility/how-to-provide-an-asynchronous-visual-studio-service.md) discute como fornecer um serviço assíncrono.

- [Como: Solucionar problemas de serviços](../extensibility/how-to-troubleshoot-services.md) aborda problemas comuns e apresenta soluções para eles.

## <a name="related-sections"></a>Seções relacionadas
- [SDK do Visual Studio](../extensibility/visual-studio-sdk.md)