---
title: Erros do Designer de Classe
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.classdesigner.CPlusPlusViewInDiagramNoTypeFound
- vs.classdesigner.CPlusPlusNoTypeFound
- vs.classdesigner.CannotShowBaseType
- vs.classdesigner.MatchOrphanTypesAtLoad
- vs.classdesigner.CannotShowType
- vs.classdesigner.AssociationTypeNotFoundError
- vs.classdesigner.ViewInDiagramNoTypesFound
- vs.classdesigner.CannotImplementInterface
- vs.classdesigner.CannotShowImplementedInterface
- vs.classdesigner.ViewInDiagramUnparsableTypeFound
- vs.classdesigner.AssociationTypeNotFound
- vs.classdesigner.CPlusPlusTypeCannotBeAdded
helpviewer_keywords:
- errors, class diagrams
- errors, Class Designer
- error messages, Class Designer
- error messages, class diagrams
- Class Designer [Visual Studio], errors
- class diagrams, errors
ms.assetid: 79d70e70-704c-4255-ab68-c10d6949470e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: aadc0cfb66226f463ff8a2049d4dbf81e7bcf62b
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55957098"
---
# <a name="class-designer-errors"></a>Erros do Designer de Classe

O **Designer de Classe** não controla o local dos arquivos de origem, portanto, modificar a estrutura do projeto ou mover os arquivos de origem no projeto pode fazer com que o **Designer de Classe** perca o controle do tipo, Por exemplo, é comum modificar o tipo de origem de um typedef, de classes base ou de tipos de associação. É possível receber um erro como **O Designer de Classe não pode exibir este tipo**. Para resolver o erro, arraste o código-fonte modificado ou realocado para o diagrama de classe novamente para exibi-lo.

## <a name="resources"></a>Recursos

Você pode obter ajuda com outros erros e avisos nos seguintes recursos:

- [Trabalhar com o código do Visual C++](working-with-visual-cpp-code.md) inclui informações de solução de problemas de como exibir C++ em um diagrama de classe.
- O [Fórum do Designer de Classe do Visual Studio](http://go.microsoft.com/fwlink/?LinkId=160754) fornece um fórum para perguntas sobre o **Designer de Classe**.

## <a name="see-also"></a>Consulte também

- [Projetar e exibir classes e tipos](designing-and-viewing-classes-and-types.md)
