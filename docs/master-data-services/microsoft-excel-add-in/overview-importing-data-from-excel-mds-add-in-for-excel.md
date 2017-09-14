---
title: "Vue d’ensemble : Importation de données à partir d’Excel (complément MDS pour Excel) | Documents Microsoft"
ms.custom:
- SQL2016_New_Updated
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea84a9aa-aeec-411b-ab8d-bc1b14f864a3
caps.latest.revision: 13
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: c84ecb3308a641a538bcb8aaf85ebcf728d15cb3
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="overview-importing-data-from-excel-mds-add-in-for-excel"></a>Vue d’ensemble : importation de données à partir d’Excel (complément MDS pour Excel)
  Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publiez les données dans le référentiel MDS lorsque vous souhaitez les partager avec d’autres utilisateurs. Dès que les données sont publiées, elles peuvent être téléchargées par les autres utilisateurs du complément.  
  
 Lorsque vous publiez des données, toutes celles que vous avez ajoutées ou mises à jour sont publiées dans le référentiel MDS. Les données que vous avez supprimées ne sont pas publiées, vous devez les supprimer séparément. Pour plus d’informations, consultez [Delete a Row &#40;MDS Add-in for Excel&#41;](../../master-data-services/microsoft-excel-add-in/delete-a-row-mds-add-in-for-excel.md).  
  
> [!NOTE]  
>  La publication ne peut pas être utilisée pour créer une entité. Pour plus d’informations sur la création d’entités, consultez [Créer une entité &#40;Complément MDS pour Excel&#41;](../../master-data-services/microsoft-excel-add-in/create-an-entity-mds-add-in-for-excel.md).  
  
## <a name="when-multiple-users-publish-at-the-same-time"></a>Lorsque plusieurs utilisateurs publient en même temps  
 Plusieurs utilisateurs peuvent publier des mises à jour sur les mêmes données. Lorsqu'un utilisateur publie, la mise à jour est enregistrée dans la base de données. Cela signifie qu'un utilisateur qui ne travaille pas sur des données récemment mises à jour peut toujours modifier leurs valeurs lorsqu'il les publie.  
  
 Seules les modifications que vous apportez sont publiées dans la base de données. Aucune donnée obsolète dans la feuille de calcul n'est publiée.  
  
## <a name="transactions-and-annotations"></a>Transactions et annotations  
 Chaque modification publiée est enregistrée comme une transaction. Si vous le souhaitez, vous pouvez ajouter des annotations (commentaires) à une transaction, pour expliquer pourquoi vous avez effectué la modification.  
  
-   Vous ne pouvez pas annoter les suppressions, bien que celles-ci soient enregistrées en tant que transactions qui peuvent être inversées par un administrateur.  
  
-   Si vous modifiez la valeur **Code** d’un membre, toutes les transactions précédentes de ce membre seront indisponibles. En redéfinissant **Code** sur sa valeur d’origine, vous pourrez accéder aux transactions précédentes.  
  
-   Vous pouvez afficher les transactions effectuées sur un membre par d'autres utilisateurs. Vous pouvez également afficher toutes les transactions que vous avez effectuées sur un membre, même si vous n'avez plus l'autorisation d'accès aux attributs spécifiques. Vous ne pouvez pas visualiser les transactions qui impliquent des attributs dans lesquels votre autorisation est définie sur Refuser.  
  
 Vous pouvez afficher toutes les transactions effectuées sur un membre. Pour plus d’informations, consultez [View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;](../../master-data-services/microsoft-excel-add-in/view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).  
  
> [!IMPORTANT]  
>  Si vous entrez une annotation de plus de 500 caractères, elle sera automatiquement tronquée.  
  
## <a name="business-rule-and-other-validation"></a>Règle d'entreprise et autres validations  
 Lorsque vous publiez des données, une validation est exécutée pour garantir que les données sont exactes avant d'être ajoutées au référentiel MDS. Si les données ne répondent pas aux critères spécifiés, elles ne seront pas publiées dans le référentiel. Pour plus d’informations, consultez [Validation des données &#40;Complément MDS pour Excel&#41;](../../master-data-services/microsoft-excel-add-in/validating-data-mds-add-in-for-excel.md).  
  
## <a name="related-tasks"></a>Tâches associées  
  
|Description de la tâche|Rubrique|  
|----------------------|-----------|  
|Publiez des données à partir de la feuille de calcul active vers le référentiel MDS.|[Publier des données d’Excel dans MDS &#40;Complément MDS pour Excel&#41;](../../master-data-services/microsoft-excel-add-in/import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)|  
|Supprimez une ligne du référentiel MDS et de la feuille de calcul en même temps.|[Supprimer une ligne &#40;Complément MDS pour Excel&#41;](../../master-data-services/microsoft-excel-add-in/delete-a-row-mds-add-in-for-excel.md)|  
|Visualisez les annotations (commentaires) et les transactions des lignes de données (membres) lorsque vous souhaitez consulter les mises à jour des données dans le temps.|[Afficher toutes les annotations ou transactions pour un membre &#40;Complément MDS pour Excel&#41;](../../master-data-services/microsoft-excel-add-in/view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md)|  
|Combinez les données de deux feuilles de calcul lorsque vous souhaitez comparer les données avant la publication.|[Combiner des données &#40;Complément MDS pour Excel&#41;](../../master-data-services/microsoft-excel-add-in/combine-data-mds-add-in-for-excel.md)|  

  
## <a name="related-content"></a>Contenu connexe  
  
-   [Actualisation des données &#40;Complément MDS pour Excel&#41;](../../master-data-services/microsoft-excel-add-in/refreshing-data-mds-add-in-for-excel.md)  
  
-   [Complément Master Data Services pour Microsoft Excel](../../master-data-services/microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md)  
  
  