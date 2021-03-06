---
title: Criar exibições personalizadas de objetos | Microsoft Docs
ms.date: 01/08/2019
ms.topic: conceptual
f1_keywords:
- vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data types, custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 733f3ec7573287e934f8a5f0167db89c0683759a
ms.sourcegitcommit: cd91a8a4f6086cda9ba6948be25864fc7d6b8e44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59537472"
---
# <a name="create-custom-views-of-objects-c-visual-basic-c"></a>Criar exibições personalizadas de objetos (C#, Visual Basic, C++)
Você pode personalizar o modo como o Visual Studio exibe tipos de dados nas janelas variáveis do depurador.

## <a name="native-code"></a>Código nativo

Para C++ código, você pode adicionar expansões de tipo de dados personalizados usando a estrutura do Natvis, conforme descrito em [criar exibições personalizadas de C++ objetos no depurador](/visualstudio/debugger/create-custom-views-of-native-objects). Para C++/código CLI, você também pode usar atributos, aqui descritos neste artigo.

## <a name="attributes"></a>Atributos

No C#, Visual Basic, e C++ (C++código /CLI somente), você pode adicionar expansões para dados personalizados usando <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, e <xref:System.Diagnostics.DebuggerBrowsableAttribute>.

No código do [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], o Visual Basic não dá suporte ao atributo DebuggerBrowsable. Essa restrição é removida em versões mais recentes do .NET Framework.

## <a name="visualizers"></a>Visualizadores

Você pode escrever um visualizador para exibir qualquer tipo de dados gerenciados. Para obter mais informações, confira [Como: Escrever um visualizador](/visualstudio/debugger/create-custom-visualizers-of-data).

## <a name="see-also"></a>Consulte também

- [Instruir o depurador o que mostram como usar o atributo DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)
- [Informar ao depurador o tipo para mostram como usar o atributo DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md)
- [Janelas Inspeção e Inspeção Rápida](../debugger/watch-and-quickwatch-windows.md)
- [Aprimorando a depuração com os atributos de exibição do depurador](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)