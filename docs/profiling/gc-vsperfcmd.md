---
title: GC (VSPerfCmd) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 50b2e269ec292aaf37b8d0c707fa27ff8268a1f0
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56596122"
---
# <a name="gc-vsperfcmd"></a>GC (VSPerfCmd)
A opção **GC** habilita a coleta de dados de alocação de memória do.NET Framework e dados de tempo de vida do objeto. A opção **GC** pode ser usada somente com o método de criação de perfil de amostragem e somente com a opção **Inicializar**.

 Quando você estiver usando a opção **GC**, o comando VSPerfClrEnv **/sampleon** não é obrigatório.

 Se nenhum parâmetro for especificado ou se o parâmetro **Alocação** for especificado, apenas os dados de alocação de memória do .NET Framework são coletados. Se o parâmetro **Tempo de Vida** for especificado, os dados de alocação de memória do .NET Framework e de tempo de vida do objeto do .NET Framework são coletados.

## <a name="syntax"></a>Sintaxe

```cmd
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]
```

#### <a name="parameters"></a>Parâmetros
 **Alocação** Padrão. Coleta dados de alocação de memória do .NET Framework.

 **Tempo de Vida** Coleta dados de alocação de memória do .NET Framework e dados de tempo de vida do objeto do .NET Framework.

## <a name="required-options"></a>Opções obrigatórias
 A opção **GC** pode ser usada somente com a opção **Inicializar**.

 **Iniciar:** `AppName` Inicia o aplicativo especificado e inicia a criação de perfil com o método de amostragem.

## <a name="example"></a>Exemplo
 O exemplo a seguir inicia um aplicativo e coleta dados de alocação de memória do .NET Framework.

```cmd
VSPerfCmd.exe /Launch:TestApp.exe /gc
```

## <a name="see-also"></a>Consulte também
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Aplicativos Autônomos de Perfil](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Criar o perfil de aplicativos Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profile services (Serviços de perfil)](../profiling/command-line-profiling-of-services.md)