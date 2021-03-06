---
title: IActiveScriptAuthor::AddNamedItem | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.AddNamedItem
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::AddNamedItem
ms.assetid: 951003b6-1c4a-4086-b7ce-2f128e007280
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 95bc529db8129c4e9af1ed9f9dc3d91de9686223
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58145649"
---
# <a name="iactivescriptauthoraddnameditem"></a>IActiveScriptAuthor::AddNamedItem
Adiciona o nome de um item de nível raiz para o namespace do mecanismo de criação de script. Um *item de nível raiz* é um objeto que pode conter propriedades e métodos, e também podem conter uma origem do evento.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT AddNamedItem(  
   LPCOLESTR          pszName,  
   DWORD              dwFlags,  
   IDispatch          *pdisp  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pszName`  
 [in] O nome do item, conforme exibido a partir do script. O nome deve ser exclusiva e persistente.  
  
 `dwFlags`  
 [in] Os sinalizadores que estão associados com o item nomeado. Pode ser uma combinação dos seguintes valores:  
  
|Constante|Valor|Descrição|  
|--------------|-----------|-----------------|  
|SCRIPTITEM_ISVISIBLE|0x00000002|Indica que o nome do item está disponível no namespace do script. Isso permite o acesso a propriedades, métodos e eventos do item.<br /><br /> Por convenção, as propriedades do item incluem membros de filhos do item. Portanto, todas as propriedades do objeto filho e métodos (e seus membros filho, recursivamente) são acessíveis.|  
|SCRIPTITEM_ISSOURCE|0x00000004|Indica os eventos da origem do item que o script pode ter manipuladores de eventos de script.|  
|SCRIPTITEM_GLOBALMEMBERS|0x00000008|Indica que o item é uma coleção de propriedades e métodos que estão associados com o script globais. Seus membros são criados como métodos e variáveis globais.|  
|SCRIPTITEM_ISPERSISTENT|0x00000040|Indica que o item deve ser salvo se o mecanismo de criação de script é salvo.|  
|SCRIPTITEM_CODEONLY|0x00000200|Indica que o item nomeado representa um objeto somente código, e não tem um membro para criar.|  
|SCRIPTITEM_NOCODE|0x00000400|Indica que o item nomeado é apenas um nome que está sendo adicionado e ele não tem nada a criar.|  
  
 `pdisp`  
 [in] O `IDispatch` do `NamedItem` objeto que é usado para coletar os métodos, propriedades ou a origem do evento.  
  
## <a name="return-value"></a>Valor de retorno  
 Um `HRESULT`. Os possíveis valores incluem, mas sem limitação, aqueles na tabela a seguir.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|`S_OK`|O método foi bem-sucedido.|  
  
## <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte também  
 [Interface IActiveScriptAuthor](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::RemoveNamedItem](../../winscript/reference/iactivescriptauthor-removenameditem.md)