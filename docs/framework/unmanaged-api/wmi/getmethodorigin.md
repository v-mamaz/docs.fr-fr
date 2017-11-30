---
title: "GetMethodOrigin (fonction) (référence des API non managées)"
description: "La fonction GetMethodOrigin détermine la classe dans laquelle une méthode est déclarée."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethodOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethodOrigin
helpviewer_keywords: GetMethodOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7982ef2f272173e89434b64a4c296a2ce963594e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2017
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="dfa0e-103">GetMethodOrigin (fonction)</span><span class="sxs-lookup"><span data-stu-id="dfa0e-103">GetMethodOrigin function</span></span>
<span data-ttu-id="dfa0e-104">Détermine la classe dans laquelle une méthode est déclarée.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="dfa0e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="dfa0e-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="dfa0e-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="dfa0e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="dfa0e-107">[in] Ce paramètre est inutilisé.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="dfa0e-108">[in] Un pointeur vers un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="dfa0e-109">[in] Le nom de la méthode de l’objet dont la classe propriétaire est demandée.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="dfa0e-110">[out] Reçoit le nom de la classe qui possède la méthode.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="dfa0e-111">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="dfa0e-111">Return value</span></span>

<span data-ttu-id="dfa0e-112">Les valeurs suivantes est retournées par cette fonction sont définies dans le *WbemCli.h* fichier d’en-tête, ou vous pouvez les définir en tant que constantes dans votre code :</span><span class="sxs-lookup"><span data-stu-id="dfa0e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="dfa0e-113">Constante</span><span class="sxs-lookup"><span data-stu-id="dfa0e-113">Constant</span></span>  |<span data-ttu-id="dfa0e-114">Valeur</span><span class="sxs-lookup"><span data-stu-id="dfa0e-114">Value</span></span>  |<span data-ttu-id="dfa0e-115">Description</span><span class="sxs-lookup"><span data-stu-id="dfa0e-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="dfa0e-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="dfa0e-116">0x80041002</span></span> | <span data-ttu-id="dfa0e-117">La méthode spécifiée est introuvable.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="dfa0e-118">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="dfa0e-118">0x80041008</span></span> | <span data-ttu-id="dfa0e-119">Un ou plusieurs paramètres ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="dfa0e-120">0</span><span class="sxs-lookup"><span data-stu-id="dfa0e-120">0</span></span> | <span data-ttu-id="dfa0e-121">L’appel de fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="dfa0e-122">Remarques</span><span class="sxs-lookup"><span data-stu-id="dfa0e-122">Remarks</span></span>

<span data-ttu-id="dfa0e-123">Cette fonction encapsule un appel à la [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) (méthode).</span><span class="sxs-lookup"><span data-stu-id="dfa0e-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="dfa0e-124">Car une classe peut hériter des méthodes à partir d’une ou plusieurs classes de base, les développeurs souhaitent souvent de déterminer la classe dans laquelle une méthode donnée est définie.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="dfa0e-125">Le `pstrClassName` paramètre ne doit pas pointer vers un valide `BSTR` avant l’appel de la fonction, car il s’agit d’un `out` paramètre ; ce pointeur n’est pas libéré une fois que la fonction retourne.</span><span class="sxs-lookup"><span data-stu-id="dfa0e-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="dfa0e-126">Spécifications</span><span class="sxs-lookup"><span data-stu-id="dfa0e-126">Requirements</span></span>  
<span data-ttu-id="dfa0e-127">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfa0e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfa0e-128">**En-tête :** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="dfa0e-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="dfa0e-129">**Versions du .NET framework :**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dfa0e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa0e-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dfa0e-130">See also</span></span>  
[<span data-ttu-id="dfa0e-131">WMI et les compteurs de Performance (référence des API non managées)</span><span class="sxs-lookup"><span data-stu-id="dfa0e-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)