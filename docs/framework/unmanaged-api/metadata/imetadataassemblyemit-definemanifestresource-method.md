---
title: "IMetaDataAssemblyEmit::DefineManifestResource — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 516099f0735e83982fcbab62936bb398c4f7b02d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="71505-102">IMetaDataAssemblyEmit::DefineManifestResource — Metoda</span><span class="sxs-lookup"><span data-stu-id="71505-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="71505-103">Tworzy `ManifestResource` struktury metadane zawierające dla określonego zasobu manifestu i zwraca token skojarzone metadane.</span><span class="sxs-lookup"><span data-stu-id="71505-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71505-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="71505-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71505-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="71505-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="71505-106">[in] Nazwa zasobu.</span><span class="sxs-lookup"><span data-stu-id="71505-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="71505-107">[in] Token metadanych typu `mdtFile` lub `mdtAssemblyRef` mapujący do dostawcy zasobów.</span><span class="sxs-lookup"><span data-stu-id="71505-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="71505-108">Wartości NULL wskazuje, że plik, w którym jest osadzony metadanych jest dostawcy zasobów.</span><span class="sxs-lookup"><span data-stu-id="71505-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="71505-109">[in] Przesunięcie początku zasobów w pliku.</span><span class="sxs-lookup"><span data-stu-id="71505-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="71505-110">Dla zasobów w plikach autonomicznego ta będzie zawsze równa zero.</span><span class="sxs-lookup"><span data-stu-id="71505-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="71505-111">Jeśli zasób jest osadzony w pliku PE (przenośny plik wykonywalny), to przesunięcie obiektu BLOB, który uruchamia się w lokalizacji określonej w pliku nagłówka cor.h zasobu.</span><span class="sxs-lookup"><span data-stu-id="71505-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="71505-112">[in] Bitowe połączenie wartości flagi, które określają ustawienia właściwości definicji zasobu.</span><span class="sxs-lookup"><span data-stu-id="71505-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="71505-113">[out] Wskaźnik do tokenu metadane zwrócony.</span><span class="sxs-lookup"><span data-stu-id="71505-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71505-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="71505-114">Remarks</span></span>  
 <span data-ttu-id="71505-115">Jeden `ManifestResource` struktura metadanych musi być zdefiniowana dla każdego zasobu jest zaimplementowana w każdym z zestawu plików.</span><span class="sxs-lookup"><span data-stu-id="71505-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71505-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="71505-116">Requirements</span></span>  
 <span data-ttu-id="71505-117">**Platforma:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71505-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71505-118">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71505-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71505-119">**Biblioteka:** używany jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71505-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71505-120">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71505-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71505-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="71505-121">See Also</span></span>  
 [<span data-ttu-id="71505-122">IMetaDataAssemblyEmit — interfejs</span><span class="sxs-lookup"><span data-stu-id="71505-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)