---
title: Funções de retorno de chamada implementadas pelo IDE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, callback functions
- callback functions, source control plug-ins
ms.assetid: 4a8833f0-6ac0-4ea7-9400-8275aa991468
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fc3b4423b54975c773de743b093f882f1fd9c42c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56697553"
---
# <a name="callback-functions-implemented-by-the-ide"></a>Funções de retorno de chamada implementadas pelo IDE
Para fazer a integração com o ambiente de desenvolvimento integrado (IDE) como perfeita possível e para fornecer uma experiência unificada do usuário final, o plug-in de controle de origem pode usar funções de retorno de chamada que são implementadas pelo IDE. O plug-in pode chamar essas funções em momentos apropriados durante uma operação de controle do código-fonte para passar informações para o IDE; o IDE pode exibir essas informações como os elementos incorporados na sua interface do usuário nativa. O usuário tem uma experiência menos fragmentada neste cenário que se o plug-in empregados sua própria interface do usuário.

 É o arquivo de cabeçalho necessários *scc.h*. O local padrão é *\Program Files\VSIP 8.0\EnvSDK\common\inc\\*. Ele também está na pasta VSIP que tem o exemplo de plug-in de controle do código-fonte em *\Program Files\VSIP 8.0\MSSCCI\\*.

## <a name="in-this-section"></a>Nesta seção
- [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) descreve a função de retorno de chamada que é usada pelo [SccOpenProject](../extensibility/sccopenproject-function.md) para exibir mensagens de controle de fonte de plug-in por meio do IDE.

- [POPLISTFUNC](../extensibility/poplistfunc.md) descreve a função de retorno de chamada que é usada pelo [SccPopulateList](../extensibility/sccpopulatelist-function.md) quando o IDE não tem acesso completo a informações que estão disponíveis somente para o plug-in, como uma lista completa de controle de origem arquivos sob controle de versão.

- [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md) descreve a função de retorno de chamada que é usada pelas [SccQueryChanges](../extensibility/sccquerychanges-function.md) operação.

- [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md) descreve a função de retorno de chamada que é usada pelas [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) operação.

- [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) descreve a função de retorno de chamada definida por uma chamada para o [SccSetOption](../extensibility/sccsetoption-function.md) que permite que o plug-in para se comunicar alterações de nome de volta para o IDE de controle de origem.

## <a name="related-sections"></a>Seções relacionadas
- [SccOpenProject](../extensibility/sccopenproject-function.md) abre um projeto.

- [SccPopulateList](../extensibility/sccpopulatelist-function.md) examina a lista de arquivos para seu status atual. Além disso, usa o `pfnPopulate` função para notificar o chamador quando um arquivo não coincide com os critérios para o `nCommand`.

- [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) examina uma lista de diretórios e arquivos em um projeto ou projetos que estão sob controle do código-fonte. Cada nome de arquivo e diretório encontrado é passado para uma função de retorno de chamada.

- [SccQueryChanges](../extensibility/sccquerychanges-function.md) examina as alterações de nome que foram feitas em uma lista de arquivos. Cada nome de arquivo é passado para uma função de retorno de chamada juntamente com seu status de alteração.

- [SccSetOption](../extensibility/sccsetoption-function.md) define uma ampla variedade de opções. Cada opção começa com `SCC_OPT_xxx` e tem seu próprio conjunto definido de valores.

- [Plug-ins de controle de origem](../extensibility/source-control-plug-ins.md) descreve o conteúdo da seção de referência do SDK do plug-in de controle de origem.