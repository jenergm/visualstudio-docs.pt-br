---
title: Função SccHistory | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccHistory
helpviewer_keywords:
- SccHistory function
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2fb579cf56d0fdf9e8c441a1393d934fcc7348d4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58923447"
---
# <a name="scchistory-function"></a>Função SccHistory
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Esta função exibe o histórico dos arquivos especificados.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
SCCRTN SccHistory(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pvContext`  
 [in] A estrutura de contexto de plug-in de controle de origem.  
  
 `hWnd`  
 [in] Um identificador para a janela do IDE que o plug-in de controle de origem pode usar como um pai para todas as caixas de diálogo que ele oferece.  
  
 `nFiles`  
 [in] Número de arquivos especificados no `lpFileName` matriz.  
  
 `lpFileName`  
 [in] Matriz de nomes totalmente qualificados de arquivos.  
  
 `fOptions`  
 [in] Sinalizadores de comando (não usados no momento).  
  
 `pvOptions`  
 [in] Opções de plug-in específico de controle de origem.  
  
## <a name="return-value"></a>Valor de retorno  
 A implementação de plug-in de controle do código-fonte desta função deve retornar um dos seguintes valores:  
  
|Valor|Descrição|  
|-----------|-----------------|  
|SCC_OK|Histórico de versão foi obtido com êxito.|  
|SCC_I_RELOADFILE|O sistema de controle do código-fonte, na verdade, modificou o arquivo em disco ao buscar o histórico (por exemplo, fazendo com que uma versão antiga dele), portanto, o IDE deve recarregar este arquivo.|  
|SCC_E_FILENOTCONTROLLED|O arquivo não está sob controle de origem.|  
|SCC_E_OPNOTSUPPORTED|O sistema de controle do código-fonte não suporta esta operação.|  
|SCC_E_NOTAUTHORIZED|O usuário não tem permissão para executar esta operação.|  
|SCC_E_ACCESSFAILURE|Houve um problema ao acessar o sistema de controle do código-fonte, provavelmente devido a problemas de rede ou de contenção. É recomendável uma nova tentativa.|  
|SCC_E_PROJNOTOPEN|O projeto não tiver sido aberto.|  
|SCC_E_NONSPECIFICERROR|Falha não específica. Não foi possível obter o histórico de arquivos.|  
  
## <a name="remarks"></a>Comentários  
 O plug-in de controle do código-fonte pode exibir sua própria caixa de diálogo para mostrar o histórico de cada arquivo, usando `hWnd` como a janela pai. Como alternativa, o retorno de chamada de saída o texto opcional função fornecida para o [SccOpenProject](../extensibility/sccopenproject-function.md) pode ser usado, se houver suporte.  
  
 Observe que, em determinadas circunstâncias, o arquivo que está sendo examinado pode ser alterados durante a execução desta chamada. Por exemplo, o [!INCLUDE[vsvss](../includes/vsvss-md.md)] comando history dá ao usuário uma chance de obter uma versão antiga do arquivo. Nesse caso, o controle de fonte plug-in retorna `SCC_I_RELOAD` para avisar o IDE que ele precisa recarregar o arquivo.  
  
> [!NOTE]
>  Se o plug-in de controle do código-fonte não dá suporte a essa função para uma matriz de arquivos, somente o histórico de arquivos para o primeiro arquivo pode ser exibido.  
  
## <a name="see-also"></a>Consulte também  
 [Funções de API de plug-in de controle do código-fonte](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)
