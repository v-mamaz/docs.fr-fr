---
title: "ISymUnmanagedVariable::GetSignature, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetSignature
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e29cd4a38e9abbe380b51b81fc2849b833d87e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="c49b4-102">ISymUnmanagedVariable::GetSignature, méthode</span><span class="sxs-lookup"><span data-stu-id="c49b4-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="c49b4-103">Obtient la signature de cette variable.</span><span class="sxs-lookup"><span data-stu-id="c49b4-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c49b4-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c49b4-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c49b4-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c49b4-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="c49b4-106">[in] La longueur de la mémoire tampon vers laquelle pointe le `sig` paramètre.</span><span class="sxs-lookup"><span data-stu-id="c49b4-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="c49b4-107">[out] Un pointeur vers un `ULONG32` qui reçoit la taille, en caractères, de la mémoire tampon requise pour contenir la signature.</span><span class="sxs-lookup"><span data-stu-id="c49b4-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="c49b4-108">[out] Mémoire tampon qui stocke la signature.</span><span class="sxs-lookup"><span data-stu-id="c49b4-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c49b4-109">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c49b4-109">Return Value</span></span>  
 <span data-ttu-id="c49b4-110">S_OK si la méthode réussit ; Sinon, E_FAIL ou un autre code d’erreur.</span><span class="sxs-lookup"><span data-stu-id="c49b4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c49b4-111">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c49b4-111">Requirements</span></span>  
 <span data-ttu-id="c49b4-112">**En-tête :** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c49b4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c49b4-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c49b4-113">See Also</span></span>  
 [<span data-ttu-id="c49b4-114">ISymUnmanagedVariable (Interface)</span><span class="sxs-lookup"><span data-stu-id="c49b4-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)