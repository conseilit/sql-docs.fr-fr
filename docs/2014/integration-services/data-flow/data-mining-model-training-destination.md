---
title: Destination d’apprentissage du modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingmodeltrainingdest.f1
helpviewer_keywords:
- destinations [Integration Services], Data Mining Model Training
- Data Mining Model Training destination
- mining models [Analysis Services], training
- training mining models
ms.assetid: 6bc8cbe2-46af-4f7b-93d6-86779313c9d7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: fdef0e0ed6de3bf527a5b87bc05a12e1bc6ace5f
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48068956"
---
# <a name="data-mining-model-training-destination"></a>Destination d’apprentissage du modèle d’exploration de données
  La destination d'apprentissage du modèle d'exploration de données exerce les modèles d'exploration de données en transmettant les données que la destination reçoit par le biais des algorithmes de modèles d'exploration de données. Plusieurs modèles d'exploration de données peuvent faire l'objet d'un apprentissage par une même destination si les modèles sont construits sur la même structure d'exploration des données. Pour plus d’informations, consultez [Colonnes de structure d’exploration de données](../../analysis-services/data-mining/mining-structure-columns.md) et [Colonnes d’un modèle d’exploration de données](../../analysis-services/data-mining/mining-model-columns.md).  
  
## <a name="configuration-of-the-data-mining-model-training-destination"></a>Configuration de la destination d'apprentissage du modèle d'exploration de données  
 Si une colonne de niveau de cas de la structure cible et les modèles créés sur cette structure ont un contenu de type KEY TIME ou KEY SEQUENCE, les données d'entrée doivent être triées sur cette colonne. Par exemple, les modèles créés à l'aide de l'algorithme Microsoft Time Series utilisent le type de contenu KEY TIME. Si les données d'entrée ne sont pas triées, le traitement du modèle risque d'échouer. Si les données doivent être triées, vous pouvez utiliser une transformation de tri plus haut dans le flux de données afin de trier les données. Ceci ne s'applique pas aux colonnes dont le type de contenu est KEY. Pour plus d’informations, consultez [Types de contenu &#40;exploration de données&#41;](../../analysis-services/data-mining/content-types-data-mining.md) et [Transformation de tri](transformations/sort-transformation.md).  
  
> [!NOTE]  
>  L'entrée de la destination d'apprentissage du modèle d'exploration de données doit être triée. Pour trier les données, vous pouvez inclure une destination de tri en amont de la destination d'apprentissage du modèle d'exploration de données dans le flux de données. Pour plus d’informations, voir [Sort Transformation](transformations/sort-transformation.md).  
  
 La destination comporte une entrée et aucune sortie.  
  
 La destination d’apprentissage du modèle d’exploration de données utilise un gestionnaire de connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour se connecter au projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à l’instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui contient la structure et les modèles d’exploration de données dont la destination assure l’apprentissage. Pour plus d'informations, consultez [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).  
  
 Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.  
  
 Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur d’apprentissage du modèle d’exploration de données**, cliquez sur l’une des rubriques suivantes :  
  
-   [Éditeur d’apprentissage du modèle d’exploration de données données &#40;onglet Connexion&#41;](../data-mining-model-training-editor-connection-tab.md)  
  
-   [Éditeur d’apprentissage du modèle d’exploration de données données &#40;onglet colonnes&#41;](../data-mining-model-training-editor-columns-tab.md)  
  
 La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation. Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :  
  
-   [Propriétés communes](../common-properties.md)  
  
-   [Propriétés personnalisées de la destination d’apprentissage du modèle d’exploration de données](data-mining-model-training-destination-custom-properties.md)  
  
 Pour plus d’informations sur la façon de définir des propriétés, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).  
  
  
