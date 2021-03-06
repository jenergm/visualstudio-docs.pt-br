---
title: ProcessOn e ProcessOff | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d3dc6a7e-bc0f-48a6-a4ec-f386348bb296
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ab218f8dabb2b4360c1be17d809399a752f7cc2c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611796"
---
# <a name="processon-and-processoff"></a>ProcessOn e ProcessOff
Os subcomandos VSPerfCmd.exe **ProcessOff** e **ProcessOn** pausam e retomam a criação de perfil para o processo especificado em uma sessão de criação de perfil de linha de comando. **ProcessOff** interrompe o processo de criação de perfil e **ProcessOn** inicia o processo de criação de perfil.

 Na maioria dos casos, você deve especificar **ProcessOn** ou **ProcessOff** como a única opção em um VSPerfCmd.exe linha de comando, mas eles também podem ser combinados com os subcomandos **GlobalOn**, **GlobalOff**, **ThreadOn** e **ThreadOff**.

 Os subcomandos **ProcessOn** e **ProcessOff** subcomandos interagem com o **GlobalOn** e **GlobalOff** subcomandos que controlam a coleta de dados para todos os processos em uma sessão de criação de perfil de linha de comando e os subcomandos **ThreadOn** e **ThreadOff** que controlam a coleta de dados para um thread especificado.

 Os subcomandos **ProcessOff** e **ProcessOn** também afetam a contagem de Thread iniciar/parar é manipulada por funções de API do criador de perfil.

- **ProcessOff** imediatamente define a contagem de iniciar/parar o processo como 0 e, portanto, fará uma pausa de criação de perfil.

- **ProcessOn** imediatamente define a contagem de iniciar/parar o processo para 1 e, portanto, retoma a criação de perfil.

  Confira [APIs de Ferramentas de Criação de Perfil](../profiling/profiling-tools-apis.md) para obter mais informações.

## <a name="syntax"></a>Sintaxe

```cmd
VSPerfCmd.exe /{ProcessOff|ProcessOn}:PID [Options]

```

#### <a name="parameters"></a>Parâmetros
 `PID` O identificador inteiro do processo a ser iniciado ou interrompido. As IDs de processo são listadas na guia **Processo** do Gerenciador de Tarefas do Windows.

## <a name="required-subcommands"></a>Subcomandos necessários
 Nenhum

## <a name="valid-subcommands"></a>Subcomandos válidos
 **ProcessOn** e **ProcessOff** podem ser especificados em linhas de comando que também contêm os subcomandos a seguir.

 **Iniciar:** `Method` Inicializa a sessão de criação de perfil de linha de comando e define o método de criação de perfil especificado.

 **Iniciar:** `AppName` Inicia o aplicativo especificado e inicia a criação de perfil com o método de amostragem.

 **Anexar:** `PID` Inicia a criação de perfil do processo especificado.

 **GlobalOff**&#124;**GlobalOn** Interrompe ou inicia a criação de perfil para todos os processos em uma sessão de criação de perfil de linha de comando.

 {**ThreadOff**&#124;**ThreadOn**}**:**`TID` Interrompe ou inicia a criação de perfil para o thread especificado (somente no método de instrumentação).

## <a name="example"></a>Exemplo
 Neste exemplo, o subcomando **ProcessOff** é usado para coletar dados de criação de inicialização do aplicativo.

```cmd
; Initialize the profiler.
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp
; Start the instrumented application.
; Stop profiling the process after startup.
VSPerfCmd.exe /ProcessOff:12345
; Shut down the target application.
; Close the profiler.
VSPerfCmd /Shutdown

```

## <a name="see-also"></a>Consulte também
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Aplicativos Autônomos de Perfil](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Criar o perfil de aplicativos Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profile services (Serviços de perfil)](../profiling/command-line-profiling-of-services.md)