---
title: CorSymSearchPolicyAttributes — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4c3aedea4cc8ce2d8fb8c0c0bf3fead727dcf64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>CorSymSearchPolicyAttributes — Wyliczenie
Określa zasady do użycia podczas wyszukiwania dla czytnika symboli. Stałe te są używane przez [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) i [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) metody.  
  
> [!IMPORTANT]
>  Jest to zagrożenie, aby otworzyć plik programu (PDB) bazy danych z niezaufanego źródła.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`AllowRegistryAccess`|Wysyła zapytanie do rejestru dla ścieżki wyszukiwania symboli.|  
|`AllowSymbolServerAccess`|Uzyskuje dostęp do serwera symboli.|  
|`AllowOriginalPathAccess`|Wyszukuje ścieżka określona w katalogu debugowania.|  
|`AllowReferencePathAccess`|Wyszukuje PDB w miejscu, w którym się plik .exe.|  
  
## <a name="requirements"></a>Wymagania  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia magazynu symboli diagnostycznych](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
