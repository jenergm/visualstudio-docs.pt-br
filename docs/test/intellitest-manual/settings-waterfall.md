---
title: Cascata de configurações | Ferramenta de teste para desenvolvedores do Microsoft IntelliTest
ms.date: 05/02/2017
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 966182ca79ffd06e17642e1b24d6e48b8e637efe
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55923715"
---
# <a name="settings-waterfall"></a>Cascata de configurações

O conceito de cascata de configurações significa que o usuário pode especificar as configurações no nível do **Assembly**, do **Acessório** e da **Exploração**:

* Assembly – [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* Acessório – [PexClass](attribute-glossary.md#pexclass)
* Exploração – [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

As configurações especificadas no nível do **Assembly** afetam todos os acessórios e as explorações sob esse assembly. As configurações especificadas no nível do **Acessório** afetam todas as explorações sob esse acessório. As configurações filho têm prioridade: se uma configuração for definida nos níveis do **Assembly** e do **Acessório**, serão usadas as configurações do **Acessório**.

Observe que algumas configurações são específicas para o nível do **Assembly** ou para o nível do **Acessório**.

**Exemplo**

```csharp
using Microsoft.Pex.Framework;

[assembly: PexAssemblySettings(MaxBranches = 1000)] // we override the default value of maxbranches

namespace MyTests
{
    [PexClass(MaxBranches = 500)] // we override the 1000 value and set maxbranches to 500
    public partial class MyTests
    {
        [PexMethod(MaxBranches = 100)] // we override again, maxbranches = 100
        public void MyTest(...) { ... }
    }
}
```

## <a name="got-feedback"></a>Recebeu comentários?

Poste suas ideias e solicitações de recursos na [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com/content/idea/post.html?space=8).