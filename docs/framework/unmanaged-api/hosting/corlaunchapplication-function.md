---
title: CorLaunchApplication — Funkcja
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a53b0a9cdcec33846f9d491e7d6567bcf9235b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication — Funkcja
Uruchamia aplikację w ścieżce określonej sieci przy użyciu określonego manifestów i innych danych aplikacji.  
  
 Ta funkcja jest przestarzała w [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwClickOnceHost`  
 [in] Wartość [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) wyliczenie określający typ hosta, który jest uruchomienie aplikacji.  
  
 `pwzAppFullName`  
 [in] Pełna nazwa aplikacji, w której jest on uruchomiony.  
  
 `dwManifestPaths`  
 [in] Liczba ścieżek manifestu dla aplikacji.  
  
 `ppwzManifestPaths`  
 [in] Tablica ciągów, z których każdy określa ścieżkę do manifestu dla aplikacji, która jest jest uruchamiana.  
  
 `dwActivationData`  
 [in] Liczba elementów danych aktywacji dla aplikacji, która jest jest uruchamiana.  
  
 `ppwzActivationData`  
 [in] Tablica ciągów, z których każdy jest element danych aktywacji dla aplikacji, która jest jest uruchamiana.  
  
 `lpProcessInformation`  
 [out] Wskaźnik do informacji na temat procesu, w którym został załadowany w aplikacji.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** biblioteki MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Przestarzałe funkcje hostingu środowiska CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
