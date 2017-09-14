---
title: Type de connexion Teradata (SSRS) | Documents Microsoft
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b02779c2-a6b9-453c-815f-adad53353952
caps.latest.revision: 10
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: c74e24e12f97d264780e712a1e7e5f3fbea6f9fb
ms.contentlocale: fr-fr
ms.lasthandoff: 08/09/2017

---
# <a name="teradata-connection-type-ssrs"></a>Type de connexion Teradata (SSRS)
  Pour inclure les données d'une base de données relationnelle Teradata dans votre rapport, vous devez avoir un dataset basé sur une source de données de rapport de type Teradata. Ce type de source de données intégré est basé sur le fournisseur managé .NET de l'extension pour le traitement des données Teradata.  
  
 Utilisez les informations de cette rubrique pour générer une source de données. Pour obtenir des instructions détaillées, consultez [Ajouter et vérifier une connexion de données &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).  
  
##  <a name="Connection"></a> Chaîne de connexion  
 Contactez l'administrateur de votre base de données pour connaître les informations de connexion et d'identification à utiliser pour se connecter à la source de données. L'exemple de chaîne de connexion suivant spécifie une base de données Teradata sur le serveur indiqué avec l'adresse IP :  
  
```  
data source=<IP Address>  
```  
  
 Pour obtenir d’autres exemples de chaînes de connexion, consultez [Connexions de données, sources de données et chaînes de connexion dans le Générateur de rapports](http://msdn.microsoft.com/library/7e103637-4371-43d7-821c-d269c2cc1b34).  
  
##  <a name="Credentials"></a> Informations d'identification  
 Les informations d'identification sont obligatoires pour exécuter des requêtes, afficher l'aperçu du rapport localement et afficher l'aperçu du rapport à partir du serveur de rapports.  
  
 Après avoir publié votre rapport, vous pouvez devoir modifier les informations d'identification pour la source de données afin que les autorisations soient valides pour récupérer les données lorsque le rapport s'exécute sur le serveur de rapports.  
  
 Pour plus d’informations, consultez [Connexions de données, sources de données et chaînes de connexion &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md) ou [Spécifier des informations d’identification dans le Générateur de rapports](http://msdn.microsoft.com/library/7412ce68-aece-41c0-8c37-76a0e54b6b53).  
  
  
##  <a name="Remarks"></a> Notes  
 Avant de pouvoir connecter une source de données Teradata, l'administrateur système doit installer au préalable la version du fournisseur de données .NET pour Teradata qui prend en charge la récupération des données à partir de la base de données Teradata. Ce fournisseur de données doit être installé sur le même ordinateur que le Générateur de rapports, ainsi que sur le serveur de rapports.  
  
 Certains modes de remise de rapport ne sont pas pris en charge par ce fournisseur de données. La remise des rapports par le biais d'abonnements pilotés par les données n'est pas prise en charge pour cette extension pour le traitement des données. Pour plus d’informations, consultez [Utiliser une source de données externe pour les données des abonnés &#40;abonnement piloté par les données&#41;](../../reporting-services/subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md) dans la documentation de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] disponible dans la [documentation en ligne](http://go.microsoft.com/fwlink/?linkid=121312)de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
  
##  <a name="Models"></a> Modèles de rapport  
 Pour créer un dataset à partir d'un modèle de rapport basé sur une source de données Teradata, le modèle doit être conçu dans le Générateur de modèles dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] et publié sur un serveur de rapports.  
  
  
##  <a name="Related"></a> Sections connexes  
 Ces sections de la documentation fournissent des informations de fond d'ordre conceptuel sur les données de rapport, ainsi que des informations sur les procédures de définition, de personnalisation et d'utilisation des parties d'un rapport qui sont liées aux données.  
  
 [Datasets de rapport &#40;SSRS&#41;](../../reporting-services/report-data/report-datasets-ssrs.md)  
 Fournit une vue d'ensemble de l'accès aux données pour votre rapport.  
  
 [Connexions de données, les Sources de données et les chaînes de connexion dans le Générateur de rapports](http://msdn.microsoft.com/library/7e103637-4371-43d7-821c-d269c2cc1b34)  
 Fournit des informations sur les connexions de données et les sources de données.  
  
 [Rapport incorporé des jeux de données et des Datasets partagés &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 Fournit des informations sur les datasets incorporés et partagés.  
  
 [Collection de champs de DataSet &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-data/dataset-fields-collection-report-builder-and-ssrs.md)  
 Fournit des informations sur la collection de champs générée par la requête de dataset.  
  
 [Sources de données prises en charge par Reporting Services &#40;SSRS&#41;](../../reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs.md) dans la documentation de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][](http://go.microsoft.com/fwlink/?linkid=121312).  
 Fournit des informations détaillées sur la prise en charge des plateformes et des versions pour chaque extension de données.  
  
 [Using SQL Server 2008 Reporting Services with the .NET Framework Data Provider for Teradata (éventuellement en anglais)](http://go.microsoft.com/fwlink/?LinkID=130848)  
 Fournit des informations détaillées sur l'utilisation de cette extension de données.  
  
  
## <a name="see-also"></a>Voir aussi  
 [Paramètres de rapport &#40; Le Générateur de rapports et le Concepteur de rapports &#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)   
 [Filtre, groupe et trier des données &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)   
 [Expressions &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-design/expressions-report-builder-and-ssrs.md)  
  
  