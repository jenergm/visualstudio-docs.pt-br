---
title: IDebugCustomAttributeQuery::GetCustomAttributeByName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCustomAttributeQuery::GetCustomAttributeByName
- GetCustomAttributeByName
ms.assetid: 6779727c-d10a-4abe-9acd-d0a1eb0737e7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 60341aa39a61f7179d0b913ec78aca10fae5b84c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56725015"
---
# <a name="idebugcustomattributequerygetcustomattributebyname"></a>IDebugCustomAttributeQuery::GetCustomAttributeByName
Recupera um atributo personalizado, dado seu nome.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT GetCustomAttributeByName(
    LPCOLESTR pszCustomAttributeName,
    BYTE*     ppBlob,
    DWORD*    pdwLen
);
```

```csharp
int GetCustomAttributeByName(
    string    pszCustomAttributeName,
    ref int[] ppBlob,
    out uint  pdwLen
);
```

#### <a name="parameters"></a>Parâmetros
`pszCustomAttributeName`

 [in] Nome do atributo personalizado.

`ppBlob`

[no, out] Matriz de bytes que contém os dados de atributo personalizado.

`pdwLen`

 [out] Comprimento em bytes do `ppBlob` parâmetro.

## <a name="return-value"></a>Valor de retorno
Se for bem-sucedido, retornará `S_OK`. Se o atributo personalizado não existir, retornará `S_FALSE`. Caso contrário, retornará um código de erro.

## <a name="example"></a>Exemplo
O exemplo a seguir mostra como implementar esse método para um **CDebugClassFieldSymbol** objeto que expõe a [IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md) interface.

```cpp
HRESULT CDebugClassFieldSymbol::GetCustomAttributeByName(
    LPCOLESTR pszCustomAttributeName,
    BYTE *pBlob,
    DWORD *pdwLen
)
{
    HRESULT hr = S_FALSE;
    CComPtr<IMetaDataImport> pMetadata;
    mdToken token = mdTokenNil;
    CComPtr<IDebugField> pField;
    CComPtr<IDebugCustomAttributeQuery> pCA;

    ASSERT(IsValidWideStringPtr(pszCustomAttributeName));
    ASSERT(IsValidWritePtr(pdwLen, ULONG*));

    METHOD_ENTRY( CDebugClassFieldSymbol::GetCustomAttributeByName );

    IfFalseGo( pszCustomAttributeName && pdwLen, E_INVALIDARG );

    IfFailGo( m_spSH->GetMetadata( m_spAddress->GetModule(), &pMetadata ) );

    IfFailGo( CDebugCustomAttribute::GetTokenFromAddress( m_spAddress, &token) );
    IfFailGo( CDebugCustomAttribute::GetCustomAttributeByName( pMetadata,
              token,
              pszCustomAttributeName,
              pBlob,
              pdwLen ) );
Error:

    METHOD_EXIT( CDebugClassFieldSymbol::GetCustomAttributeByName, hr );
    return hr;
}
```

## <a name="see-also"></a>Consulte também
- [IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)
