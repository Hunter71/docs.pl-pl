---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9874c8e567a89fd3977be360666c86406f2cd395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[Obsługiwane w [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] i nowszych wersjach]  
  
 Odczytuje bajtów ze strumienia symbol w pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `moduleId`  
 [in] Identyfikator modułu zawierającego strumienia w pamięci.  
  
 `symbolsReadOffset`  
 [in] Przesunięcie w ramach strumienia w pamięci, jaką należy rozpocząć odczyt bajtów.  
  
 `pSymbolBytes`  
 [out] Wskaźnik do buforu, do którego zostaną skopiowane dane. Rozmiar buforu powinien mieć `countSymbolBytes` dostępnego miejsca.  
  
 `countSymbolBytes`  
 [in] Liczba bajtów do skopiowania.  
  
 `pCountSymbolBytesRead`  
 [out] Gdy metoda zwróci wartość, zawiera rzeczywista liczba bajtów odczytanych.  
  
## <a name="return-value"></a>Wartość zwracana  
 `S_OK`, jeśli zostały odczytane niezerową liczbę bajtów.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, jeśli moduł został utworzony przy użyciu <xref:System.Reflection.Emit>.  
  
## <a name="remarks"></a>Uwagi  
 `ReadInMemorySymbols` Metody podejmuje próbę odczytania `countSymbolBytes` danych, rozpoczynając od przesunięcia `symbolsReadOffset` w strumieniu w pamięci. Dane są kopiowane do `pSymbolBytes`, który powinien mieć `countSymbolBytes` dostępnego miejsca.     `pCountSymbolsBytesRead` zawiera rzeczywista liczba bajtów odczytanych, co może być mniejsza niż `countSymbolBytes` gdy zostanie osiągnięty koniec strumienia.  
  
> [!NOTE]
>  Bieżąca implementacja nie obsługuje Reflection.Emit. Jeśli moduł został utworzony przy użyciu Reflection.Emit, metoda zwraca `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICorProfilerInfo7, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
