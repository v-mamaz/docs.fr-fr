---
title: ICorProfilerInfo::GetILFunctionBodyAllocator, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0ae8b209ad03594cb77029193b0e9dec773a6e02
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603324"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a>ICorProfilerInfo::GetILFunctionBodyAllocator, méthode
Obtient une interface qui fournit une méthode pour allouer de mémoire pouvant être utilisée pour permuter le corps d’une méthode dans le code Microsoft intermediate language (MSIL).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `moduleId`  
 [in] L’ID du module dans lequel réside la méthode.  
  
 `ppMalloc`  
 [out] Un pointeur vers un [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface qui fournit une méthode pour allouer la mémoire.  
  
## <a name="remarks"></a>Notes  
 Un corps de méthode en code MSIL doit se trouver en tant qu’une adresse virtuelle relative (RVA), par rapport à module chargé, ce qui signifie qu’il suit le module au sein de 4 Go. Pour faciliter un outil qui permet de permuter le corps d’une méthode, le `GetILFunctionBodyAllocator` méthode garantit que la mémoire est allouée dans cette plage.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl, CorProf.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [ICorProfilerInfo, interface](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
