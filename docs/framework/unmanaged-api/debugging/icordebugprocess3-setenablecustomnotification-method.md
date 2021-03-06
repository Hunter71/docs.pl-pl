---
title: ICorDebugProcess3::SetEnableCustomNotification — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a84061cff7cc5dbdeba1e0e66396e04a8f345cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification — Metoda
Włącza i wyłącza powiadomienia debugera niestandardowe określonego typu.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pClass`  
 [in] Typ, który określa debuger niestandardowych powiadomień.  
  
 `fEnable`  
 [in] `true` do włączenia powiadomień debugera niestandardowych; `false` Aby wyłączyć powiadomienia. Wartość domyślna to `false`.  
  
## <a name="remarks"></a>Uwagi  
 Gdy `fEnable` ustawiono `true`, wywołań <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> wyzwalacza — metoda [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) wywołania zwrotnego. Powiadomienia są domyślnie wyłączona; w związku z tym debuger należy określić wszystkie typy powiadomień zna i chce obsługiwać. Ponieważ [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) klasy jest ograniczone w zależności od domeny aplikacji, należy wywołać debuger `SetEnableCustomNotification` dla każdej domeny aplikacji w ramach procesu, jeśli chce otrzymywać powiadomienia przez cały proces.  
  
 Począwszy od [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], tylko powiadomień obsługiwanych jest powiadomień zależności między wątkami.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICorDebugProcess3, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debugowanie](../../../../docs/framework/unmanaged-api/debugging/index.md)
