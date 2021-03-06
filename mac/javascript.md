---
title: JavaScript e TypeScript
description: Informações sobre o suporte para JavaScript no Visual Studio para Mac
author: conceptdev
ms.author: crdun
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 61432695-5B12-4257-B250-48D37EED106D
ms.openlocfilehash: ed84e5478ae7a15905a5555a318bd656c664710e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62982893"
---
# <a name="javascript-and-typescript-support"></a>Suporte a JavaScript e TypeScript

O Visual Studio para Mac dá suporte para JavaScript e TypeScript por meio do IntelliSense, da formatação de código e do realce de sintaxe.

![Suporte para o Editor de TypeScript](https://msdnshared.blob.core.windows.net/media/2018/03/TypeScript-editor.gif)

Para obter mais informações sobre como escrever JavaScript, consulte os guias [Escrevendo código JavaScript](/scripting/javascript/writing-javascript-code).

## <a name="adding-a-javascript-file"></a>Adicionando um arquivo JavaScript

Arquivos JavaScript frequentemente são adicionados a projetos do ASP.NET Core usando a caixa de diálogo **Novo Arquivo**. Para adicionar um arquivo JavaScript, clique com o botão direito do mouse no projeto e vá até **Adicionar > Novo Arquivo**:

![Adicionando novos arquivos ao projeto](media/javascript-image1.png)

Na caixa de diálogo **Novo Arquivo**, selecione **Web > Arquivo JS Vazio ou Web** > **Arquivos TypeScript**. Dê um nome ao arquivo e, em seguida, escolha **Novo**:

![Criando um novo arquivo TypeScript usando o modelo](media/javascript-image2.png)

## <a name="intellisense"></a>IntelliSense

O Visual Studio para Mac usa o [JavaScript Language Service](/visualstudio/ide/javascript-intellisense) para fornecer IntelliSense, permitindo que você tenha conclusão de código inteligente, informações de parâmetro e listas de membros ao escrever código.

O IntelliSense de JavaScript no Visual Studio para Mac pode ser baseado em inferência de tipos, JSDoc ou em declarações de TypeScript.

- **Inferência de tipos** – o tipo de um objeto é presumido com base no contexto do código ao redor. Para obter mais informações, consulte a seção do Visual Studio sobre [IntelliSense baseado na inferência de tipos](/visualstudio/ide/javascript-intellisense#intellisense-based-on-type-inference).
- **JSDoc** – há ocasiões em que a inferência de tipos não fornece as informações de tipo corretas. Nesses casos, as informações de tipo podem ser fornecidas explicitamente pelas anotações de [JSDoc](http://usejsdoc.org/about-getting-started.html). Para obter mais informações, consulte a seção do Visual Studio sobre [IntelliSense baseado no JSDoc](/visualstudio/ide/javascript-intellisense#intellisense-based-on-jsdoc)
- **Arquivos de declaração de TypeScript** – arquivos `.d.ts` são usados para fornecer valores para o IntelliSense de JavaScript. Tipos declarados no arquivo podem ser usados como tipos em comentários de JSDoc. Para obter mais informações, confira a seção do Visual Studio sobre [IntelliSense baseado em arquivos de declaração TypeScript](/visualstudio/ide/javascript-intellisense#intellisense-based-on-typescript-declaration-files)

    ![adicionando um arquivo de definição de typescript](media/javascript-image3.png)

## <a name="see-also"></a>Consulte também

- [IntelliSense de JavaScript (Visual Studio no Windows)](/visualstudio/ide/javascript-intellisense)
