---
title: Funkcja GetPropertyOrigin (Dokumentacja interfejsu API Unmnaged)
description: "Funkcja GetPropertyOrigin Określa klasę, w którym zadeklarowany jest właściwością."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyOrigin
helpviewer_keywords: GetPropertyOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 68df29e88b41cb12d002913d5bbd42050395d871
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="b977b-103">Funkcja GetPropertyOrigin</span><span class="sxs-lookup"><span data-stu-id="b977b-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="b977b-104">Określa klasę, w którym zadeklarowany jest właściwością.</span><span class="sxs-lookup"><span data-stu-id="b977b-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b977b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b977b-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="b977b-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="b977b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b977b-107">[in] Ten parametr nie jest używana.</span><span class="sxs-lookup"><span data-stu-id="b977b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b977b-108">[in] Wskaźnik do [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="b977b-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="b977b-109">[in] Nazwa właściwości dla obiektu, w których klasa będąca właścicielem jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="b977b-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="b977b-110">[out] Uzyskuje nazwę klasy, która jest właścicielem właściwości.</span><span class="sxs-lookup"><span data-stu-id="b977b-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="b977b-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b977b-111">Return value</span></span>

<span data-ttu-id="b977b-112">Następujące wartości zwracane przez tę funkcję są zdefiniowane w *WbemCli.h* pliku nagłówka, lub należy je zdefiniować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="b977b-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b977b-113">Stała</span><span class="sxs-lookup"><span data-stu-id="b977b-113">Constant</span></span>  |<span data-ttu-id="b977b-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="b977b-114">Value</span></span>  |<span data-ttu-id="b977b-115">Opis</span><span class="sxs-lookup"><span data-stu-id="b977b-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="b977b-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b977b-116">0x80041001</span></span> | <span data-ttu-id="b977b-117">Wystąpił błąd ogólny.</span><span class="sxs-lookup"><span data-stu-id="b977b-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="b977b-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b977b-118">0x80041002</span></span> | <span data-ttu-id="b977b-119">Nie znaleziono określonej właściwości.</span><span class="sxs-lookup"><span data-stu-id="b977b-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b977b-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b977b-120">0x80041008</span></span> | <span data-ttu-id="b977b-121">Parametr jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="b977b-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b977b-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b977b-122">0x80041006</span></span> | <span data-ttu-id="b977b-123">Za mało pamięci jest dostępna do wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="b977b-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b977b-124">0</span><span class="sxs-lookup"><span data-stu-id="b977b-124">0</span></span> | <span data-ttu-id="b977b-125">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="b977b-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b977b-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b977b-126">Remarks</span></span>

<span data-ttu-id="b977b-127">Ta funkcja jest zawijana wywołanie [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) metody.</span><span class="sxs-lookup"><span data-stu-id="b977b-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b977b-128">Ponieważ klasy mogą dziedziczyć właściwości co najmniej jednej klasy podstawowej, deweloperzy często chcą określić właściwości, w którym jest zdefiniowany danej metody.</span><span class="sxs-lookup"><span data-stu-id="b977b-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="b977b-129">`pstrClassName` Parametru nie musi wskazywać na prawidłową `BSTR` przed wywołaniem funkcji, ponieważ jest to `out` parametru; ten wskaźnik nie cofnięciu przydziału po funkcja zwraca wartość.</span><span class="sxs-lookup"><span data-stu-id="b977b-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="b977b-130">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b977b-130">Requirements</span></span>  
<span data-ttu-id="b977b-131">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b977b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b977b-132">**Nagłówek:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b977b-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b977b-133">**Wersje programu .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b977b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b977b-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b977b-134">See also</span></span>  
[<span data-ttu-id="b977b-135">Liczniki wydajności (niezarządzany wykaz interfejsów API) i usługi WMI</span><span class="sxs-lookup"><span data-stu-id="b977b-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)