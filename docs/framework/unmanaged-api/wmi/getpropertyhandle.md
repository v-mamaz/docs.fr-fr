---
title: "GetPropertyHandle (fonction) (référence des API non managées)"
description: "La fonction GetPropertyHandle retourne un identificateur unique qu’identités une propriété."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyHandle
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyHandle
helpviewer_keywords: GetPropertyHandle function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab3df6d2233059de76036da7ff27f5cc1808aaf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="afabd-103">GetPropertyHandle (fonction)</span><span class="sxs-lookup"><span data-stu-id="afabd-103">GetPropertyHandle function</span></span>
<span data-ttu-id="afabd-104">Retourne un identificateur unique qui identifie une propriété.</span><span class="sxs-lookup"><span data-stu-id="afabd-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="afabd-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="afabd-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="afabd-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="afabd-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="afabd-107">[in] Ce paramètre est inutilisé.</span><span class="sxs-lookup"><span data-stu-id="afabd-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="afabd-108">[in] Un pointeur vers un [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span><span class="sxs-lookup"><span data-stu-id="afabd-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="afabd-109">[in] Se terminant par null chaîne codée au format UTF16 characaters qui contient le nom de propriété.</span><span class="sxs-lookup"><span data-stu-id="afabd-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="afabd-110">[out] Un pointeur vers un [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) membre d’énumération qui représente le type CIM de la propriété.</span><span class="sxs-lookup"><span data-stu-id="afabd-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="afabd-111">[out] Pointeur vers un entier qui contient le descripteur de propriété.</span><span class="sxs-lookup"><span data-stu-id="afabd-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="afabd-112">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="afabd-112">Return value</span></span>

<span data-ttu-id="afabd-113">Les valeurs suivantes est retournées par cette fonction sont définies dans le *WbemCli.h* fichier d’en-tête, ou vous pouvez les définir en tant que constantes dans votre code :</span><span class="sxs-lookup"><span data-stu-id="afabd-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="afabd-114">Constante</span><span class="sxs-lookup"><span data-stu-id="afabd-114">Constant</span></span>  |<span data-ttu-id="afabd-115">Valeur</span><span class="sxs-lookup"><span data-stu-id="afabd-115">Value</span></span>  |<span data-ttu-id="afabd-116">Description</span><span class="sxs-lookup"><span data-stu-id="afabd-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="afabd-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="afabd-117">0x80041002</span></span> | <span data-ttu-id="afabd-118">Le nom de la propriété spécifiée est introuvable.</span><span class="sxs-lookup"><span data-stu-id="afabd-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="afabd-119">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="afabd-119">0x80041008</span></span> | <span data-ttu-id="afabd-120">Un paramètre n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="afabd-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="afabd-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="afabd-121">0x8004100c</span></span> | <span data-ttu-id="afabd-122">La propriété demandée est de type sont `CIM_OBJECT` ou `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="afabd-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="afabd-123">0</span><span class="sxs-lookup"><span data-stu-id="afabd-123">0</span></span> | <span data-ttu-id="afabd-124">L’appel de fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="afabd-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="afabd-125">Remarques</span><span class="sxs-lookup"><span data-stu-id="afabd-125">Remarks</span></span>

<span data-ttu-id="afabd-126">Cette fonction encapsule un appel à la [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) (méthode).</span><span class="sxs-lookup"><span data-stu-id="afabd-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="afabd-127">Vous pouvez utiliser ce handle pour identifier les propriétés lorsque vous utilisez [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) méthodes pour lire ou écrire des valeurs de propriété.</span><span class="sxs-lookup"><span data-stu-id="afabd-127">You can use this handle to identify properties when using  [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) methods to read or write property values.</span></span>

<span data-ttu-id="afabd-128">Handles peuvent être récupérées pour les propriétés de tous les types de données autres que `CIM_OBJECT` et `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="afabd-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="afabd-129">Retournée le travail de handles sur toutes les instances d’une classe.</span><span class="sxs-lookup"><span data-stu-id="afabd-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="afabd-130">Spécifications</span><span class="sxs-lookup"><span data-stu-id="afabd-130">Requirements</span></span>  
<span data-ttu-id="afabd-131">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afabd-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afabd-132">**En-tête :** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="afabd-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="afabd-133">**Versions du .NET framework :**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="afabd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afabd-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="afabd-134">See also</span></span>  
[<span data-ttu-id="afabd-135">WMI et les compteurs de Performance (référence des API non managées)</span><span class="sxs-lookup"><span data-stu-id="afabd-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)