---
title: Ajouter, modifier ou supprimer les valeurs par défaut d’un paramètre de rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10460"
- sql12.rtp.rptdesigner.reportparameters.defaultvalues.f1
- "10072"
ms.assetid: 6a87e069-b3a9-47b6-bcec-afcdd8aff65f
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 294940b2ffdeab57d3cde8f7a1fe8a8b61d6532a
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48221879"
---
# <a name="add-change-or-delete-default-values-for-a-report-parameter-report-builder-and-ssrs"></a>Ajouter, modifier ou supprimer les valeurs par défaut d'un paramètre de rapport (Générateur de rapports et SSRS)
  Après avoir créé un paramètre de rapport, vous pouvez fournir une liste de valeurs par défaut. Si tous les paramètres ont une valeur par défaut valide, le rapport s'exécute automatiquement lorsque vous l'affichez pour la première fois ou en affichez un aperçu.  
  
 Les paramètres de rapport peuvent représenter une ou plusieurs valeurs. Pour les valeurs uniques, vous pouvez fournir un littéral ou une expression. Pour les valeurs multiples, vous pouvez fournir une liste statique ou une liste provenant d'un dataset de rapport.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 Après la publication d'un rapport, vous pouvez remplacer les valeurs par défaut définies dans l'outil de création de rapports en définissant les valeurs de propriété de paramètre sur le serveur de rapports. Vous pouvez également fournir plusieurs jeux de valeurs de paramètre par défaut en créant des rapports liés. Pour plus d’informations, consultez [les paramètres de rapport &#40;Générateur de rapports et Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md)  
  
### <a name="to-add-or-change-the-default-values-for-a-report-parameter"></a>Pour ajouter ou modifier les valeurs par défaut d'un paramètre de rapport  
  
1.  Dans le volet Données du rapport, développez le nœud **Paramètres** . Cliquez avec le bouton droit sur le paramètre, puis cliquez sur **Modifier**. La boîte de dialogue **Propriétés du paramètre de rapport** s'ouvre.  
  
    > [!NOTE]  
    >  Si le volet Données du rapport n’est pas visible, cliquez sur **Affichage** , puis sur **Données du rapport**.  
  
2.  Cliquez sur **Valeurs par défaut**.  
  
3.  Sélectionnez une option par défaut :  
  
    -   Pour fournir manuellement une valeur ou une liste de valeurs, cliquez sur **Spécifier les valeurs**. Cliquez sur **Ajouter** , puis entrez la valeur dans la zone de texte **Valeur** . Vous pouvez écrire une expression pour une valeur. Le type de données doit correspondre au type de données du paramètre. Les noms de champs ne peuvent pas être utilisés dans une expression pour un paramètre.  
  
         Pour les paramètres à valeurs multiples, répétez cette étape pour toutes les valeurs que vous souhaitez fournir. L'ordre des éléments que vous voyez dans cette liste détermine l'ordre dans lequel l'utilisateur les voit dans la liste déroulante. Pour modifier l’ordre d’un élément dans la liste, cliquez sur la zone de texte **Valeur** pour sélectionner l’élément, puis utilisez les flèches haut et bas pour déplacer l’élément dans la liste.  
  
    -   Pour fournir le nom d’un dataset existant qui récupère les valeurs, cliquez sur **Obtenir les valeurs à partir d’une requête**. Dans **Dataset**, choisissez le nom du dataset.  
  
         Dans **Champ de valeur**, choisissez le nom du champ qui fournit les valeurs de paramètre.  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-the-default-values-for-a-report-parameter"></a>Pour supprimer les valeurs par défaut d'un paramètre de rapport  
  
1.  Dans le volet Données du rapport, développez le nœud **Paramètres** . Cliquez avec le bouton droit sur le paramètre, puis cliquez sur **Modifier**. La boîte de dialogue **Propriétés du paramètre de rapport** s'ouvre.  
  
2.  Cliquez sur **Valeurs par défaut**.  
  
3.  Dans **Sélectionnez l’une des options suivantes**, cliquez sur **Aucune valeur par défaut**.  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Paramètres de rapport &#40;Générateur de rapports et Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md)   
 [Ajouter des paramètres en cascade à un rapport &#40;Générateur de rapports et SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Didacticiel : ajouter un paramètre à un rapport &#40;Générateur de rapports&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupes &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Références à la collection Parameters&#40;Générateur de rapports et SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md)   
 [Modifier l’ordre d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)   
 [Ajouter, modifier ou supprimer un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)   
 [Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md)  
  
  
