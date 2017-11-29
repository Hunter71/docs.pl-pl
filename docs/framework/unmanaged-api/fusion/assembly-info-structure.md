---
title: "ASSEMBLY_INFO — Struktura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d532bbd2d338f942c09c4213620468a3361db5f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyinfo-structure"></a>ASSEMBLY_INFO — Struktura
Zawiera informacje dotyczące zestawu, który jest zarejestrowany w globalnej pamięci podręcznej zestawów.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`cbAssemblyInfo`|Rozmiar w bajtach struktury. To pole jest zarezerwowana dla przyszłych rozszerzalności.|  
|`dwAssemblyFlags`|Flagi, które wskazują szczegóły instalacji zestawu. Obsługiwane są następujące wartości:<br /><br /> Wartość ASSEMBLYINFO_FLAG_INSTALLED, co oznacza, że zestaw jest zainstalowany. Zawsze Ustawia bieżącą wersję programu .NET Framework `dwAssemblyFlags` tej wartości.<br />Wartość ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, co oznacza, że zestaw jest rezydentna ładunku. Bieżąca wersja programu .NET Framework nigdy nie ustawia `dwAssemblyFlags` tej wartości.|  
|`uliAssemblySizeInKB`|Całkowity rozmiar w kilobajtach, plików, które zawiera zestaw.|  
|`pszCurrentAssemblyPathBuf`|Wskaźnik do buforu ciągu, która przechowuje bieżącej ścieżki do pliku manifestu. Ścieżka musi kończyć się znakiem null.|  
|`cchBuf`|Liczba znaki dwubajtowe, włącznie z terminatorem null, która `pszCurrentAssemblyPathBuf` zawiera.|  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion.h  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Łączenie — struktury](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [Globalna pamięć podręczna zestawów](../../../../docs/framework/app-domains/gac.md)