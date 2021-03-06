---
title: ICorProfilerCallback::ObjectReferences — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e64eeff8ef80aa264c9c49bd12a0cc45e0da18a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences — Metoda
Powiadamia profilera dotyczących obiektów w pamięci, które są przywoływane przez określony obiekt.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a>Parametry  
 `objectId`  
 [in] Identyfikator obiektu, który odwołuje się do obiektów.  
  
 `classId`  
 [in] Identyfikator klasy określony obiekt jest wystąpieniem.  
  
 `cObjectRefs`  
 [in] Liczba obiektów odwołuje się określony obiekt (to znaczy, że liczba elementów w `objectRefIds` tablicy).  
  
 `objectRefIds`  
 [in] Tablicę identyfikatorów obiektów, które są przywoływane przez `objectId`.  
  
## <a name="remarks"></a>Uwagi  
 `ObjectReferences` Metoda jest wywoływana dla każdego obiektu pozostałych sterty po zakończeniu wyrzucania elementów bezużytecznych. Jeśli profilera zwraca błąd, to wywołanie zwrotne, usług profilowania nie będzie kontynuowane wywoływania tego wywołania zwrotnego do czasu następnego wyrzucanie elementów bezużytecznych.  
  
 `ObjectReferences` Wywołania zwrotnego można używać w połączeniu z [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) wywołanie zwrotne do utworzenia wykres odwołanie cały obiekt środowiska uruchomieniowego. Środowisko uruchomieniowe języka wspólnego (CLR) zapewnia, że odwołanie do każdego obiektu jest raportowane tylko raz przez `ObjectReferences` metody.  
  
 Identyfikatory obiektów zwrócona przez `ObjectReferences` są nieprawidłowe podczas wywołania zwrotnego, ponieważ wyrzucanie elementów bezużytecznych może znajdować się w środku przenoszenie obiektów. W związku z tym profilowania nie wolno próbować sprawdzić obiekty podczas `ObjectReferences` wywołania. Gdy [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) jest nazywany odzyskiwanie kolekcji została zakończona i inspekcji można bezpiecznie wykonać.  
  
 Wartość null `ClassId` oznacza to, że `objectId` ma typ, który jest zwalnianie.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICorProfilerCallback, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
