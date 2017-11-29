---
title: "ICorDebugNativeFrame::GetLocalRegisterValue — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 43fdfc5cf4f17aaa9b26fc4a028c98c63a1b3c54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="f009a-102">ICorDebugNativeFrame::GetLocalRegisterValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="f009a-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="f009a-103">Pobiera wartość argumentu lub zmiennej lokalnej, która jest przechowywana w rejestrze określonego dla tego natywną.</span><span class="sxs-lookup"><span data-stu-id="f009a-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f009a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f009a-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f009a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f009a-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="f009a-106">[in] Wartość wyliczenia "CorDebugRegister", która określa rejestru zawierającego wartość.</span><span class="sxs-lookup"><span data-stu-id="f009a-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f009a-107">[in] Liczba całkowita określająca rozmiar podpisu metadanych binarny, który odwołuje się do niego `pvSigBlob` parametru.</span><span class="sxs-lookup"><span data-stu-id="f009a-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f009a-108">[in] A `PCCOR_SIGNATURE` wartość, która wskazuje podpisu metadanych binarnego typu wartości.</span><span class="sxs-lookup"><span data-stu-id="f009a-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f009a-109">[out] Wskaźnik do adresu reprezentujący pobranej wartości przechowywanej w rejestrze określonego obiektu "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="f009a-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f009a-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f009a-110">Remarks</span></span>  
 <span data-ttu-id="f009a-111">`GetLocalRegisterValue` Metoda może być używana w ramka natywna lub just-in-time (JIT)-skompilowany ramki.</span><span class="sxs-lookup"><span data-stu-id="f009a-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f009a-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f009a-112">Requirements</span></span>  
 <span data-ttu-id="f009a-113">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f009a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f009a-114">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f009a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f009a-115">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f009a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f009a-116">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f009a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f009a-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f009a-117">See Also</span></span>  
 