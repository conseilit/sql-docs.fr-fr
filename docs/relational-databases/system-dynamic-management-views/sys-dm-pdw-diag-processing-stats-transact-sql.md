---
title: Sys.dm_pdw_diag_processing_stats (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: df659c55-4f63-45f8-8afe-ce300031bc5b
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: f1e2180e6d22cee81c94d880eca1debaa20c8c5d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47837187"
---
# <a name="sysdmpdwdiagprocessingstats-transact-sql"></a>Sys.dm_pdw_diag_processing_stats (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  Affiche les informations relatives à tous les événements de diagnostics internes qui peut être incorporés dans des sessions de diagnostic définies par l’administrateur. Interroger cette vue pour comprendre les statistiques derrière les sous-systèmes de gestion des événements et de diagnostic que le remplissage de toutes les autres vues DMV le lecteur. Il existe un groupe de files d’attente pour chaque processus sur chaque nœud.  
  
|Nom de la colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|**pdw_node_id**|**Int**|Nœud d’appliance que provient ce journal.|  
|**process_id**|**Int**|Identificateur du processus en cours d’exécution soumettre cette statistique.|  
|**target_name**|**nvarchar(255)**|Nom de la file d'attente.|  
|**queue_size**|**Int**|Le nombre d’éléments dans la file d’attente de processus. La taille de file d’attente est généralement 0. Un nombre positif indique que le système est en situation de stress et construction du retard des événements. Un nombre positif dans les autres colonnes signifie système ont été endommagé pour cette file d’attente particulière et les vues DMV liées aux.|  
|**lost_events_count**|**bigint**|Le nombre d’événements perdus.|  
  
## <a name="see-also"></a>Voir aussi  
 [Vues de gestion dynamique de l’entrepôt SQL Data Warehouse et Parallel Data &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
