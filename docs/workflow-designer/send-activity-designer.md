---
title: Designer de fluxo de trabalho - Designer de atividade de envio
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Send.UI
ms.assetid: b514f2e4-767c-4b94-ac61-dd3a54d4b96d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8d27bd9be1b769215dd77d1e906a5698e17bd18b
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59659923"
---
# <a name="send-activity-designer"></a>Enviar o designer de atividades

O **envie** designer de atividade é usado para criar e configurar um <xref:System.ServiceModel.Activities.Send> atividade.

## <a name="the-send-activity"></a>Atividade de enviar

 Uma atividade de <xref:System.ServiceModel.Activities.Send> é usada para enviar uma mensagem a um serviço. Uma atividade de <xref:System.ServiceModel.Activities.ReceiveReply> pode ser associada a uma atividade de <xref:System.ServiceModel.Activities.Send> que receberá uma mensagem como parte de um padrão de troca de solicitação/resposta de mensagem no cliente.

### <a name="using-the-send-activity-designer"></a>Usando o designer de atividade de enviar

Acesso a **envie** designer de atividade na **Messaging** categoria da **caixa de ferramentas**. O **envie** designer de atividade pode ser arrastado da **caixa de ferramentas** e ignorados sobre a superfície do Designer de fluxo de trabalho onde quer que as atividades são colocadas em geral. Isso cria uma atividade de <xref:System.ServiceModel.Activities.Send> com uma opção <xref:System.Activities.Activity.DisplayName%2A> de enviar. O <xref:System.Activities.Activity.DisplayName%2A> pode ser editado no cabeçalho do **enviar** designer de atividade ou nos **DisplayName** caixa da grade de propriedade.

Para criar uma <xref:System.ServiceModel.Activities.ReceiveReply> atividade e associá-lo ao selecionado <xref:System.ServiceModel.Activities.Send> atividade, com o botão direito o **enviar** clique de designer, atividade de **crie ReceiveReply** item no menu de contexto e o **ReceiveReplyForSend** designer aparece abaixo de **enviar** designer. A atividade de <xref:System.ServiceModel.Activities.ReceiveReply> é uma atividade que receberá uma mensagem como parte de um padrão de troca de solicitação/resposta de mensagem no cliente. Ele pode ser configurado com o **ReceiveReplyForSend** designer.

Como alternativa, o **SendAndReceiveReply** designer de modelo na **Messaging** categoria dos **caixa de ferramentas** pode ser usado para criar um par de pré-compilação configurado <xref:System.ServiceModel.Activities.Send>e <xref:System.ServiceModel.Activities.ReceiveReply> atividades. Para obter mais informações sobre o uso do **SendAndReceiveReply** e **ReceiveReplyForSend** modelos, consulte a [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) tópico.

### <a name="the-send-activity-properties"></a>As propriedades de atividade de enviar

A tabela a seguir mostra as propriedades de <xref:System.ServiceModel.Activities.Send> e descreve como elas são usadas no designer. Essas propriedades podem ser editadas na grade de propriedades ou na superfície do Designer de fluxo de trabalho.

| Nome da Propriedade | Necessária | Uso |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | False | O nome amigável de atividade de <xref:System.ServiceModel.Activities.Send> . O padrão é enviar. Embora não seja necessário <xref:System.Activities.Activity.DisplayName%2A> restrita, é uma prática recomendada usar um. |
| <xref:System.ServiceModel.Activities.Send.OperationName%2A> | verdadeiro | O nome da operação de serviço chamada por esta atividade de <xref:System.ServiceModel.Activities.Send> . Essa propriedade é usada para construir o valor padrão para o **ação** propriedade se o **ação** propriedade não está definida explicitamente. |
| <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> | verdadeiro | O nome do contrato de serviço que o serviço ser chamado implementa. |
| <xref:System.ServiceModel.Activities.Send.Content%2A> | False | Especifica o conteúdo de mensagem ou de parâmetro para receber. Pode ser uma atividade de <xref:System.ServiceModel.Activities.ReceiveMessageContent> ou uma atividade de <xref:System.ServiceModel.Activities.ReceiveParametersContent> . Editar essa propriedade, selecionando o botão de reticências ao lado de **conteúdo** campo na grade de propriedade ou clicando o **definir...**  botão ao lado de **conteúdo** rótulos no **Receive** superfície do designer de atividade. Ambos exibe a **definição de conteúdo** caixa de diálogo. Para obter mais informações sobre como usar essa caixa, consulte o [caixa de diálogo de definição de conteúdo](../workflow-designer/content-definition-dialog-box.md) tópico. |
| <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> | False | Especifica <xref:System.ServiceModel.Activities.CorrelationHandle> usado para rotear a mensagem à instância apropriado de fluxo de trabalho.<br /><br /> Clique no botão de reticências ao lado de <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> propriedade na grade de propriedades para abrir o **Editor de expressão** caixa de diálogo. Para obter mais informações sobre o uso desta caixa de diálogo, consulte o [como: Use o Editor de expressão](../workflow-designer/how-to-use-the-expression-editor.md) tópico. |
| <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> | False | Especifica a coleção de objetos de <xref:System.ServiceModel.Activities.CorrelationInitializer> que inicializam vários objetos de <xref:System.ServiceModel.Activities.CorrelationHandle> que configuram esta atividade de <xref:System.ServiceModel.Activities.Send> dentro de fluxo de trabalho. Clique no botão de reticências ao lado de <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> propriedade na grade de propriedades para abrir o **adicionar inicializadores de correlação** caixa de diálogo. Para obter mais informações sobre como usar essa caixa, consulte o [caixa de diálogo Adicionar CorrelationInitializers](../workflow-designer/add-correlationinitializers-dialog-box.md) tópico. |
| <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> | False | Uma coleção de tipos conhecidos para que a operação de serviço é chamada por esta atividade de <xref:System.ServiceModel.Activities.Send> . Esta propriedade deve ser usada em conjunto com a propriedade de <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> definida como <xref:System.Runtime.Serialization.DataContractSerializer>. É ignorada se <xref:System.Xml.Serialization.XmlSerializer> é usado.<br /><br /> Selecione o botão de reticências ao lado de **KnownTypes** campo na grade de propriedade para exibir o **Editor de coleção do tipo** caixa de diálogo com a qual você pode adicionar tipos relevantes.<br /><br /> Selecione o botão de reticências ao lado de **KnownTypes** campo na grade de propriedade para exibir o **Editor de coleção do tipo** caixa de diálogo com a qual você pode adicionar tipos relevantes. Para obter mais informações sobre como usar essa caixa, consulte o [caixa de diálogo do Editor de coleção de tipo](../workflow-designer/type-collection-editor-dialog-box.md) tópico. |
| <xref:System.ServiceModel.Activities.Send.ProtectionLevel%2A> | verdadeiro | Especifica <xref:System.Net.Security.ProtectionLevel> para a mensagem.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> significa somente autenticação.<br />2. <xref:System.Net.Security.ProtectionLevel> significa assinar dados para ajudar a garantir a integridade dos dados transmitidos.<br />3. <xref:System.Net.Security.ProtectionLevel> significa criptografar e assinar dados para ajudar a garantir a confidencialidade e integridade dos dados transmitidos. |
| <xref:System.ServiceModel.Activities.Send.SerializerOption%2A> | verdadeiro | O serializador usar para que a operação de serviço é chamada pela atividade de <xref:System.ServiceModel.Activities.Send> . O valor padrão é <xref:System.Runtime.Serialization.DataContractSerializer>, que serializa e desserializa uma instância de um tipo em um fluxo XML ou em um documento usando um contrato fornecido de dados. |
| <xref:System.ServiceModel.Activities.Send.Action%2A> | False | Especifica o cabeçalho da ação de mensagem. Se ele não for definido explicitamente, seu valor padrão é: https://tempuri.org/{service de contrato de namespace} / {nome do contrato de serviço} / {nome da operação}. Se especificado em uma atividade de <xref:System.ServiceModel.Activities.Send> , a atividade de <xref:System.ServiceModel.Activities.Receive> que recebe a mensagem deve ter o mesmo valor para que a mensagem é entregada corretamente. |
| <xref:System.ServiceModel.Activities.Send.TokenImpersonationLevel%2A> | | <xref:System.Security.Principal.TokenImpersonationLevel> permitido o receptor de mensagem. Ele define os níveis de representação de segurança, que controla o grau ao qual um processo do servidor pode agir em nome de um processo do cliente.<xref:System.Security.Principal.TokenImpersonationLevel> indica que um nível de representação não está atribuído. <xref:System.Security.Principal.TokenImpersonationLevel> indica que o processo do servidor não pode obter informações de identificação sobre o cliente e não pode representar o cliente. <xref:System.Security.Principal.TokenImpersonationLevel> indica que o processo do servidor pode obter informações sobre o cliente, como identificadores de segurança e privilégios, mas que não pode representar o cliente. Isso é útil para servidores que exportam seus próprios objetos, por exemplo, os produtos de base de dados que exporte tabelas e modos de exibição. Usando informações recuperadas de cliente segurança, o servidor pode tomar decisões de acesso de validação não poderá usar outros serviços usando o contexto de segurança do cliente. <xref:System.Security.Principal.TokenImpersonationLevel> indica que o processo do servidor pode representar o contexto de segurança de cliente no seu sistema local. O servidor não pode representar o cliente em sistemas remotos. <xref:System.Security.Principal.TokenImpersonationLevel> indica que o processo do servidor pode representar o contexto de segurança de cliente em sistemas remotos. |
| <xref:System.ServiceModel.Activities.Send.Endpoint%2A> | | <xref:System.ServiceModel.Endpoint> que a atividade de <xref:System.ServiceModel.Activities.Send> envia à mensagem. Se essa propriedade é definida a <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> propriedade deve ser **nulo**. |
| <xref:System.ServiceModel.Activities.Send.EndpointAddress%2A> | | <xref:System.ServiceModel.EndpointAddress> que a mensagem é enviada. |
| <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> | | O nome da configuração de ponto de extremidade. Essa propriedade é definida quando você estiver configurando um ponto de extremidade em um arquivo de configuração. Essa propriedade deve ser definida para o nome fornecido  **\<ponto de extremidade >** elemento no arquivo de configuração. Se essa propriedade for definida, o <xref:System.ServiceModel.Activities.Send.Endpoint%2A> propriedade deve ser **nulo**. |

## <a name="see-also"></a>Consulte também

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Receber](../workflow-designer/receive-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)