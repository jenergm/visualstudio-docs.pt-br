---
title: Conceitos básicos do serviço | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- services, essentials
ms.assetid: fbe84ad9-efe1-48b1-aba3-b50b90424d47
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6e867c9e83bf353e57d75ee611fe1074efcc9cfe
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60070375"
---
# <a name="service-essentials"></a>Conceitos básicos do serviço
Um serviço é um contrato entre dois VSPackages. Um VSPackage fornece um conjunto específico de interfaces para outro VSPackage consumir. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] é uma coleção de VSPackages que fornece serviços a outros VSPackages.

 Por exemplo, você pode usar o serviço de SVsActivityLog para obter uma interface IVsActivityLog, que pode ser usado para gravar no log de atividades. Para obter mais informações, confira [Como: Usar o Log de atividades](../../extensibility/how-to-use-the-activity-log.md).

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] também fornece alguns serviços internos que não estão registrados. Os VSPackages pode substituir internos ou outros serviços, fornecendo uma substituição de serviço. Somente um serviço de substituição é permitida para qualquer serviço.

 Os serviços não têm nenhuma capacidade de descoberta. Portanto, você deve saber o identificador de serviço (SID) de um serviço que você deseja consumir, e você deve saber quais interfaces que ele fornece. A documentação de referência para o serviço fornece essas informações.

- Os VSPackages que fornecem serviços são chamados de provedores de serviço.

- Serviços que são fornecidos a outros VSPackages são chamados de serviços globais.

- Serviços que estão disponíveis somente para o VSPackage que implementa-los, ou qualquer objeto que ele cria, são chamados de serviços locais.

- Serviços que substituir serviços internos ou serviços fornecidos por outros pacotes, são chamados de substituições de serviço.

- Serviços ou substituições de serviço, são carregadas sob demanda, ou seja, o provedor de serviço é carregado quando o serviço que fornece, é solicitado por outro VSPackage.

- Para dar suporte a carregamento sob demanda, um provedor de serviço registra seus serviços globais com [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Para obter mais informações, confira [Como: Fornecer um serviço](../../extensibility/how-to-provide-a-service.md).

- Depois de obter um serviço, use [QueryInterface](/cpp/atl/queryinterface) (código não gerenciado) ou conversão (código gerenciado) para obter a interface desejada, por exemplo:

  ```vb
  TryCast(GetService(GetType(SVsActivityLog)), IVsActivityLog)
  ```

  ```csharp
  GetService(typeof(SVsActivityLog)) as IVsActivityLog;
  ```

- Código gerenciado se refere a um serviço por seu tipo, enquanto que o código não gerenciado se refere a um serviço pelo seu GUID.

- Quando [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] carrega um VSPackage, ele passa um provedor de serviços para o VSPackage para fornecer o acesso de VSPackage aos serviços globais. Isso é chamado de "localização" VSPackage.

- Os VSPackages pode ser provedores de serviço para os objetos que eles criam. Por exemplo, um formulário pode enviar uma solicitação para um serviço de cor ao seu quadro, que pode passar a solicitação [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

- Objetos gerenciados que estão profundamente aninhados ou não foi localizados, podem chamar <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> para acesso direto aos serviços globais.

<a name="how-to-use-getglobalservice"></a>

## <a name="use-getglobalservice"></a>Usar GetGlobalService

Às vezes, você precisará obter um serviço de uma janela de ferramenta ou controle de contêiner que não tenha sido colocado no local, caso contrário, foi colocado no local com um provedor de serviço que não sabe sobre o serviço que você deseja. Por exemplo, você talvez queira gravar no log de atividade de dentro de um controle. Para obter mais informações sobre esses e outros cenários, consulte [como: Solucionar problemas de serviços](../../extensibility/how-to-troubleshoot-services.md).

Você pode obter a maioria dos serviços do Visual Studio chamando estático <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> método.

<xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> se baseia em um serviço em cache provedor que é inicializado na primeira vez que qualquer VSPackage derivado de pacote é colocado no local. Você deve assegurar que essa condição for atendida, ou então estar preparada para um serviço de nulo.

Felizmente, <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> funciona corretamente na maioria das vezes.

- Se um VSPackage fornece um serviço conhecido apenas outro VSPackage, o VSPackage solicitando o serviço é colocado no local antes do VSPackage fornecendo que o serviço é carregado.

- Se uma janela de ferramenta é criada por um VSPackage, o VSPackage é colocado antes que a janela da ferramenta é criada no local.

- Se um contêiner de controle for hospedado por uma janela de ferramenta criada por um VSPackage, o VSPackage é colocado antes que o contêiner de controle é criado no local.

### <a name="to-get-a-service-from-within-a-tool-window-or-control-container"></a>Para obter um serviço de dentro de um contêiner de controle ou janela de ferramenta

- Inserir este código na janela da ferramenta, construtor ou contêiner de controle:

    ```csharp
    IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog;
        if (log == null) return;
    ```

    ```vb
    Dim log As IVsActivityLog = TryCast(Package.GetGlobalService(GetType(SVsActivityLog)), IVsActivityLog)
    If log Is Nothing Then
        Return
    End If
    ```

    Esse código obtém um serviço SVsActivityLog e converte-o em uma interface IVsActivityLog, que pode ser usada para gravar no log de atividades. Para obter um exemplo, consulte [ Usar o Log de atividades](../../extensibility/how-to-use-the-activity-log.md).

## <a name="see-also"></a>Consulte também

- [Lista de serviços disponíveis](../../extensibility/internals/list-of-available-services.md)
- [Usar e fornecer serviços](../../extensibility/using-and-providing-services.md)
- [Transmissões e conversões de tipo](/dotnet/csharp/programming-guide/types/casting-and-type-conversions)
- [Conversão](/cpp/cpp/casting)