---
title: sysmergesubsetfilters (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- replication
ms.topic: language-reference
f1_keywords:
- sysmergesubsetfilters
- sysmergesubsetfilters_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysmergesubsetfilters system table
ms.assetid: f91d1c6c-3132-47f6-926c-88f56848cafe
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: c0b87c85c3d45c87aed84604bb0b7732c47ffa5e
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47783277"
---
# <a name="sysmergesubsetfilters-transact-sql"></a>sysmergesubsetfilters (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contient des informations sur les filtres de jointure des articles partitionnés. Cette table est stockée dans les bases de données de publication et d’abonnement.  
  
|Nom de colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|**nom de filtre**|**sysname**|Nom du filtre utilisé pour créer l'article.|  
|**join_filterid**|**Int**|ID de l'objet représentant le filtre de jointure.|  
|**pubid**|**uniqueidentifier**|ID de la publication.|  
|**artid**|**uniqueidentifier**|L’ID de l’article.|  
|**art_nickname**|**Int**|Surnom de l'article.|  
|**join_articlename**|**sysname**|Nom de la table avec laquelle il faut effectuer une jointure pour déterminer si la ligne lui appartient.|  
|**join_nickname**|**Int**|Surnom de la table avec laquelle il faut effectuer une jointure pour déterminer si la ligne lui appartient.|  
|**join_unique_key**|**Int**|Indique une jointure sur une clé unique de **join_tablename**:<br /><br /> 0 = N'est pas une clé unique<br /><br /> 1 = Est une clé unique|  
|**expand_proc**|**sysname**|Nom de la procédure stockée utilisée par l'Agent de fusion pour identifier les lignes à envoyer à un Abonné ou à supprimer de celui-ci.|  
|**join_filterclause**|**nvarchar(1000)**|Clause de filtre utilisée pour la jointure.|  
|**filter_type**|**tinyint**|Spécifie le type de filtre parmi les types suivants :<br /><br /> 1 = Filtre de jointure.<br /><br /> 2 = Lien d'enregistrement logique.<br /><br /> 3 = Filtre de jointure et lien d'enregistrement logique.|  
  
## <a name="see-also"></a>Voir aussi  
 [Tables de réplication &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Vues de réplication &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
