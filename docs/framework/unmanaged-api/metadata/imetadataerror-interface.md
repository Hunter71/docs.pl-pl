---
title: "IMetaDataError — Interfejs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError
helpviewer_keywords: IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ae90221a1b305fdf09ae9583e720a2092289362
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="21e73-102">IMetaDataError — Interfejs</span><span class="sxs-lookup"><span data-stu-id="21e73-102">IMetaDataError Interface</span></span>
<span data-ttu-id="21e73-103">Udostępnia mechanizm wywołania zwrotnego dla usługi raportowania błędów podczas scalania metadanych.</span><span class="sxs-lookup"><span data-stu-id="21e73-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21e73-104">`IMetaDataError` Interfejs musi być implementowana przez klienta.</span><span class="sxs-lookup"><span data-stu-id="21e73-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21e73-105">Metody</span><span class="sxs-lookup"><span data-stu-id="21e73-105">Methods</span></span>  
  
|<span data-ttu-id="21e73-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="21e73-106">Method</span></span>|<span data-ttu-id="21e73-107">Opis</span><span class="sxs-lookup"><span data-stu-id="21e73-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21e73-108">OnError — metoda</span><span class="sxs-lookup"><span data-stu-id="21e73-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="21e73-109">Zapewnia powiadomienie błędów występujących podczas scalania metadanych.</span><span class="sxs-lookup"><span data-stu-id="21e73-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21e73-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="21e73-110">Requirements</span></span>  
 <span data-ttu-id="21e73-111">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21e73-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21e73-112">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="21e73-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21e73-113">**Biblioteka:** używany jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21e73-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21e73-114">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21e73-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e73-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="21e73-115">See Also</span></span>  
 [<span data-ttu-id="21e73-116">Interfejsy metadanych</span><span class="sxs-lookup"><span data-stu-id="21e73-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)