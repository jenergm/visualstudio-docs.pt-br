---
title: 'Como: Criar um documento XML baseado em um esquema XSD'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d4ba0106a1494c7e7e8d56c3e902a3436f657712
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60115348"
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Como: Criar um documento XML baseado em um esquema XSD

O **gerar XML de exemplo** recurso gera um arquivo XML de exemplo com base em seu arquivo de esquema XML (XSD).

 Você pode usar esta opção para os seguintes situações:

- Para entender o uso de várias construções no seu esquema.

- Para confirmar que o esquema faz o que é esperado dele.

O **gerar XML de exemplo** recurso só está disponível nos elementos globais e requer um conjunto de esquema XML válido.

Esse recurso normalmente gera documentos XML válidos. No entanto, se o esquema contiver um ou mais dos seguintes, o exemplo poderá não ser válido:

- As restrições de identidade `xs:key`, `xs:keyref` e `xs:unique`.

- `xs:pattern` facetas.

- Enumerações do tipo `xs:QName`.

- Tipos `xs:ENTITY`, `xs:ENTITIES` e `xs:NOTATION`.

Além disso, observe que o conteúdo de `xs:base64Binary` será gerado apenas se as enumerações ocorrerem no esquema para esse tipo.

## <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>Para gerar um documento de instância XML baseado no arquivo XSD

1. Siga as etapas em [como: Criar e editar um arquivo de esquema XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).

2. No [XML Schema Explorer](../xml-tools/xml-schema-explorer.md), clique com botão direito do `PurchaseOrder` elemento global. Selecione **gerar XML de exemplo**.

     Quando você seleciona essa opção, PurchaseOrder. *xml* arquivo com o conteúdo XML de exemplo a seguir será gerado e aberto no editor de XML:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <PurchaseOrder OrderDate="1900-01-01" xmlns="http://tempuri.org/PurchaseOrderSchema.xsd">
      <ShipTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </ShipTo>
      <ShipTo country="US">
        <name>name2</name>
        <street>street2</street>
        <city>city2</city>
        <state>state2</state>
        <zip>-79228162514264337593543950335</zip>
      </ShipTo>
      <BillTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </BillTo>
    </PurchaseOrder>
    ```