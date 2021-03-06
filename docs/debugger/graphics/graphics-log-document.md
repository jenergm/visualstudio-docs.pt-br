---
title: Documento de Log de elementos gráficos | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.graphics.vsglog.error
- vs.graphics.experiment
- vs.graphics.vsglog
ms.assetid: 6ccb1269-d55f-49c4-920d-baedf7de2888
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: aed2acd4dbf921d99bcefe2e74575401fc01c7d7
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60101307"
---
# <a name="graphics-log-document"></a>Documentos de log de gráfico
O documento de Log de gráficos é o registro de eventos de gráficos que ocorreu enquanto o aplicativo foi executado em uma sessão de diagnóstico de gráficos. Após ser gravado, você pode examinar o log no analisador de gráficos do Visual Studio para diagnosticar problemas de desempenho e renderização.

 Este é o que um documento de log gráficos é semelhante no analisador de gráficos:

 ![Um log de gráficos que contém dois quadros capturados. ](media/gfx_diag_demo_graphics_log_orientation.png "gfx_diag_demo_graphics_log_orientation")

## <a name="understanding-graphics-log-documents"></a>Entendendo os documentos de log de gráficos
 Usando o analisador de gráficos para examinar um documento de log de gráficos, você pode visualizar os efeitos de eventos do Direct3D no destino de renderização que ocorreram durante a captura. É possível indicar as áreas exatas do destino de renderização com saídas inesperadas. Ao selecionar um pixel na área afetada, você pode usar os diagnósticos gráficos para inspecioná-la e inspecionar seus sombreadores, os eventos do Direct3D que a afetaram, a pilha de chamadas do aplicativo que resultou nesses eventos e os objetos do DirectX compatíveis com esses eventos. Você pode usar essas informações para diagnosticar problemas de renderização em seu jogo ou aplicativo.

 A parte superior da janela (**Graphics Experiment.vsglog**) exibe a saída do destino de renderização atual do quadro selecionado. A parte inferior exibe uma **Lista de Quadros** com imagens em miniatura dos quadros capturados.

#### <a name="to-inspect-a-frame"></a>Para inspecionar um quadro

- Na **Lista de Quadros**, selecione o quadro que você quer inspecionar. A saída do destino de renderização que aparece na parte superior do documento de log de gráficos é atualizada para exibir o quadro selecionado.

#### <a name="to-inspect-a-pixel"></a>Para inspecionar um pixel

- Na parte superior do documento de log de gráficos, selecione o pixel desejado da saída do destino de renderização. Com um pixel selecionado, você pode usar a janela **Histórico de Pixel de Gráficos** para exibir informações detalhadas sobre o pixel selecionado. Para obter mais informações, consulte [histórico de Pixel](graphics-pixel-history.md).

## <a name="playback-machine"></a>Máquina de reprodução
 No canto superior direito da **Lista de Quadros** fica a **Máquina de Reprodução**. O computador de reprodução é um computador ou dispositivo usado para reproduzir eventos de gráficos de um arquivo de log de gráficos em uma sessão de diagnóstico posterior. Ao usar outro dispositivo para reproduzir eventos capturados no lugar de seu computador de desenvolvimento, você pode reproduzir com mais precisão o ambiente de execução no qual o problema ocorreu. Por exemplo, você pode usar um computador com drivers ou hardwares gráficos que seu computador de desenvolvimento não usa ou outros tipos de dispositivos, como um tablet Windows RT baseado em ARM ou um dispositivo com Windows Phone.

 Para obter informações sobre como especificar um computador de reprodução, consulte [como: Alterar o computador de reprodução de Diagnóstico de Gráficos](how-to-change-the-graphics-diagnostics-playback-machine.md).

## <a name="graphics-log-summary-information"></a>Informações de resumo do log de elementos gráficos
 Quando o arquivo de log de elementos gráficos está ativo, a janela **Propriedades** exibe informações sobre o ambiente que hospedou a sessão de captura do Diagnóstico de Gráficos. Essa janela exibe informações de diversas categorias.

 **Informações do Direct3D** lista informações sobre os recursos de hardware e driver do adaptador de vídeo que foi usado durante a sessão de captura.

|Propriedade|Descrição|
|--------------|-----------------|
|**Formato XR High Color de 10 bits**|**True** se o formato XR High Color de 10 bits tiver suporte; caso contrário, **False**.|
|**DirectCompute CS 4.x**|**True** se Compute Shader 4.0 tiver suporte; caso contrário, **False**.|
|**Sombreadores de precisão dupla**|**True** se a placa de vídeo der suporte a valores de ponto flutuante com precisão dupla (64 bits); caso contrário, **False**.|
|**Listas de comando do driver**|**True** se o driver der suporte às listas de comando; caso contrário, **False**.|
|**Criações concorrentes de driver**|**True** se o driver tiver suporte à criação concorrente (assíncrona); caso contrário, **False**.|
|**Formatos estendidos (BGRA, etc.)**|**True** se formatos estendidos como BGRA tiverem suporte; caso contrário, **False**.|
|**Nível máximo de funcionalidade de hardware**|Exibe o mais alto nível de recursos permitido pela placa de vídeo.|

 **Exibir informações** lista informações sobre o adaptador de vídeo que foi usado durante a sessão de captura.

|Propriedade|Descrição|
|--------------|-----------------|
|**Descrição**|A cadeia de caracteres de descrição da placa de vídeo.|
|**Memória de vídeo**|A quantidade de memória instalada no adaptador gráfico.|
|**Nome do driver**|O nome do driver do adaptador gráfico.|
|**Versão do driver**|A versão do driver do adaptador gráfico.|
|**Nome**|O nome do adaptador gráfico.|

 **Testar arquivo** lista informações sobre o arquivo de teste que está associada com a sessão de captura.

|Propriedade|Descrição|
|--------------|-----------------|
|**Path**|O caminho do arquivo .vsglog. **Observação:**  Essa propriedade não é usada em capturas herdadas.|

 **Informações de módulo** lista o nome e versão das bibliotecas de vínculo dinâmico (DLLs) que foram carregados pelo aplicativo durante a sessão de captura.

 **Informações do sistema** lista informações sobre o hardware e sistema operacional que hospedou o aplicativo durante a sessão de captura.

|Propriedade|Descrição|
|--------------|-----------------|
|**Memória**|A quantidade de memória instalada no computador.|
|**Arquitetura do SO**|A arquitetura da CPU de destino do sistema operacional.|
|**Versão do SO**|A versão do sistema operacional.|
|**Processador**|O processador instalado no computador.|
|**Arquitetura do aplicativo de destino**|A arquitetura da CPU de destino do aplicativo. As informações presentes nesse campo podem ser diferentes das do campo **Arquitetura do SO**.|

 **Aplicativo de destino** lista informações sobre o aplicativo que é o assunto da sessão de captura.

|Propriedade|Descrição|
|--------------|-----------------|
|**Data/hora da última modificação**|A data e hora em que o aplicativo foi compilado.|
|**Path**|O caminho do aplicativo.|
|**ID do Processo**|A ID do processo atribuída ao aplicativo.|
|**Versão**|A versão do aplicativo.|

 **Arquivo de Log VSG** lista informações sobre o documento de log de gráficos.

| Propriedade | Descrição |
|------------------------| - |
| **Criado por** | O nome do aplicativo que criou o documento de log de gráficos. Por exemplo, se a sessão de captura foi iniciada no [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (captura manual), o valor dessa propriedade será [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. |
| **Hora de início da sessão** | A data e hora em que a sessão de captura começou. |
| **Size** | O tamanho do documento de log de gráficos. |

## <a name="see-also"></a>Consulte também
- [Passo a passo: Objetos ausentes devido ao sombreamento de vértice](walkthrough-missing-objects-due-to-vertex-shading.md)
- [Passo a passo: Como depurar erros de renderização devido ao sombreamento](walkthrough-debugging-rendering-errors-due-to-shading.md)