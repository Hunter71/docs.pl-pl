---
title: "ISymUnmanagedWriter::DefineGlobalVariable — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineGlobalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7540dfcefbe7a331a26220a07b2e206c1302ddc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="5a079-102">ISymUnmanagedWriter::DefineGlobalVariable — Metoda</span><span class="sxs-lookup"><span data-stu-id="5a079-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="5a079-103">Definiuje pojedynczą zmienną globalnego.</span><span class="sxs-lookup"><span data-stu-id="5a079-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a079-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5a079-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a079-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5a079-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5a079-106">[in] Wskaźnik do `WCHAR` definiuje nazwę zmiennej globalnej.</span><span class="sxs-lookup"><span data-stu-id="5a079-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="5a079-107">[in] Atrybuty zmiennej globalnej.</span><span class="sxs-lookup"><span data-stu-id="5a079-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="5a079-108">[in] A `ULONG32` rozmiar w znaków, który wskazuje z `signature` buforu.</span><span class="sxs-lookup"><span data-stu-id="5a079-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="5a079-109">[in] Globalne podpis zmiennej.</span><span class="sxs-lookup"><span data-stu-id="5a079-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="5a079-110">[in] Typ adresu.</span><span class="sxs-lookup"><span data-stu-id="5a079-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="5a079-111">[in] Pierwszy adres Specyfikacja parametru.</span><span class="sxs-lookup"><span data-stu-id="5a079-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="5a079-112">[in] Drugi adres Specyfikacja parametru.</span><span class="sxs-lookup"><span data-stu-id="5a079-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="5a079-113">[in] Trzeci adres Specyfikacja parametru.</span><span class="sxs-lookup"><span data-stu-id="5a079-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a079-114">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="5a079-114">Return Value</span></span>  
 <span data-ttu-id="5a079-115">Wartość S_OK, jeśli metoda zakończy się pomyślnie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="5a079-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a079-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5a079-116">Requirements</span></span>  
 <span data-ttu-id="5a079-117">**Nagłówek:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5a079-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a079-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5a079-118">See Also</span></span>  
 [<span data-ttu-id="5a079-119">ISymUnmanagedWriter — interfejs</span><span class="sxs-lookup"><span data-stu-id="5a079-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="5a079-120">DefineLocalVariable — metoda</span><span class="sxs-lookup"><span data-stu-id="5a079-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)  
 [<span data-ttu-id="5a079-121">DefineGlobalVariable2 — metoda</span><span class="sxs-lookup"><span data-stu-id="5a079-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)