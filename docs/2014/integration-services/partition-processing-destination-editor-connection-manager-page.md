---
title: Éditeur de Destination de traitement de partition (Page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.connection.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 7add6f82-eed1-47fc-a5d7-7b91f3f24d34
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2822193b536423e29f0d838ad64dda20664c7f8b
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48200959"
---
# <a name="partition-processing-destination-editor-connection-manager-page"></a>Éditeur de destination de traitement de partition (page Gestionnaire de connexions)
  La page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de destination de traitement de partition** vous permet de spécifier une connexion à un projet [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].  
  
 Pour en savoir plus sur la destination de traitement de partition, consultez [Partition Processing Destination](data-flow/partition-processing-destination.md).  
  
> [!NOTE]  
>  Les tâches décrites ici ne s’appliquent pas aux modèles tabulaires Analysis Services.  Vous ne pouvez pas mapper des colonnes d’entrée aux colonnes de partition pour les modèles tabulaires. Vous pouvez en revanche utiliser la tâche DDL d'exécution [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) d'Analysis Services pour traiter la partition.  
  
## <a name="options"></a>Options  
 **Connection manager**  
 Sélectionnez un gestionnaire de connexions existant dans la liste ou créez une nouvelle connexion en cliquant sur **Nouveau**.  
  
 **Nouveau**  
 Créez une connexion à l’aide de la boîte de dialogue **Ajout d’un gestionnaire de connexions Analysis Services** .  
  
 **Liste des partitions disponibles**  
 Sélectionnez la partition à traiter.  
  
 **Méthode de traitement**  
 Sélectionnez la méthode de traitement. La valeur par défaut de cette option est **Complète**.  
  
|Valeur|Description|  
|-----------|-----------------|  
|Ajouter (incrémentiel)|Permet d'effectuer un traitement incrémentiel de la partition.|  
|Complète|Permet d'effectuer un traitement complet de la partition.|  
|Données seulement|Permet d'effectuer un traitement de mise à jour de la partition.|  
  
## <a name="see-also"></a>Voir aussi  
 [Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Éditeur de Destination de traitement de partition &#40;Page mappages&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md)   
 [Éditeur de Destination de traitement de partition &#40;Page avancé&#41;](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
