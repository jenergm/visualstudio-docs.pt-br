---
title: Habilitando recursos de depuração no Visual C++ (-D_DEBUG) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /D_DEBUG compiler option [C++]
- debugging [C++], enabling debug features
- debugging [MFC], enabling debug features
- assertions, enabling debug features
- D_DEBUG compiler option
- MFC libraries, debug version
- debug builds, MFC
- _DEBUG macro
ms.assetid: 276e2254-7274-435e-ba4d-67fcef4f33bc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 295bdc7b220f8977c85dd1b359f99af2f8d5d72a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56682460"
---
# <a name="enabling-debug-features-in-visual-c-ddebug"></a>Habilitando funcionalidades de depuração no Visual C++ (/D_DEBUG)
No [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], os recursos de depuração como asserções são habilitados quando você compila seu programa com o símbolo **_DEBUG** definido. Há duas maneiras de definir **_DEBUG**:

- Especifique **#define _DEBUG** no código-fonte ou

- Especifique a opção do compilador **/D_DEBUG**. (Se você criar seu projeto no Visual Studio usando assistentes, **/D_DEBUG** será definido automaticamente na configuração Depuração).

  Quando **_DEBUG** é definido, o compilador compila as seções de código cercadas por **#ifdef _DEBUG** e por `#endif`.

  A configuração Depuração de um programa MFC deve ser vinculada a uma versão de depuração da biblioteca MFC. Os arquivos de cabeçalho MFC determinam a versão correta da biblioteca MFC à qual vincular com base nos símbolos definidos, como **_DEBUG** e **_UNICODE**. Para obter detalhes, confira [Versões da biblioteca MFC](/cpp/mfc/mfc-library-versions).

## <a name="see-also"></a>Consulte também
- [Depurando código nativo](../debugger/debugging-native-code.md)
- [Configurações do projeto para uma configuração de depuração de C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)