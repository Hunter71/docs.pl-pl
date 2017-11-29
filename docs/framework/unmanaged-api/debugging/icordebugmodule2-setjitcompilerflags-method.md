---
title: "ICorDebugModule2::SetJITCompilerFlags — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42eea356214fedb22a2f60842f6007f3eb6a0e2a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="93c7d-102">ICorDebugModule2::SetJITCompilerFlags — Metoda</span><span class="sxs-lookup"><span data-stu-id="93c7d-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="93c7d-103">Ustawia flagi sterujące kompilacji to ICorDebugModule2 just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="93c7d-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93c7d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="93c7d-104">Syntax</span></span>  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93c7d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="93c7d-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="93c7d-106">[in] Bitowe połączenie [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) wartości wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="93c7d-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93c7d-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="93c7d-107">Remarks</span></span>  
 <span data-ttu-id="93c7d-108">Jeśli `dwFlags` wartość jest nieprawidłowa, `SetJITCompilerFlags` metoda zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="93c7d-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="93c7d-109">`SetJITCompilerFlags` Metodę można wywołać tylko z poziomu [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) wywołania zwrotnego dla tego modułu.</span><span class="sxs-lookup"><span data-stu-id="93c7d-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="93c7d-110">Próby wywołania je po `ICorDebugManagedCallback::LoadModule` wywołania zwrotnego został dostarczony spowoduje niepowodzenie.</span><span class="sxs-lookup"><span data-stu-id="93c7d-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="93c7d-111">Edytuj i Kontynuuj nie jest obsługiwana na 64-bitowym lub platformach Win9x.</span><span class="sxs-lookup"><span data-stu-id="93c7d-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="93c7d-112">W związku z tym jeśli wywołujesz `SetJITCompilerFlags` metodę na jedną z tych dwóch platform z flagą CORDEBUG_JIT_ENABLE_ENC w `dwFlags`, `SetJITCompilerFlags` — metoda i wszystkie metody określonej Edytuj i Kontynuuj, takich jak [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="93c7d-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93c7d-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="93c7d-113">Requirements</span></span>  
 <span data-ttu-id="93c7d-114">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93c7d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93c7d-115">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93c7d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93c7d-116">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93c7d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93c7d-117">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93c7d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>