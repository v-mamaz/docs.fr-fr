---
title: COR_PRF_FUNCTION_ARGUMENT_INFO, structure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4e791bdc41707133fb787a511a39d3ec3d7453a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="17bd5-102">COR_PRF_FUNCTION_ARGUMENT_INFO, structure</span><span class="sxs-lookup"><span data-stu-id="17bd5-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="17bd5-103">Représente les arguments d’une fonction, selon un ordre de gauche à droite.</span><span class="sxs-lookup"><span data-stu-id="17bd5-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17bd5-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="17bd5-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="17bd5-105">Membres</span><span class="sxs-lookup"><span data-stu-id="17bd5-105">Members</span></span>  
  
|<span data-ttu-id="17bd5-106">Membre</span><span class="sxs-lookup"><span data-stu-id="17bd5-106">Member</span></span>|<span data-ttu-id="17bd5-107">Description</span><span class="sxs-lookup"><span data-stu-id="17bd5-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="17bd5-108">Le nombre de blocs d’arguments.</span><span class="sxs-lookup"><span data-stu-id="17bd5-108">The number of blocks of arguments.</span></span> <span data-ttu-id="17bd5-109">Autrement dit, cette valeur est le nombre de [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures dans le `ranges` tableau.</span><span class="sxs-lookup"><span data-stu-id="17bd5-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="17bd5-110">La taille totale de tous les arguments.</span><span class="sxs-lookup"><span data-stu-id="17bd5-110">The total size of all arguments.</span></span> <span data-ttu-id="17bd5-111">En d’autres termes, cette valeur est la somme des longueurs d’argument.</span><span class="sxs-lookup"><span data-stu-id="17bd5-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="17bd5-112">Un tableau de `COR_PRF_FUNCTION_ARGUMENT_RANGE` des structures, dont chacun représente un bloc d’arguments de fonction.</span><span class="sxs-lookup"><span data-stu-id="17bd5-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17bd5-113">Remarques</span><span class="sxs-lookup"><span data-stu-id="17bd5-113">Remarks</span></span>  
 <span data-ttu-id="17bd5-114">Une fonction peut avoir d’arguments.</span><span class="sxs-lookup"><span data-stu-id="17bd5-114">A function may have many arguments.</span></span> <span data-ttu-id="17bd5-115">Ces arguments ne peuvent pas être stockés contiguë en mémoire.</span><span class="sxs-lookup"><span data-stu-id="17bd5-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="17bd5-116">Vous pouvez avoir un bloc de trois arguments dans un seul emplacement, un bloc de deux arguments à un autre emplacement et un dernier bloc d’un argument dans un emplacement différent.</span><span class="sxs-lookup"><span data-stu-id="17bd5-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="17bd5-117">Ces arguments sont tous pour la même fonction ; elles sont uniquement stockées dans des emplacements différents.</span><span class="sxs-lookup"><span data-stu-id="17bd5-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="17bd5-118">Le `COR_PRF_FUNCTION_ARGUMENT_INFO` structure représente tous les arguments d’une fonction unique.</span><span class="sxs-lookup"><span data-stu-id="17bd5-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="17bd5-119">Il utilise un tableau pour référencer tous les blocs d’arguments de fonction.</span><span class="sxs-lookup"><span data-stu-id="17bd5-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="17bd5-120">Par conséquent, pour une fonction unique, vous avez un seul `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, qui fait référence à plusieurs `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, chacun pointant vers un ou plusieurs arguments de fonction.</span><span class="sxs-lookup"><span data-stu-id="17bd5-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="17bd5-121">Les arguments qui sont stockés dans les registres sont répandus dans la mémoire pour générer les structures.</span><span class="sxs-lookup"><span data-stu-id="17bd5-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17bd5-122">Spécifications</span><span class="sxs-lookup"><span data-stu-id="17bd5-122">Requirements</span></span>  
 <span data-ttu-id="17bd5-123">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17bd5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17bd5-124">**En-tête :** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="17bd5-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="17bd5-125">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17bd5-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17bd5-126">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17bd5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17bd5-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17bd5-127">See Also</span></span>  
 [<span data-ttu-id="17bd5-128">Structures de profilage</span><span class="sxs-lookup"><span data-stu-id="17bd5-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)