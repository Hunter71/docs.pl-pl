---
title: "CeeSectionAttr — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionAttr
helpviewer_keywords: CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f0c87c0e5703f13cf843ca5a4213440af71bd12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="bbde9-102">CeeSectionAttr — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="bbde9-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="bbde9-103">Zawiera wartości, które określają atrybuty sekcji na potrzeby używania przez [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfejsu.</span><span class="sxs-lookup"><span data-stu-id="bbde9-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbde9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="bbde9-104">Syntax</span></span>  
  
```  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="bbde9-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="bbde9-105">Members</span></span>  
  
|<span data-ttu-id="bbde9-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="bbde9-106">Member</span></span>|<span data-ttu-id="bbde9-107">Opis</span><span class="sxs-lookup"><span data-stu-id="bbde9-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="bbde9-108">Sekcja nie ma żadnych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="bbde9-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="bbde9-109">Sekcja zawiera zainicjowane dane, które mogą być tylko odczytywane, nie zaktualizowano.</span><span class="sxs-lookup"><span data-stu-id="bbde9-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="bbde9-110">Sekcja zawiera zainicjowane dane, które można odczytać lub zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="bbde9-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="bbde9-111">Sekcja zawiera kod wykonywalny, który może być do odczytu i wykonywane.</span><span class="sxs-lookup"><span data-stu-id="bbde9-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bbde9-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bbde9-112">Requirements</span></span>  
 <span data-ttu-id="bbde9-113">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbde9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbde9-114">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bbde9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bbde9-115">**Biblioteka:** uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bbde9-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bbde9-116">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbde9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbde9-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bbde9-117">See Also</span></span>  
 [<span data-ttu-id="bbde9-118">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="bbde9-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)