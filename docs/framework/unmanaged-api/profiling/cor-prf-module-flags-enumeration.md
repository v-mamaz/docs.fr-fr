---
title: "COR_PRF_MODULE_FLAGS, énumération"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_MODULE_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_MODULE_FLAGS
helpviewer_keywords: COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 54a8ee366431360f7b653b48f4ce407a35f8465b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="corprfmoduleflags-enumeration"></a><span data-ttu-id="64ded-102">COR_PRF_MODULE_FLAGS, énumération</span><span class="sxs-lookup"><span data-stu-id="64ded-102">COR_PRF_MODULE_FLAGS Enumeration</span></span>
<span data-ttu-id="64ded-103">Spécifie les propriétés d'un module.</span><span class="sxs-lookup"><span data-stu-id="64ded-103">Specifies the properties of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64ded-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="64ded-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_MODULE_DISK             = 0x00000001,  
    COR_PRF_MODULE_NGEN             = 0x00000002,  
    COR_PRF_MODULE_DYNAMIC          = 0x00000004,  
    COR_PRF_MODULE_COLLECTIBLE      = 0x00000008,  
    COR_PRF_MODULE_RESOURCE         = 0x00000010,  
    COR_PRF_MODULE_FLAT_LAYOUT      = 0x00000020,  
    COR_PRF_MODULE_WINDOWS_RUNTIME  = 0x00000040  
}   COR_PRF_MODULE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="64ded-105">Membres</span><span class="sxs-lookup"><span data-stu-id="64ded-105">Members</span></span>  
  
|<span data-ttu-id="64ded-106">Membre</span><span class="sxs-lookup"><span data-stu-id="64ded-106">Member</span></span>|<span data-ttu-id="64ded-107">Description</span><span class="sxs-lookup"><span data-stu-id="64ded-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="64ded-108">COR_PRF_MODULE_DISK</span><span class="sxs-lookup"><span data-stu-id="64ded-108">COR_PRF_MODULE_DISK</span></span>|<span data-ttu-id="64ded-109">Le module a été chargé à partir du disque.</span><span class="sxs-lookup"><span data-stu-id="64ded-109">The module was loaded from disk.</span></span>|  
|<span data-ttu-id="64ded-110">COR_PRF_MODULE_NGEN</span><span class="sxs-lookup"><span data-stu-id="64ded-110">COR_PRF_MODULE_NGEN</span></span>|<span data-ttu-id="64ded-111">Le module a été généré par le Générateur d’images natives (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="64ded-111">The module was generated by the Native Image Generator (Ngen.exe).</span></span>|  
|<span data-ttu-id="64ded-112">COR_PRF_MODULE_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="64ded-112">COR_PRF_MODULE_DYNAMIC</span></span>|<span data-ttu-id="64ded-113">Le module a été créé par les méthodes dans le <xref:System.Reflection.Emit?displayProperty=nameWithType> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="64ded-113">The module was created by methods in the <xref:System.Reflection.Emit?displayProperty=nameWithType> namespace.</span></span>|  
|<span data-ttu-id="64ded-114">COR_PRF_MODULE_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="64ded-114">COR_PRF_MODULE_COLLECTIBLE</span></span>|<span data-ttu-id="64ded-115">Durée de vie du module est gérée par le garbage collector.</span><span class="sxs-lookup"><span data-stu-id="64ded-115">The module's lifetime is managed by the garbage collector.</span></span>|  
|<span data-ttu-id="64ded-116">COR_PRF_MODULE_RESOURCE</span><span class="sxs-lookup"><span data-stu-id="64ded-116">COR_PRF_MODULE_RESOURCE</span></span>|<span data-ttu-id="64ded-117">Le module ne contient aucune métadonnée et est exclusivement utilisé en tant que ressource.</span><span class="sxs-lookup"><span data-stu-id="64ded-117">The module contains no metadata and is used strictly as a resource.</span></span> <span data-ttu-id="64ded-118">L’équivalent managé de ce bit est la <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> (méthode).</span><span class="sxs-lookup"><span data-stu-id="64ded-118">The managed equivalent of this bit is the <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="64ded-119">COR_PRF_MODULE_FLAT_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="64ded-119">COR_PRF_MODULE_FLAT_LAYOUT</span></span>|<span data-ttu-id="64ded-120">Mise en page du module en mémoire est plat, non mappé.</span><span class="sxs-lookup"><span data-stu-id="64ded-120">The module's layout in memory is flat, not mapped.</span></span> <span data-ttu-id="64ded-121">Si un module a ce bit défini, les profileurs qui lisent des informations directement à partir de l’en-tête du fichier exécutable portable (PE) ont d’être prudent lors de l’interprétation des adresses virtuelles relatives (RVA) dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="64ded-121">If a module has this bit set, profilers that read information directly from the portable executable (PE) file header will have to be careful when interpreting relative virtual addresses (RVAs) in the header.</span></span>|  
|<span data-ttu-id="64ded-122">COR_PRF_MODULE_WINDOWS_RUNTIME</span><span class="sxs-lookup"><span data-stu-id="64ded-122">COR_PRF_MODULE_WINDOWS_RUNTIME</span></span>|<span data-ttu-id="64ded-123">L’indicateur de type de contenu de Windows Runtime est défini dans les métadonnées pour l’assembly de ce module.</span><span class="sxs-lookup"><span data-stu-id="64ded-123">The Windows Runtime content type flag is set in the metadata for this module's assembly.</span></span> <span data-ttu-id="64ded-124">C’est le cas pour tous les modules de métadonnées Windows (.winmd).</span><span class="sxs-lookup"><span data-stu-id="64ded-124">This is the case for all Windows Metadata (.winmd) modules.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64ded-125">Remarques</span><span class="sxs-lookup"><span data-stu-id="64ded-125">Remarks</span></span>  
 <span data-ttu-id="64ded-126">Bits de COR_PRF_MODULE_FLAGS sont retournés au profileur dans le `pdwModuleFlags` paramètre de sortie de la [ICorProfilerInfo3::GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="64ded-126">Bits from COR_PRF_MODULE_FLAGS are returned to the profiler in the `pdwModuleFlags` output parameter of the [ICorProfilerInfo3::GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) method.</span></span> <span data-ttu-id="64ded-127">Certaines combinaisons de deux ou plusieurs indicateurs sont possibles, mais pas toutes les combinaisons possibles.</span><span class="sxs-lookup"><span data-stu-id="64ded-127">Some combinations of two or more flags are possible, but not all combinations are possible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64ded-128">Spécifications</span><span class="sxs-lookup"><span data-stu-id="64ded-128">Requirements</span></span>  
 <span data-ttu-id="64ded-129">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64ded-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64ded-130">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64ded-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64ded-131">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64ded-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64ded-132">**Versions du .NET framework :**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64ded-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ded-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64ded-133">See Also</span></span>  
 [<span data-ttu-id="64ded-134">Énumérations de profilage</span><span class="sxs-lookup"><span data-stu-id="64ded-134">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)