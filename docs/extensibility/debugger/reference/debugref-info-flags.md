---
title: DEBUGREF_INFO_FLAGS | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUGREF_INFO_FLAGS
helpviewer_keywords:
- DEBUGREF_INFO_FLAGS enumeration
ms.assetid: 1b043327-302a-4f6d-b51d-f94f9d7c7f9d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f5864b3503b19e8a473f45e4167aad835181da50
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108378"
---
# <a name="debugrefinfoflags"></a>DEBUGREF_INFO_FLAGS
Określa, jakie informacje pobrać obiekt odwołania debug — informacje.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
typedef DWORD DEBUGREF_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
```  
  
## <a name="members"></a>Elementy członkowskie  
 DEBUGREF_INFO_NAME  
 Inicjowanie użycia `bstrName` pola w strukturze.  
  
 DEBUGREF_INFO_TYPE  
 Inicjowanie użycia `bstrType` pola w strukturze.  
  
 DEBUGREF_INFO_VALUE  
 Inicjowanie użycia `bstrValue` pola w strukturze.  
  
 DEBUGREF_INFO_ATTRIB  
 Inicjowanie użycia `dwAttrib` pola w strukturze.  
  
 DEBUGREF_INFO_REFTYPE  
 Inicjowanie użycia `dwRefType` pola w strukturze.  
  
 DEBUGREF_INFO_REF  
 Inicjowanie użycia `pReference` pola w strukturze.  
  
 DEBUGREF_INFO_VALUE_AUTOEXPAND  
 Pole wartości powinien zawierać wartość rozwinięty automatycznie, jeśli jest dostępna dla tego typu obiektu.  
  
 DEBUGREF_INFO_NONE  
 Wskazuje, że ustawiono żadnych flag.  
  
 DEBUGREF_INFO_ALL  
 Wskazuje maska flag.  
  
## <a name="remarks"></a>Uwagi  
 Te flagi są przekazywane do [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) i [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) metod, aby określić, które pola [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury mają być zainicjowany.  
  
 Używany do `dwFields` członkiem `DEBUG_REFERENCE_INFO` struktury, aby wskazać pola, które są używane i ważne, gdy struktura jest zwracany.  
  
 Te wartości mogą być łączone z bitowego `OR`.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)   
 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)