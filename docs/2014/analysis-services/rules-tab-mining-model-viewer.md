---
title: Règles d’onglet (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.rules.f1
ms.assetid: 705d5492-b58f-45d9-94d7-ed57b7025823
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 999ea0b432733fc3458cb6f50e964209c1313b54
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48059599"
---
# <a name="rules-tab-mining-model-viewer"></a>Onglet Règles (Visionneuse de modèle d'exploration de données)
  Utilisez le volet **Règles** dans un modèle d'association pour afficher les règles que l'algorithme a extraites des données. Les règles décrivent comment les éléments sont liés entre eux et peuvent être utilisées pour créer des recommandations.  
  
 Vous pouvez utiliser les options de la visionneuse pour filtrer le nombre de règles qui y sont affichées.  
  
> [!WARNING]  
>  Par défaut, seules les règles qui se trouvent au-dessus du seuil de probabilité défini dans **Probabilité minimale** sont affichées dans la visionneuse. Vous ne pouvez pas réduire cette valeur à l'aide de la visionneuse, car le seuil de probabilité pour la sortie de règle est déterminé lors de la création du modèle. Pour plus d’informations, consultez [Références techniques relatives à l’algorithme Microsoft Association](data-mining/microsoft-association-algorithm-technical-reference.md).  
  
 **Pour plus d’informations :** [Algorithme Microsoft Association](data-mining/microsoft-association-algorithm.md), [Explorer un modèle à l’aide de la visionneuse de l’algorithme MAR (Microsoft Association Rules)](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)  
  
## <a name="options"></a>Options  
 **Actualiser le contenu de l’Observateur**  
 Recharge le modèle d'exploration de données dans la visionneuse.  
  
 **Modèle d'exploration de données**  
 Choisissez un modèle d'exploration de données pour afficher le contenu de la structure d'exploration actuelle. Le modèle d'exploration de données s'ouvre dans sa visionneuse associée.  
  
 **Visionneuse**  
 Choisissez la visionneuse à utiliser pour afficher le modèle d'exploration de données sélectionné. Vous pouvez utiliser la visionneuse personnalisée pour chaque modèle d'exploration de données, ou la **Visionneuse de l'arborescence de contenu générique Microsoft**. Vous pouvez également utiliser les visionneuses de plug-in, le cas échéant.  
  
 **Probabilité minimale**  
 Modifiez cette valeur pour définir la probabilité minimale requise pour qu'une règle soit affichée dans la visionneuse. L'augmentation de la valeur de probabilité réduira le nombre de règles affichées.  
  
 **Importance minimale**  
 Modifiez cette valeur pour définir l'importance minimale requise pour qu'une règle soit affichée dans la visionneuse. L'augmentation de la valeur d'importance réduira le nombre de règles affichées.  
  
 **Règle de filtre**  
 Tapez une valeur de chaîne pour filtrer le nombre de règles affichées dans la visionneuse.  
  
 Vous pouvez également taper des expressions régulières .NET comme critères de filtre. Par exemple, l'expression suivante retourne toutes les règles qui contiennent « Road Bottle Cage » du côté gauche de la règle :  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*->.*`  
  
 Notez que vous devrez peut-être actualiser la vue pour voir les critères de filtre appliqués. Vous pouvez également activer et désactiver l'option **Afficher le nom long** afin d'actualiser la liste.  
  
 Par défaut, les critères de filtre s'appliquent au nom complet de la combinaison attribut-valeur ; par conséquent, si vous affichez le nom de l'attribut uniquement, il n'est pas évident de savoir si les critères de filtre ont été appliqués correctement. Utilisez la liste déroulante **Afficher** pour sélectionner **Afficher le nom et la valeur de l'attribut**et vérifiez que la liste des jeux d'éléments est filtrée correctement.  
  
 **Afficher**  
 Ajustez le mode d'affichage de la règle dans la visionneuse. Vous pouvez sélectionner l'une des trois options suivantes :  
  
-   Afficher le nom et la valeur de l'attribut  
  
-   Afficher la valeur de l'attribut uniquement  
  
-   Afficher le nom de l'attribut uniquement  
  
 **Afficher le nom long**  
 Affichez le nom complet de la règle tel qu'il apparaît dans le contenu du modèle d'exploration de données.  
  
 **Nombre maximal de lignes**  
 Limitez le nombre de règles affichées dans la visionneuse.  
  
 **Probabilité**  
 Cette colonne dans le graphique affiche la probabilité de chaque règle.  
  
 Vous pouvez cliquer sur l'en-tête de colonne pour effectuer le tri d'après la probabilité.  
  
 **Importance**  
 Cette colonne dans le graphique affiche l'importance de chaque règle.  
  
 Vous pouvez cliquer sur l'en-tête de colonne pour effectuer le tri d'après l'importance.  
  
 **Règle**  
 Cette colonne du graphique affiche la description textuelle de chaque règle, selon le format spécifié à l’aide des options **Afficher** et **Afficher le nom long**.  
  
 Vous pouvez cliquer sur l'en-tête de colonne pour effectuer le tri d'après le texte de la règle.  
  
## <a name="see-also"></a>Voir aussi  
 [Algorithmes d’exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Visionneuses de modèle d’exploration de données &#40;Concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md)   
 [Visionneuses de modèle d’exploration de données](data-mining/data-mining-model-viewers.md)  
  
  
