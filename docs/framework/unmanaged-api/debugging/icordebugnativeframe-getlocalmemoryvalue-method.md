---
title: "ICorDebugNativeFrame::GetLocalMemoryValue — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalMemoryValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a43bc0b4bcfb50804e4bffbe4f4f18280f873436
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a>ICorDebugNativeFrame::GetLocalMemoryValue — Metoda
Pobiera wartość argumentu lub zmiennej lokalnej, która znajduje się w lokalizacji pamięci określona dla tej ramki macierzystego.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `address`  
 [in] A `CORDB_ADDRESS` wartość, która określa lokalizację pamięci zawierającą wartość.  
  
 `cbSigBlob`  
 [in] Liczba całkowita określająca rozmiar podpisu metadanych binarny, który odwołuje się do niego `pvSigBlob` parametru.  
  
 `pvSigBlob`  
 [in] A `PCCOR_SIGNATURE` wartość, która wskazuje podpisu metadanych binarnego typu wartości.  
  
 `ppValue`  
 [out] Wskaźnik do adresu "ICorDebugValue" obiekt reprezentujący pobranej przechowywanego w lokalizacji pamięci określonej wartości.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 