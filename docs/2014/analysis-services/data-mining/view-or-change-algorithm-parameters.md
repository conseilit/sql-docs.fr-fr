---
title: Afficher ou modifier les paramètres d’algorithme | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- algorithms [data mining]
- mining models [Analysis Services], algorithms
ms.assetid: 151b899b-c27a-4a09-bcf5-5c9f0ec24168
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 18889a1dfded5f8653446c02a637502a75efd659
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48226987"
---
# <a name="view-or-change-algorithm-parameters"></a>Afficher ou modifier les paramètres d'algorithme
  Vous pouvez modifier les paramètres fournis avec les algorithmes que vous utilisez pour générer des modèles d'exploration de données pour personnaliser les résultats du modèle.  
  
 Les paramètres d’algorithme disponibles dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] modifient beaucoup plus que les seules propriétés du modèle. En effet, ils peuvent être utilisés pour modifier radicalement le traitement, le regroupement et l’affichage des données. Par exemple, vous pouvez utiliser des paramètres d'algorithme pour effectuer les opérations suivantes :  
  
-   modifier la méthode d'analyse, telle que la méthode de clustering ;  
  
-   contrôler le comportement de la sélection des fonctionnalités ;  
  
-   spécifier la taille des jeux d'éléments ou la probabilité des règles ;  
  
-   contrôler la création de branche et la profondeur des arbres de décision ;  
  
-   spécifier une valeur de départ ou la taille du jeu de données d'exclusion interne utilisé pour la création de modèle.  
  
 Les paramètres fournis pour chaque algorithme varient considérablement. Pour obtenir la liste des paramètres que vous pouvez définir pour chaque algorithme, consultez les rubriques de références techniques dans cette section : [Algorithmes d’exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining-algorithms-analysis-services-data-mining.md).  
  
### <a name="change-an-algorithm-parameter"></a>Changer un paramètre d'algorithme  
  
1.  Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez avec le bouton droit sur le type d’algorithme du modèle d’exploration de données dont vous voulez régler l’algorithme, puis sélectionnez **Définir les paramètres de l’algorithme**.  
  
     La boîte de dialogue **Paramètres d’algorithme** s’affiche.  
  
2.  Dans la colonne **Valeur** , définissez une nouvelle valeur pour l’algorithme à modifier.  
  
     Si vous n’entrez pas de valeur dans la colonne **Valeur** , [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilise la valeur de paramètre par défaut. La colonne **Plage** décrit les valeurs possibles que vous pouvez entrer.  
  
3.  Cliquez sur **OK**.  
  
     La nouvelle valeur est affectée à l'algorithme. Pour que la modification soit appliquée au paramètre dans le modèle d'exploration de données, vous devez retraiter le modèle.  
  
### <a name="view-the-parameters-used-in-an-existing-model"></a>Afficher les paramètres utilisés dans un modèle existant  
  
1.  Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez une fenêtre de requête DMX.  
  
2.  Tapez une requête semblable à celle-ci :  
  
    ```  
    select MINING_PARAMETERS   
    from $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = '<model name>'  
  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches et procédures des modèles d’exploration de données](mining-model-tasks-and-how-tos.md)  
  
  
