---
title: "ICorDebugCode3::GetReturnValueLiveOffset — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugCode3.GetReturnValueLiveOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4516f2244b72bd4f254c5090b09d6d90579f1ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="bea82-102">ICorDebugCode3::GetReturnValueLiveOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="bea82-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="bea82-103">Określony przesunięcia IL pobiera natywnego przesunięcia gdzie ma zostać umieszczony punkt przerwania, aby debuger można uzyskać wartości zwracanej przez funkcję.</span><span class="sxs-lookup"><span data-stu-id="bea82-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea82-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="bea82-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bea82-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="bea82-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="bea82-106">Przesunięciu IL.</span><span class="sxs-lookup"><span data-stu-id="bea82-106">The IL offset.</span></span> <span data-ttu-id="bea82-107">Musi to być witryna wywołania funkcji lub wywołanie funkcji zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="bea82-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="bea82-108">Liczba bajtów dostępne do przechowywania `pOffsets`.</span><span class="sxs-lookup"><span data-stu-id="bea82-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="bea82-109">Wskaźnik do liczba przesunięć faktycznie zwracane.</span><span class="sxs-lookup"><span data-stu-id="bea82-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="bea82-110">Zwykle, jego wartość wynosi 1, ale pojedynczej instrukcji IL można mapować do wielu `CALL` instrukcje zestawu.</span><span class="sxs-lookup"><span data-stu-id="bea82-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="bea82-111">Tablica natywnego przesunięcia.</span><span class="sxs-lookup"><span data-stu-id="bea82-111">An array of native offsets.</span></span> <span data-ttu-id="bea82-112">Zazwyczaj `pOffsets` zawiera pojedynczy przesunięcie, mimo że pojedyncza instrukcja IL można mapować do mapy wiele do wielu `CALL` instrukcje zestawu.</span><span class="sxs-lookup"><span data-stu-id="bea82-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bea82-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bea82-113">Remarks</span></span>  
 <span data-ttu-id="bea82-114">Ta metoda jest używana wraz z [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodę, aby pobrać wartość zwracaną przez metodę, która zwraca typ referencyjny.</span><span class="sxs-lookup"><span data-stu-id="bea82-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="bea82-115">Przekazywanie IL przesunięcie do witryny wywołania funkcji, aby ta metoda zwraca co najmniej jednego macierzystego przesunięcia.</span><span class="sxs-lookup"><span data-stu-id="bea82-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="bea82-116">Debuger można następnie ustawić punkty przerwania w macierzystym przesunięcia w funkcji.</span><span class="sxs-lookup"><span data-stu-id="bea82-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="bea82-117">Gdy debuger trafi jednego z punktów przerwania, można następnie przekazać tej samej przesunięciu IL, który został przekazany do tej metody do [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metody można pobrać wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="bea82-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="bea82-118">Debuger należy następnie wyczyść wszystkie punkty przerwania, które go ustawić.</span><span class="sxs-lookup"><span data-stu-id="bea82-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bea82-119">`ICorDebugCode3::GetReturnValueLiveOffset` i [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metody umożliwiają uzyskanie informacji zwracanej wartości dla typów referencyjnych tylko.</span><span class="sxs-lookup"><span data-stu-id="bea82-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="bea82-120">Pobieranie informacji o wartości zwracanej z typów wartości (oznacza to, wszystkie typy, które pochodzą z <xref:System.ValueType>) nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="bea82-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="bea82-121">Funkcja zwraca `HRESULT` wartości podanych w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="bea82-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="bea82-122">`HRESULT`wartość</span><span class="sxs-lookup"><span data-stu-id="bea82-122">`HRESULT` value</span></span>|<span data-ttu-id="bea82-123">Opis</span><span class="sxs-lookup"><span data-stu-id="bea82-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="bea82-124">Powodzenie.</span><span class="sxs-lookup"><span data-stu-id="bea82-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="bea82-125">Daną witrynę przesunięcia IL nie jest instrukcja wywołania lub funkcja zwraca `void`.</span><span class="sxs-lookup"><span data-stu-id="bea82-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="bea82-126">Danym przesunięciu IL jest odpowiednie połączenie, ale zwracany typ nie jest obsługiwany dla pobierania wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="bea82-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="bea82-127">`ICorDebugCode3::GetReturnValueLiveOffset` Metoda jest dostępna tylko na podstawie x86 i systemy AMD64.</span><span class="sxs-lookup"><span data-stu-id="bea82-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bea82-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bea82-128">Requirements</span></span>  
 <span data-ttu-id="bea82-129">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bea82-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bea82-130">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bea82-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bea82-131">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bea82-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bea82-132">**Wersje programu .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea82-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea82-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bea82-133">See Also</span></span>  
 [<span data-ttu-id="bea82-134">GetReturnValueForILOffset — metoda</span><span class="sxs-lookup"><span data-stu-id="bea82-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [<span data-ttu-id="bea82-135">Icordebugcode3 — interfejs</span><span class="sxs-lookup"><span data-stu-id="bea82-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)