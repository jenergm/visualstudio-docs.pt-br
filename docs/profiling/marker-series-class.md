---
title: Classe marker_series | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series
helpviewer_keywords:
- Concurrency::diagnostic::marker_series class
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 155d47f6764e754a1093cbcf884368c80d709a2a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62575911"
---
# <a name="markerseries-class"></a>Classe marker_series
Representa um canal serial de eventos gerados por um único provedor.

## <a name="syntax"></a>Sintaxe

```cpp
class marker_series;
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores públicos

|Nome|Descrição|
|----------|-----------------|
|[Construtor marker_series::marker_series](../profiling/marker-series-marker-series-constructor.md)|Inicializa uma nova instância da classe `marker_series`.|
|[Destruidor marker_series::~marker_series](../profiling/marker-series-tilde-marker-series-destructor.md)|Destrói o objeto marker_series e libera todos os recursos alocados.|

### <a name="public-methods"></a>Métodos públicos

|Nome|Descrição|
|----------|-----------------|
|[Método marker_series::is_enabled](../profiling/marker-series-is-enabled-method.md)|Determina se alguma sessão habilitou o provedor.|
|[Método marker_series::write_alert](../profiling/marker-series-write-alert-method.md)|Grava um alerta para o arquivo de rastreamento da Visualização Simultânea.|
|[Método marker_series::write_flag](../profiling/marker-series-write-flag-method.md)|Grava um sinalizador para o arquivo de rastreamento da Visualização Simultânea.|
|[Método marker_series::write_message](../profiling/marker-series-write-message-method.md)|Grava uma mensagem para o arquivo de rastreamento da Visualização Simultânea.|

## <a name="inheritance-hierarchy"></a>Hierarquia de herança
 `marker_series`

## <a name="requirements"></a>Requisitos
 **Cabeçalho:** *cvmarkersobj.h*

 **Namespace:** Concurrency::diagnostic

## <a name="see-also"></a>Consulte também
- [namespace de diagnóstico](../profiling/diagnostic-namespace.md)