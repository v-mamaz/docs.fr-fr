---
title: Applications multicouches LINQ to SQL avec ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: b85392408d2fa62c481381c5028e228f280a1dc8
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093650"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>Applications multicouches LINQ to SQL avec ASP.NET
Dans les applications [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] qui utilisent [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], vous utilisez le contrôle serveur Web <xref:System.Web.UI.WebControls.LinqDataSource> . Ce contrôle gère la plus grande part de la logique dont il doit disposer pour exécuter des requêtes sur [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], passer les données au navigateur, les récupérer et les soumettre à [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> qui met ensuite à jour la base de données. Vous configurez simplement le contrôle dans le balisage et le contrôle gère tous les transferts de données entre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] et le navigateur. Le contrôle gérant les interactions avec la couche Présentation et [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gérant les communications avec la couche Données, votre tâche principale dans les applications multicouches [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] est l'écriture de votre logique métier personnalisée.  
  
 Pour plus d’informations sur `LINQDataSource`, consultez [vue d’ensemble du contrôle serveur Web LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>Voir aussi
- [Applications multicouches et distantes avec LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
