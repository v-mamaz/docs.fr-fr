---
title: "IMetaDataEmit::DefineImportType, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4b19b291917b0b507f03c66a358b725a29234f76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="24cd1-102">IMetaDataEmit::DefineImportType, méthode</span><span class="sxs-lookup"><span data-stu-id="24cd1-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="24cd1-103">Crée une référence au type spécifié qui est défini en dehors de la portée actuelle et définit un jeton pour cette référence.</span><span class="sxs-lookup"><span data-stu-id="24cd1-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24cd1-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="24cd1-104">Syntax</span></span>  
  
```  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24cd1-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="24cd1-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="24cd1-106">[in] Un [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface qui représente l’assembly à partir duquel le type cible est importé.</span><span class="sxs-lookup"><span data-stu-id="24cd1-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="24cd1-107">[in] Tableau qui contient le code de hachage pour l’assembly spécifié par `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="24cd1-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="24cd1-108">[in] Nombre d'octets dans le tableau `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="24cd1-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="24cd1-109">[in] Un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface qui représente la portée de métadonnées à partir de laquelle le type cible est importé.</span><span class="sxs-lookup"><span data-stu-id="24cd1-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="24cd1-110">[in] Un `mdTypeDef` jeton qui spécifie le type cible.</span><span class="sxs-lookup"><span data-stu-id="24cd1-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="24cd1-111">[in] Un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface qui représente l’assembly dans lequel le type cible est importé.</span><span class="sxs-lookup"><span data-stu-id="24cd1-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="24cd1-112">[out] Le `mdTypeRef` jeton qui est défini dans l’étendue actuelle pour la référence de type.</span><span class="sxs-lookup"><span data-stu-id="24cd1-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24cd1-113">Remarques</span><span class="sxs-lookup"><span data-stu-id="24cd1-113">Remarks</span></span>  
 <span data-ttu-id="24cd1-114">Avant d’appeler le [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) (méthode), vous pouvez utiliser la `DefineImportType` méthode pour créer une référence de type dans la portée actuelle, pour la classe parente ou l’interface parente du membre.</span><span class="sxs-lookup"><span data-stu-id="24cd1-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24cd1-115">Spécifications</span><span class="sxs-lookup"><span data-stu-id="24cd1-115">Requirements</span></span>  
 <span data-ttu-id="24cd1-116">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24cd1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24cd1-117">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="24cd1-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24cd1-118">**Bibliothèque :** utilisé en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24cd1-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24cd1-119">**Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24cd1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24cd1-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24cd1-120">See Also</span></span>  
 [<span data-ttu-id="24cd1-121">IMetaDataEmit (Interface)</span><span class="sxs-lookup"><span data-stu-id="24cd1-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="24cd1-122">IMetaDataEmit2 (Interface)</span><span class="sxs-lookup"><span data-stu-id="24cd1-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)