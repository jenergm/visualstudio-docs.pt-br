---
title: 'Como: Impor um código com uma política de Check-in do análise código | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 27593a450f7c2a1b34c1c84bc1d4e7ea5bb5919f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60091870"
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>Como: Impor um código de fácil manutenção com uma política de check-in de análise de código
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Os desenvolvedores podem usar a ferramenta de avaliação de código para medir a complexidade e facilidade de manutenção de seu código, mas eles não é possível invocar as métricas de código como parte de uma política de check-in. No entanto, uma equipe pode habilitar as regras de análise de código que verificam a conformidade de seus códigos com os padrões de métricas de código e impõem as regras por meio de políticas de check-in. Para obter mais informações sobre as métricas de código, consulte o [valores de métricas de código](../code-quality/code-metrics-values.md).  
  
 Os desenvolvedores podem habilitar a profundidade de herança, acoplamento de classe, o índice de facilidade de manutenção e regras de complexidade para impor um código por meio de políticas de check-in da análise de código. Todos os quatro dessas regras são encontrados na categoria "Regras de facilidade de manutenção" no editor de política de análise de código.  
  
 Os administradores de versão de controle para [!INCLUDE[esprfound](../includes/esprfound-md.md)] pode adicionar as regras de facilidade de manutenção de análise de código para os requisitos de política de check-in. Eles check-in políticas exigem que os desenvolvedores executar a análise de código de acordo com essas alterações de regra antes de iniciar um check-in.  
  
### <a name="to-open-the-code-analysis-policy-editor"></a>Para abrir o Editor de política de análise de código  
  
1. Na **Team Explorer**, clique com botão direito do projeto de equipe, clique em **configurações de projeto de equipe**e, em seguida, clique em **controle de origem**.  
  
     O **controle de origem** caixa de diálogo é exibida.  
  
2. Sobre o **política de Check-in** guia e, em seguida, clique em **Add**.  
  
     O **adicionar política de Check-in** caixa de diálogo é exibida.  
  
3. No **política de Check-in** lista, selecione o **análise de código** caixa de seleção e, em seguida, clique em **Okey**.  
  
     O **Editor de política de análise de código** caixa de diálogo é exibida.  
  
### <a name="to-enable-code-analysis-maintainability-rules"></a>Para habilitar regras de facilidade de manutenção de análise de código  
  
1. No **Editor de política de análise de código** caixa de diálogo **configurações de regra**, expanda o **regras de facilidade de manutenção** nó.  
  
2. Marque as caixas de seleção para as seguintes regras:  
  
    - Profundidade de herança: **CA1501 AvoidExcessiveInheritance** -limite: Aviso em mais de 5 níveis de profundidade  
  
    - Complexidade: **CA1502 AvoidExcessiveComplexity** -limite: Aviso em mais de 25  
  
    - Índice de facilidade de manutenção: **CA1505 AvoidUnmaintainableCode** -limite: Aviso em menos de 20  
  
    - Acoplamento de classes: **CA1506 AvoidExcessiveClassCoupling** -limite: Aviso em mais de 80 para uma classe e mais de 30 para um método  
  
    - Além disso, se você quiser uma violação de regra para impedir que uma compilação, selecione a **tratar aviso como um erro** caixa de seleção ao lado da descrição da regra.  
  
3. Clique em **OK**. A nova política de check-in agora se aplica ao check-ins futuras.  
  
## <a name="see-also"></a>Consulte também  
 [Valores de métricas de código](../code-quality/code-metrics-values.md)   
 [Criando e usando políticas de check-in de análise de código](../code-quality/creating-and-using-code-analysis-check-in-policies.md)
