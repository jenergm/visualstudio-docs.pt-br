---
title: Usar como destino as versões anteriores do .NET Framework no F#
description: Saiba mais sobre como usar como destino a versão mais antiga do .NET Framework ao usar o F# no Visual Studio.
ms.date: 07/11/2018
ms.topic: troubleshooting
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 3572e48328317634f036e8c1301d81c38314a21c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547878"
---
# <a name="target-older-versions-of-net-f"></a>Usar como destino as versões mais antigas do .NET (F#)

O seguinte erro poderá ser exibido se você tentar usar como destino o .NET Framework 2.0, 3.0 ou 3.5 em um projeto do F# quando o Visual Studio estiver instalado no Windows 8.1:

**Este projeto exige o tempo de execução do F# 2.0, mas esse tempo de execução não está instalado.**

Esse erro costuma ocorrer na seguinte combinação de condições:

- Você instalou o Visual Studio no Windows 8.1.

- Você não habilitou o .NET Framework 3.5 antes de instalar o Visual Studio.

- O projeto é direcionado ao .NET Framework 2.0, 3.0 ou 3.5.

Quando você instala o Visual Studio, ele detecta as versões instaladas do .NET Framework. O Visual Studio instala o tempo de execução do F# 2.0 somente se o .NET Framework 3.5 está instalado e habilitado.

## <a name="resolve-the-error"></a>Resolver o erro

Para resolver esse erro, você pode:

- Usar como destino uma versão mais recente do .NET Framework.

- Habilitar o .NET Framework 3.5 no Windows 8.1 e, em seguida, instalar o tempo de execução do F# 2.0 ao reparar a instalação do Visual Studio. Veja a seguir as etapas para fazer isso.

### <a name="to-enable-the-net-framework-35-on-windows-81"></a>Para habilitar o .NET Framework 3.5 no Windows 8.1

1. Na tela **Iniciar**, digite **Painel de Controle**.

   Conforme você digita, o ícone do **Painel de Controle** é exibido no cabeçalho **Aplicativos**.

2. Escolha o ícone do **Painel de Controle**, escolha o ícone de **Programas** e, em seguida, escolha o link **Ativar ou desativar recursos do Windows**.

3. Verifique se a caixa de seleção **.NET Framework 3.5 (inclui o .NET 2.0 e 3.0)** está marcada e, em seguida, escolha o botão **OK**. Não é necessário marcar as caixas de seleção dos nós filho para componentes opcionais do .NET Framework.

   O .NET Framework 3.5 será habilitado, caso ainda não estivesse.

### <a name="to-install-the-f-20-runtime"></a>Para instalar o tempo de execução do F# 2.0

Siga as [etapas para reparar o Visual Studio](../install/repair-visual-studio.md).

## <a name="see-also"></a>Consulte também

- [Guia do F# (.NET Framework)](/dotnet/fsharp/)
- [F# no Visual Studio](fsharp-visual-studio.md)