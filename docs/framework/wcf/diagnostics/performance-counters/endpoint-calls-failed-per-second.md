---
title: "Point de terminaison : Nombre d'appels ayant échoué par seconde"
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 03fbdd83246fa811424f445823f705a3bef5697a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608035"
---
# <a name="endpoint-calls-failed-per-second"></a>Point de terminaison : Nombre d'appels ayant échoué par seconde
Nom du compteur : Appels ayant échoué par seconde.  
  
## <a name="description"></a>Description  
 Nombre d'appels ayant des exceptions non traitées et reçus par ce point de terminaison en une seconde.  
  
 Ce compteur est de type de compteur de performances [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dont la valeur est calculée à l’aide de la formule suivante.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Ce compteur est incrémenté à chaque exception non traitée à ce point de terminaison.  
  
## <a name="see-also"></a>Voir aussi
- [Spécification et gestion des erreurs dans les contrats et les services](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
