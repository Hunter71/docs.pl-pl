---
title: ICorProfilerInfo4::InitializeCurrentThread — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5a4a6bc7b1e79068b11b099352cec64dd09f301
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread — Metoda
Inicjuje bieżący wątek klienta z wyprzedzeniem kolejnych profilera, który wywołania interfejsu API w tym samym wątku, aby uniknąć tego zakleszczenia.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Uwagi  
 Firma Microsoft zaleca, aby wywołać `InitializeCurrentThread` w którymkolwiek wątku, który będzie dzwonić profiler interfejsu API, gdy są zawieszone wątków. Ta metoda jest zwykle używana przez profilowania próbkowania, które utworzyć własne wątku do wywołania [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) przedstawiono metodę w celu stosu podczas docelowy wątek jest zawieszony. Wywołując `InitializeCurrentThread` po po profilera najpierw tworzy wątku próbkowania, profilery można zapewnić, inicjowanie tego wątku opóźnieniem, które wykonywania innych podczas pierwszego wywołania do środowiska CLR `DoStackSnapshot` może teraz wystąpić bezpiecznie kiedy są nie ma innych wątków zawieszone.  
  
> [!NOTE]
>  `InitializeCurrentThread` nie inicjowania z wyprzedzeniem, aby zakończyć zadania wykonuj blokad, które mogą zakleszczenie. Wywołanie `InitializeCurrentThread` tylko wtedy, gdy nie ma żadnych zawieszonych wątków.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICorProfilerInfo4, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Interfejsy profilowania](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilowanie](../../../../docs/framework/unmanaged-api/profiling/index.md)
