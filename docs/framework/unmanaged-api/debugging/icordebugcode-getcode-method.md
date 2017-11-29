---
title: "ICorDebugCode::GetCode — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12820d0be725c92754640aaa4eebca56bbc33ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode — Metoda
Pobiera cały kod dla określonej funkcji, sformatowany dezasemblacji. Ta metoda jest przestarzała w programie .NET Framework w wersji 2.0. Użyj [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) zamiast tego.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `startOffset`  
 [in] Przesunięcie początku funkcji.  
  
 `endOffset`  
 [in] Przesunięcia końca funkcji.  
  
 `cBufferAlloc`  
 [in] Rozmiar `buffer` tablicy, do której zostanie zwrócony kod.  
  
 `buffer`  
 [out] Tablica, do którego zostanie zwrócony kod.  
  
 `pcBufferSize`  
 [out] Liczba bajtów zwrócona.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli kod funkcji został podzielony na wiele fragmentów, są one połączone w porządku rosnących przesunięcie natywnego. Instrukcja granice nie są sprawdzane.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Zobacz też  
 [GetCodeChunks — metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 