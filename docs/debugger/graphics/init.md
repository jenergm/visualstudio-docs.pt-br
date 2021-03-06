---
title: Init | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c55ddec8-9101-4673-979b-4109caca9146
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7a2bd17b91f7a18adce1153634cb9fc55902720b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680900"
---
# <a name="init"></a>Init
Prepara o componente no aplicativo de diagnóstico de gráficos para capturar e registrar informações de gráficos em um arquivo de log de gráficos ativamente.

## <a name="syntax"></a>Sintaxe

```C++
void Init(
  std::function<void (int len, wchar_t * pszBuffer)> vsgLogGetter
);
```

#### <a name="parameters"></a>Parâmetros
 `vsgLogGetter` Uma entidade que pode ser chamada — como uma função, ponteiro de função, lambda ou objeto de função — que usa como parâmetros o comprimento de um buffer composto `wchar_t` e um ponteiro para esse buffer e retorna `void`. Quando invocada, a entidade que pode ser chamada determina o nome do arquivo que será usado para registrar informações de gráficos e grava-o buffer especificado antes de retornar.

## <a name="remarks"></a>Comentários
 O `Init` função é chamada automaticamente quando uma instância das `VsgDbg` classe for construída, especificando o `bDefaultInit` parâmetro de seu construtor como `true`; caso contrário, `Init` deve ser chamado explicitamente antes de você pode capturar ativamente e registre informações de gráficos.

 Você pode finalizar a fechar os elementos gráficos ativos arquivo de log e chamando `UnInit`e, em seguida, capturar e registrar informações de gráficos mais para um novo arquivo de log de elementos gráficos chamando `Init` novamente. Você pode repetir isso quantas vezes você deseja criar gráficos independentes de vários arquivos de log usando o mesmo `VsgDbg` instância.

## <a name="see-also"></a>Consulte também
- [UnInit](init.md)