---
title: Sys.partition_parameters (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- partition_parameters_TSQL
- partition_parameters
- sys.partition_parameters_TSQL
- sys.partition_parameters
dev_langs:
- TSQL
helpviewer_keywords:
- sys.partition_parameters catalog view
ms.assetid: 2012ed9d-3ea3-4c29-9b78-dfa54a392dce
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 464fc14c2dbb192fb5c06aee7c718cfec5806d54
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47791157"
---
# <a name="syspartitionparameters-transact-sql"></a>sys.partition_parameters (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Contient une ligne pour chaque paramètre d'une fonction de partition.  
  
|Nom de colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|**function_id**|**Int**|Identificateur de la fonction de partition à laquelle appartient ce paramètre.|  
|**parameter_id**|**Int**|ID du paramètre. Unique au sein de la fonction de partition, en commençant par 1.|  
|**system_type_id**|**tinyint**|Identificateur du type système du paramètre. Correspond à la **system_type_id** colonne de la **sys.types** vue de catalogue.|  
|**max_length**|**smallint**|Longueur maximale du paramètre, en octets.|  
|**Précision**|**tinyint**|Précision du paramètre s'il est de type numérique ; sinon, 0.|  
|**Mise à l’échelle**|**tinyint**|Échelle du paramètre s'il est de type numérique ; sinon, 0.|  
|**collation_name**|**sysname**|Nom du classement du paramètre s'il est constitué de caractères alphanumériques, sinon NULL.|  
|**user_type_id**|**Int**|ID du type. Unique dans la base de données. Pour les types de données système **user_type_id** = **system_type_id**.|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Affichages catalogue des fonctions de partition &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/partition-function-catalog-views-transact-sql.md)   
 [Affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [sys.partition_functions &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partition-functions-transact-sql.md)   
 [Sys.partition_range_values &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partition-range-values-transact-sql.md)  
  
  
