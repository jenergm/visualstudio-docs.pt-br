---
title: Criar modelos de projeto
ms.date: 01/02/2018
ms.topic: conceptual
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- project templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7cd5bd20d5840b560d5954d62e5d158eb1f6c6e6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62430504"
---
# <a name="how-to-create-project-templates"></a>Como: Criar modelos de projeto

Este tópico mostra como criar um modelo usando o **Assistente de Exportação de Modelo**, que empacota o modelo em um arquivo *.zip*.

## <a name="use-the-export-template-wizard"></a>Use o Assistente para Exportar Modelo

1. Criar um projeto.

    > [!NOTE]
    > Use apenas caracteres identificadores válidos para nomear um projeto que será a origem de um modelo. Caso contrário, poderão ocorrer erros de compilação nos projetos criados usando o modelo. Para obter mais informações sobre caracteres identificadores válido, consulte [Nomes de elementos declarados (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names) ou [Identificadores (C++)](/cpp/cpp/identifiers-cpp). Como alternativa, você pode usar [parâmetros de modelo](../ide/template-parameters.md) para usar nomes "seguros" para classes e namespaces.

2. Edite o projeto até que ele esteja pronto para ser exportado como um modelo. Por exemplo, você talvez queira editar arquivos de código para indicar onde a substituição de parâmetro deve ocorrer. Confira [Como: Substituir parâmetros em um modelo](../ide/how-to-substitute-parameters-in-a-template.md).

3. No menu **Projeto**, escolha **Exportar Modelo**.

   O **Assistente para Exportar Modelo** é aberto.

4. Na página **Escolher Tipo de Modelo**, selecione **Modelo de Projeto**. Selecione o projeto que você deseja exportar como um modelo e, em seguida, escolha **Avançar**.

::: moniker range="vs-2017"

5. Na página **Selecionar Opções do Modelo**, insira um nome e uma descrição opcional, um ícone e uma imagem de exibição para o modelo. Esses itens serão exibidos na caixa de diálogo **Novo Projeto**. Escolha **Concluir**.

   O projeto será exportado para um arquivo *.zip* e colocado no local de saída especificado e, se selecionado, importado para o Visual Studio.

Para localizar o modelo na caixa de diálogo **Novo Projeto**, expanda **Instalado** e, em seguida, expanda a categoria que corresponde ao elemento `ProjectType` no arquivo *.vstemplate*. Por exemplo, um arquivo *.vstemplate* que contém `<ProjectType>CSharp</ProjectType>` aparece sob **Instalado** > **Visual C#**, por padrão. Para organizar seu modelo em um subdiretório do tipo de projeto basta criar uma pasta nesse diretório e colocar o arquivo *.zip* do modelo nele. Para obter mais informações, confira [Como: Localizar e organizar modelos](../ide/how-to-locate-and-organize-project-and-item-templates.md).

::: moniker-end

::: moniker range=">=vs-2019"

5. Na página **Selecionar Opções do Modelo**, insira um nome e uma descrição opcional, um ícone e uma imagem de exibição para o modelo. Esses itens serão exibidos na caixa de diálogo em que você cria um projeto. Escolha **Concluir**.

   O projeto será exportado para um arquivo *.zip* e colocado no local de saída especificado e, se selecionado, importado para o Visual Studio.

Para localizar seu modelo na caixa de diálogo em que você cria um projeto, faça uma pesquisa por nome ou percorra a lista. (A filtragem com base na linguagem de programação ou no tipo de projeto não é possível no momento para modelos de usuário.)

::: moniker-end

## <a name="other-ways-to-create-project-templates"></a>Outras maneiras de criar modelos de projeto

Você pode criar modelos de projeto manualmente reunindo os arquivos que constituem o projeto em uma pasta e criando um arquivo XML *.vstemplate* com os metadados apropriados. Para obter mais informações, confira [Como: Criar modelos da Web manualmente](../ide/how-to-manually-create-web-templates.md).

Se o SDK do Visual Studio estiver instalado, você poderá encapsular o modelo concluído em um arquivo VSIX para implantação usando o modelo **Projeto VSIX**. Para obter mais informações, consulte [Introdução ao modelo de projeto do VSIX](../extensibility/getting-started-with-the-vsix-project-template.md).

## <a name="see-also"></a>Consulte também

- [Criar modelos de projeto e de item](../ide/creating-project-and-item-templates.md)
- [Como: Criar modelos de item](../ide/how-to-create-item-templates.md)
- [Introdução ao modelo de projeto do VSIX](../extensibility/getting-started-with-the-vsix-project-template.md)