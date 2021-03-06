---
title: Sys.column_store_segments (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 01/15/2018
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- column_store_segments
- sys.column_store_segments_TSQL
- sys.column_store_segments
- column_store_segments_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.column_store_segments catalog view
ms.assetid: 1253448c-2ec9-4900-ae9f-461d6b51b2ea
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: df7698d222c2c2f0f68138eaa5f6289106b97659
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47799477"
---
# <a name="syscolumnstoresegments-transact-sql"></a>sys.column_store_segments (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2014-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2014-xxxx-xxxx-xxx-md.md)]

Retourne une ligne pour chaque segment de colonne dans un index columnstore. Il existe un segment de colonne par colonne par groupe de lignes. Par exemple, une table avec 10 groupes de lignes et 34 colonnes retourne des 340 lignes. 
  
|Nom de colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|**partition_id**|**bigint**|Indique l'ID de partition. Unique dans une base de données.|  
|**hobt_id**|**bigint**|ID du segment ou de l'index d'arbre B (B-tree) pour la table ayant cet index columnstore.|  
|**column_id**|**Int**|ID de la colonne columnstore.|  
|**segment_id**|**Int**|ID du rowgroup. Pour la compatibilité descendante, le nom de colonne continue à être appelée segment_id même si cela est l’ID de groupe de lignes. Vous pouvez identifier un segment à l’aide \<hobt_id, partition_id, column_id >, < segment_id >.|  
|**version**|**Int**|Version du format de segment de colonne.|  
|**encoding_type**|**Int**|Type d’encodage utilisé pour ce segment :<br /><br /> 1 = VALUE_BASED - non chaîne/binaire avec aucun dictionnaire (très similaire à 4 avec certaines variantes internes)<br /><br /> 2 = VALUE_HASH_BASED - colonne de type chaîne ou binaire avec des valeurs courantes dans le dictionnaire<br /><br /> 3 = STRING_HASH_BASED - colonne de type chaîne ou binaire avec des valeurs courantes dans le dictionnaire<br /><br /> 4 = STORE_BY_VALUE_BASED - non chaîne/binaire avec aucun dictionnaire<br /><br /> 5 = STRING_STORE_BY_VALUE_BASED - chaîne/binaire avec aucun dictionnaire<br /><br /> Tous les encodages de tirer parti de l’encodage de compression de bits et la longueur de l’exécution lorsque cela est possible.|  
|**row_count**|**Int**|Nombre de lignes dans le groupe de lignes.|  
|**has_nulls**|**Int**|1 si le segment de colonne a des valeurs NULL.|  
|**base_id**|**bigint**|Id de la valeur de base si le type d’encodage 1 est utilisé.  Si le type d’encodage 1 n'est pas utilisé, ID a la valeur -1.|  
|**magnitude**|**float**|Grandeur si le type d’encodage 1 est utilisé.  Si le type d’encodage 1 n'est pas utilisé, grandeur a la valeur -1.|  
|**primary_dictionary_id**|**Int**|La valeur 0 représente le dictionnaire global. La valeur -1 indique qu’aucun dictionnaire global créé pour cette colonne est.|  
|**secondary_dictionary_id**|**Int**|Une valeur non nulle pointe vers le dictionnaire local pour cette colonne dans le segment actuel (par exemple, le groupe de lignes). La valeur -1 indique qu’aucun dictionnaire local pour ce segment est.|  
|**min_data_id**|**bigint**|ID de données minimum dans le segment de colonne.|  
|**max_data_id**|**bigint**|ID de données maximum dans le segment de colonne.|  
|**null_value**|**bigint**|Valeur utilisée pour représenter les valeurs NULL.|  
|**on_disk_size**|**bigint**|Taille de segment en octets.|  
  
## <a name="remarks"></a>Notes  
 La requête suivante retourne des informations sur les segments d'un index columnstore.  
  
```sql  
SELECT i.name, p.object_id, p.index_id, i.type_desc,   
    COUNT(*) AS number_of_segments  
FROM sys.column_store_segments AS s   
INNER JOIN sys.partitions AS p   
    ON s.hobt_id = p.hobt_id   
INNER JOIN sys.indexes AS i   
    ON p.object_id = i.object_id  
WHERE i.type = 5 OR i.type = 6  
GROUP BY i.name, p.object_id, p.index_id, i.type_desc ;  
GO  
```  
  
## <a name="permissions"></a>Permissions  
 Toutes les colonnes requièrent au moins **VIEW DEFINITION** autorisation sur la table. Les colonnes suivantes retournent null à moins que l’utilisateur ait également **sélectionnez** autorisation : has_nulls, base_id, magnitude, min_data_id, max_data_id et null_value.  
  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Vues de catalogue d’objets &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Interrogation des catalogues système SQL Server FAQ](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)   
 [sys.columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-columns-transact-sql.md)   
 [sys.all_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-all-columns-transact-sql.md)   
 [sys.computed_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-computed-columns-transact-sql.md)   
 [Guide des index columnstore](~/relational-databases/indexes/columnstore-indexes-overview.md)    
 [sys.column_store_dictionaries &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-column-store-dictionaries-transact-sql.md)  
  
  

