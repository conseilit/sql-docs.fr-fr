---
title: Relation de synchronisation d’entités (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology:
- master-data-services
ms.topic: conceptual
ms.assetid: bd627a2d-dc64-47e9-9a71-2d0ad04b4962
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 0cc2a083ef0ead82da8829e9a03206e416186427
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47843067"
---
# <a name="entity-sync-relationship-master-data-services"></a>Relation de synchronisation d’entités (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  La synchronisation d’entités est une synchronisation unidirectionnelle et reproductible entre des versions d’entités. Elle vous permet de partager des données d’entités entre différents modèles. Vous pouvez conserver une seule source fiable dans un modèle et réutiliser ces données de référence dans d’autres modèles. Par exemple, vous pouvez stocker des données américaines dans une entité de modèle et réutiliser ces données dans d’autres modèles.  
  
 Avec la synchronisation d’entités, vous pouvez aussi copier les données en une seule fois.  
  
 Tous les membres feuille avec attributs de forme libre et attributs de fichier dans l’entité source sont synchronisés avec l’entité cible lors de l’exécution de la synchronisation. Cette opération crée, supprime et modifie le schéma de l’entité ainsi que les membres.  
  
 Dès qu’une relation de synchronisation a été établie, l’entité cible ne peut être modifiée que par synchronisation. Une relation de synchronisation peut être supprimée à tout moment pour permettre la modification de l’entité cible.  
  
## <a name="see-also"></a> Voir aussi  
 [Créer et exécuter une relation de synchronisation d’entités &#40;Master Data Services&#41;](../master-data-services/create-and-execute-an-entity-sync-relationship-master-data-services.md)   
 [Modifier et supprimer une relation de synchronisation d’entités &#40;Master Data Services&#41;](../master-data-services/edit-and-delete-an-entity-sync-relationship-master-data-services.md)  
  
  
