---
title: "CorSymSearchPolicyAttributes, énumération"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymSearchPolicyAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymSearchPolicyAttributes
helpviewer_keywords: CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 016378de8d4ba4b6f16f7e7b91b6427f73c9687d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="3d87f-102">CorSymSearchPolicyAttributes, énumération</span><span class="sxs-lookup"><span data-stu-id="3d87f-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="3d87f-103">Spécifie la stratégie à utiliser lorsque vous effectuez une recherche pour un lecteur de symboles.</span><span class="sxs-lookup"><span data-stu-id="3d87f-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="3d87f-104">Ces constantes sont utilisées par le [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) et [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) méthodes.</span><span class="sxs-lookup"><span data-stu-id="3d87f-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3d87f-105">Il s’agit d’un risque de sécurité pour ouvrir un fichier du programme (PDB) de la base de données à partir d’une source non fiable.</span><span class="sxs-lookup"><span data-stu-id="3d87f-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d87f-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3d87f-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="3d87f-107">Membres</span><span class="sxs-lookup"><span data-stu-id="3d87f-107">Members</span></span>  
  
|<span data-ttu-id="3d87f-108">Membre</span><span class="sxs-lookup"><span data-stu-id="3d87f-108">Member</span></span>|<span data-ttu-id="3d87f-109">Description</span><span class="sxs-lookup"><span data-stu-id="3d87f-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="3d87f-110">Interroge le Registre pour les chemins de recherche de symbole.</span><span class="sxs-lookup"><span data-stu-id="3d87f-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="3d87f-111">Accède à un serveur de symboles.</span><span class="sxs-lookup"><span data-stu-id="3d87f-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="3d87f-112">Recherche le chemin d’accès spécifié dans le répertoire de débogage.</span><span class="sxs-lookup"><span data-stu-id="3d87f-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="3d87f-113">Recherche le fichier PDB à l’endroit où le fichier .exe.</span><span class="sxs-lookup"><span data-stu-id="3d87f-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d87f-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="3d87f-114">Requirements</span></span>  
 <span data-ttu-id="3d87f-115">**En-tête :** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3d87f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d87f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d87f-116">See Also</span></span>  
 [<span data-ttu-id="3d87f-117">Énumérations du magasin de symboles de Diagnostics</span><span class="sxs-lookup"><span data-stu-id="3d87f-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)