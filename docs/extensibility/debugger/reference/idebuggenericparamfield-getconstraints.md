---
title: IDebugGenericParamField::GetConstraints | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugGenericParamField::GetConstraints
- GetConstraints
ms.assetid: 86a78b5a-ee0f-4999-a0ba-919d3dc7d969
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5101aceb0c187996d601d9a3c3adbd746df9ad09
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31111649"
---
# <a name="idebuggenericparamfieldgetconstraints"></a>IDebugGenericParamField::GetConstraints
Pobiera ograniczenia, które są skojarzone z tym parametru ogólnego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetConstraints(  
   ULONG32       cConstraints,  
   IDebugField** ppConstraints,  
   ULONG32*      pcConstraints  
);  
```  
  
```csharp  
int GetConstraints(  
   uint              cConstraints,  
   out IDebugField[] ppConstraints,  
   ref uint          pcConstraints  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cConstraints`  
 [in] Liczba ograniczeń.  
  
 `ppConstraints`  
 [out] Zwraca tablicę zawierającą ograniczenia związane z tym polem.  
  
 `pcConstraints`  
 [w, out] Liczba ograniczeń `ppConstraints` tablicy.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia sposób zaimplementować tę metodę do **CDebugGenericParamFieldType** obiekt ujawniający [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md) interfejsu.  
  
```cpp  
HRESULT CDebugGenericParamFieldType::GetConstraints(  
    ULONG32 cConstraints,  
    IDebugField** ppConstraints,  
    ULONG32* pcConstraints)  
{  
    HRESULT hr = S_OK;  
    CComPtr<IMetaDataImport> pMetadata;  
    CComPtr<IMetaDataImport2> pMetadata2;  
    mdGenericParamConstraint* rgParamConsts = NULL;  
    HCORENUM hEnum = 0;  
    ULONG cConst = 0;  
    ULONG iConst;  
    ULONG iConstOut = 0;  
  
    METHOD_ENTRY( CDebugGenericParamFieldType::GetConstraints );  
  
    IfFalseGo(ppConstraints && pcConstraints, E_INVALIDARG );  
    *pcConstraints = 0;  
  
    IfNullGo( rgParamConsts = new mdGenericParamConstraint[cConstraints], E_OUTOFMEMORY);  
  
    IfFailGo( m_spSH->GetMetadata( m_idModule, &pMetadata ) );  
    IfFailGo( pMetadata->QueryInterface(IID_IMetaDataImport2, (void**)&pMetadata2) );  
    IfFailGo( pMetadata2->EnumGenericParamConstraints( &hEnum,  
              m_tokParam,  
              rgParamConsts,  
              cConstraints,  
              &cConst) );  
    pMetadata->CloseEnum(hEnum);  
    hEnum = NULL;  
  
    for (iConst = 0; iConst < cConst; iConst++)  
    {  
        mdToken tokConst;  
  
        IfFailGo( pMetadata2->GetGenericParamConstraintProps( rgParamConsts[iConst],  
                  NULL,  
                  &tokConst ) );  
        switch (TypeFromToken(tokConst))  
        {  
            case mdtTypeRef:  
                {  
                    Module_ID mid;  
                    mdTypeDef tokClass;  
  
                    IfFailGo( CDebugClassFieldType::GetClassToken(m_spSH, m_idModule, tokConst, &mid, &tokClass) );  
                    IfFailGo( m_spSH->CreateClassType( mid, tokClass, ppConstraints + iConstOut ) );  
                    iConstOut++;  
                    break;  
                }  
            case mdtTypeDef:  
                {  
                    IfFailGo( m_spSH->CreateClassType( m_idModule, tokConst, ppConstraints + iConstOut ) );  
                    iConstOut++;  
                    break;  
                }  
            case mdtTypeSpec:  
                {  
                    PCCOR_SIGNATURE pvSig;  
                    ULONG cbSig;  
                    DWORD cb = 0;  
                    DWORD dwElementType;  
  
                    IfFailGo( pMetadata2->GetTypeSpecFromToken( tokConst, &pvSig, &cbSig) );  
  
                    cb += CorSigUncompressData(&(pvSig[cb]), &dwElementType);  
  
                    IfFailGo( m_spSH->CreateType( pvSig, cbSig, m_idModule, mdMethodDefNil, m_pGenScope, ppConstraints + iConstOut ) );  
  
                    iConstOut++;  
  
                    break;  
                }  
            default:  
                {  
                    ASSERT(!"Bad constraint token");  
                }  
        }  
    }  
  
    *pcConstraints = iConstOut;  
  
Error:  
  
    METHOD_EXIT( CDebugGenericParamFieldType::GetConstraints, hr );  
  
    DELETERG(rgParamConsts);  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)