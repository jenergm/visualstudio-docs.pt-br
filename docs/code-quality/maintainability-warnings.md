---
title: Avisos de facilidade de manutenção
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7d5508e203b8ed5087f456c715c492d8f1ca7c86
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55943448"
---
# <a name="maintainability-warnings"></a>Avisos de facilidade de manutenção

Avisos de facilidade de manutenção suporte à manutenção de biblioteca e o aplicativo.

## <a name="in-this-section"></a>Nesta seção

| Regra | Descrição |
|-----------|-----------------------------------|
| [CA1500: Nomes de variáveis não devem corresponder aos nomes de campo](../code-quality/ca1500-variable-names-should-not-match-field-names.md) | Um método de instância declara um parâmetro ou uma variável local cujo nome corresponde a um campo de instância do tipo declarativo, que leva a erros. |
| [CA1501: Evitar herança excessiva](../code-quality/ca1501-avoid-excessive-inheritance.md) | Um tipo está mais de quatro níveis abaixo na hierarquia de herança. As hierarquias de tipo profundamente aninhado podem ser difíceis de seguir, compreender e manter. |
| [CA1502: Evitar complexidade excessiva](../code-quality/ca1502-avoid-excessive-complexity.md) | Esta regra mede o número de caminhos linearmente independentes por meio do método, o que é determinado pelo número e pela complexidade das ramificações condicionais. |
| [CA1504: Examine os nomes de campo](../code-quality/ca1504-review-misleading-field-names.md) | O nome de um campo de instância começa com "s _", ou o nome de um estático (compartilhado no [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) campo começa com "m _". |
| [CA1505: Evitar código que](../code-quality/ca1505-avoid-unmaintainable-code.md) | Um tipo ou um método tem um baixo valor de índice de facilidade de manutenção. Um baixo índice de facilidade de manutenção indica que um tipo ou um método é provavelmente difícil de manter e seria um bom candidato para um novo design. |
| [CA1506: Evite acoplamento de classes excessivo](../code-quality/ca1506-avoid-excessive-class-coupling.md) | Esta regra mede o acoplamento de classes contando o número de referências de tipo exclusivas que um tipo ou um método contém. |

## <a name="see-also"></a>Consulte também

- [Medindo complexidade e facilidade de manutenção do código gerenciado](../code-quality/code-metrics-values.md)