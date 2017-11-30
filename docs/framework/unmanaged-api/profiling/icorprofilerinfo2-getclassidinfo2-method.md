---
title: "ICorProfilerInfo2::GetClassIDInfo2, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetClassIDInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8bfa970acd21a518112dd6ee9228b621758e49f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="832a8-102">ICorProfilerInfo2::GetClassIDInfo2, méthode</span><span class="sxs-lookup"><span data-stu-id="832a8-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="832a8-103">Obtient le module parent et les métadonnées de jeton pour la définition générique ouverte de la classe spécifiée, le `ClassID` de sa classe parente et le `ClassID` pour chaque argument de type, le cas échéant, de la classe.</span><span class="sxs-lookup"><span data-stu-id="832a8-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="832a8-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="832a8-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="832a8-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="832a8-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="832a8-106">[in] ID de la classe pour laquelle les informations seront récupérées.</span><span class="sxs-lookup"><span data-stu-id="832a8-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="832a8-107">[out] Pointeur vers l’ID du module parent pour la définition générique ouverte de la classe spécifiée.</span><span class="sxs-lookup"><span data-stu-id="832a8-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="832a8-108">[out] Pointeur vers le jeton de métadonnées pour la définition générique ouverte de la classe spécifiée.</span><span class="sxs-lookup"><span data-stu-id="832a8-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="832a8-109">[out] Pointeur vers l'ID de la classe parente.</span><span class="sxs-lookup"><span data-stu-id="832a8-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="832a8-110">[in] Taille du tableau `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="832a8-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="832a8-111">[out] Pointeur vers le nombre total d'éléments disponibles.</span><span class="sxs-lookup"><span data-stu-id="832a8-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="832a8-112">[out] Tableau de valeurs `ClassID`, chacune représentant l'ID d'un argument de type de la classe.</span><span class="sxs-lookup"><span data-stu-id="832a8-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="832a8-113">Quand la méthode retourne son résultat, `typeArgs` contient une partie ou la totalité des valeurs `ClassID` disponibles.</span><span class="sxs-lookup"><span data-stu-id="832a8-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="832a8-114">Remarques</span><span class="sxs-lookup"><span data-stu-id="832a8-114">Remarks</span></span>  
 <span data-ttu-id="832a8-115">Le `GetClassIDInfo2` méthode est similaire à la [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) (méthode), mais `GetClassIDInfo2` Obtient des informations supplémentaires sur un type générique.</span><span class="sxs-lookup"><span data-stu-id="832a8-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="832a8-116">Le code du profileur peut appeler [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) pour obtenir un [métadonnées](../../../../docs/framework/unmanaged-api/metadata/index.md) interface pour un module donné.</span><span class="sxs-lookup"><span data-stu-id="832a8-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="832a8-117">Le jeton de métadonnées qui est retourné à l'emplacement référencé par `pTypeDefToken` peut alors servir à accéder aux métadonnées pour la classe.</span><span class="sxs-lookup"><span data-stu-id="832a8-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="832a8-118">Suite au retour de `GetClassIDInfo2`, vous devez vérifier que le tampon `typeArgs` est suffisamment grand pour contenir toutes les valeurs `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="832a8-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="832a8-119">Pour ce faire, comparez la valeur vers laquelle `pcNumTypeArgs` pointe à celle du paramètre `cNumTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="832a8-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="832a8-120">Si `pcNumTypeArgs` pointe vers une valeur supérieure à `cNumTypeArgs`, allouez une mémoire tampon `typeArgs` plus grande, mettez à jour `cNumTypeArgs` pour refléter la nouvelle taille et rappelez `GetClassIDInfo2`.</span><span class="sxs-lookup"><span data-stu-id="832a8-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="832a8-121">Vous pouvez également commencer par appeler `GetClassIDInfo2` avec un tampon `typeArgs` de longueur nulle pour obtenir la taille correcte du tampon.</span><span class="sxs-lookup"><span data-stu-id="832a8-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="832a8-122">Vous pouvez ensuite définir la taille du tampon `typeArgs` sur la valeur retournée dans `pcNumTypeArgs`, puis appeler `GetClassIDInfo2` à nouveau.</span><span class="sxs-lookup"><span data-stu-id="832a8-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="832a8-123">Spécifications</span><span class="sxs-lookup"><span data-stu-id="832a8-123">Requirements</span></span>  
 <span data-ttu-id="832a8-124">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="832a8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="832a8-125">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="832a8-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="832a8-126">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="832a8-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="832a8-127">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="832a8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832a8-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="832a8-128">See Also</span></span>  
 [<span data-ttu-id="832a8-129">ICorProfilerInfo (Interface)</span><span class="sxs-lookup"><span data-stu-id="832a8-129">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="832a8-130">ICorProfilerInfo2 (Interface)</span><span class="sxs-lookup"><span data-stu-id="832a8-130">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="832a8-131">Interfaces de profilage</span><span class="sxs-lookup"><span data-stu-id="832a8-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="832a8-132">Profilage</span><span class="sxs-lookup"><span data-stu-id="832a8-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)