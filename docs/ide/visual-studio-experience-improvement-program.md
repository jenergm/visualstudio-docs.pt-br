---
title: Programa de Aperfeiçoamento da Experiência do Usuário
description: Descubra como gerenciar as configurações de privacidade no Visual Studio.
ms.date: 05/21/2018
ms.topic: conceptual
author: PoulChapman
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a1e4f59b672049ee8148c94dbbf51e560e22c31e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62581990"
---
# <a name="visual-studio-customer-experience-improvement-program"></a>Programa de Aperfeiçoamento da Experiência do Usuário do Visual Studio

O VSCEIP (Programa de Aperfeiçoamento da Experiência do Usuário do Visual Studio) foi projetado para ajudar a Microsoft a aperfeiçoar o Visual Studio ao longo do tempo. Esse programa [coleta informações sobre erros](../ide/diagnostic-data-collection.md), hardware do computador e como as pessoas usam o Visual Studio, sem interromper os usuários em suas tarefas no computador. As informações coletadas ajudam a Microsoft a identificar quais funcionalidades devem ser aprimoradas. Este documento aborda como aceitar ou recusar o VSCEIP.

[!INCLUDE [gdpr-hybrid-note](../misc/includes/gdpr-hybrid-note.md)]

## <a name="opt-in-or-out"></a>Aceitar ou recusar

O VSCEIP está ativado por padrão. Você pode desligá-lo ou ativá-lo novamente seguindo estas instruções:

1. No Visual Studio, escolha **Ajuda** > **Enviar Comentários** e selecione **Configurações**.

   A caixa de diálogo **Programa de Aperfeiçoamento da Experiência do Visual Studio** será aberta.

1. Para recusar, selecione **Não, prefiro não participar** e, em seguida, selecione **OK**. Para aceitar, selecione **Sim, desejo participar** e, em seguida, selecione **OK**.

   ![Caixa de diálogo Programa de Aperfeiçoamento da Experiência do Visual Studio](media/experience-improvement-program.png)

### <a name="registry-settings"></a>Configurações do Registro

Se você instalar as [Ferramentas de Build do Visual Studio](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017), precisará atualizar o Registro para configurar o VSCEIP. Os clientes corporativos podem construir uma política de grupo para aceitar ou recusar sua participação no VSCEIP por meio da definição de uma política baseada em Registro.

A chave do Registro e as configurações relevantes são as seguintes:

::: moniker range="vs-2017"

- Em um sistema operacional de 64 bits, Chave = **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSCommon\15.0\SQM**
- Em um sistema operacional de 32 bits, Chave = **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSCommon\15.0\SQM**
- Quando a Política de Grupo está habilitada, Chave = **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\VisualStudio\SQM**

::: moniker-end

::: moniker range=">=vs-2019"

- Em um sistema operacional de 64 bits, Chave = **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSCommon\16.0\SQM**
- Em um sistema operacional de 32 bits, Chave = **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSCommon\16.0\SQM**
- Quando a Política de Grupo está habilitada, Chave = **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\VisualStudio\SQM**

::: moniker-end

Entrada = **OptIn**

Valor = (DWORD)

- **0** é recusado (desligar o VSCEIP)
- **1** é aceito (ativar o VSCEIP)

> [!CAUTION]
> A edição incorreta do Registro pode causar danos graves ao sistema. Antes de alterar o Registro, faça backup de todos os dados importantes do computador. Use também a opção de inicialização **Última Configuração Válida** caso encontre problemas depois de aplicar as alterações manuais.

Para obter mais informações sobre as informações coletadas, processadas ou transmitidas pelo VSCEIP, confira a [Política de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Consulte também

* [Informações de diagnóstico coletadas pelo Visual Studio](diagnostic-data-collection.md)
* [Fale conosco](../ide/talk-to-us.md)
* [Como relatar um problema com o Visual Studio](../ide/how-to-report-a-problem-with-visual-studio.md)
* [Comunidade de Desenvolvedores do Visual Studio](https://developercommunity.visualstudio.com/)
* [Política de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement)
