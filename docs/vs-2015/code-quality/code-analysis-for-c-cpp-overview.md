---
title: Visão geral da análise de código C/C++ | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: overview
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: jillfra
ms.openlocfilehash: bc84b3f89aa819755a689a0798aea7fbb8147510
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805622"
---
# <a name="code-analysis-for-cc-overview"></a>Análise de código para visão geral do C/C++
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A ferramenta de análise de código C/C++ fornece informações aos desenvolvedores sobre possíveis defeitos no código-fonte C/C++. Erros de codificação comuns relatados pela ferramenta incluem estouros de buffer, memória não inicializada, desreferências de ponteiro nulo e perdas de memória e de recursos.  
  
## <a name="ide-integrated-development-environment-integration"></a>Integração ao IDE (ambiente de desenvolvimento integrado)  
 Para que os desenvolvedores usem a ferramenta de análise de uma forma natural, ela é totalmente integrada ao IDE do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Durante o processo de build, todos os avisos gerados para o código-fonte aparecem na Lista de Erros. Você pode navegar para o código-fonte que causou o aviso e ver informações adicionais sobre a causa e possíveis soluções do problema.  
  
## <a name="pragma-support"></a>Suporte para #pragma  
 Os desenvolvedores podem usar a diretiva `#pragma` para tratar avisos como erros, habilitar ou desabilitar avisos e suprimir avisos de linhas individuais do código. Para obter mais informações, confira [Como: Habilitar e desabilitar análise de código para avisos do C/C++ específicos](http://msdn.microsoft.com/910b8518-71f1-4b2e-b012-70647795642a).  
  
## <a name="annotation-support"></a>Suporte para anotação  
 As anotações melhoram a precisão da análise de código. As anotações fornecem informações adicionais sobre pré e pós-condições nos parâmetros de função e nos tipos retornados. Para obter mais informações, confira [Como: especificar informações de código adicionais usando __analysis_assume](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)  
  
## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>Execute a ferramenta de análise como parte da política de check-in  
 Talvez você queira exigir que todos os check-ins do código-fonte satisfaçam determinadas políticas. Em particular, convém verificar se a análise foi executada como uma etapa do build local mais recente. Para obter mais informações de como habilitar uma política de check-in de análise de código, confira [Criando e usando políticas de check-in de análise de código](../code-quality/creating-and-using-code-analysis-check-in-policies.md)  
  
## <a name="team-build-integration"></a>Integração ao Team Build  
 Você pode usar os recursos integrados do sistema de build para executar a ferramenta de análise de código como uma etapa do processo de build do [!INCLUDE[esprtfs](../includes/esprtfs-md.md)]. Para obter mais informações, consulte [Compilar o aplicativo](http://msdn.microsoft.com/library/a971b0f9-7c28-479d-a37b-8fd7e27ef692).  
  
## <a name="command-line-support"></a>Suporte para linha de comando  
 Além da integração completa com o ambiente de desenvolvimento, os desenvolvedores também podem usar a ferramenta de análise por meio da linha de comando, conforme é mostrado no exemplo a seguir:  
  
 `C:\>cl /analyze Sample.cpp`
