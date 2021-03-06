---
title: Sys.security_policies (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- SYS.SECURITY_POLICIES_TSQL
- SECURITY_POLICIES_TSQL
- SYS.SECURITY_POLICIES
- SECURITY_POLICIES
dev_langs:
- TSQL
helpviewer_keywords:
- sys.security_policies catalog view
- security_policies catalog view
ms.assetid: 35362f5b-e601-4049-9e1d-c5307e823831
author: VanMSFT
ms.author: vanto
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 5c0462984a2c1ff7c28d0ff327eedc415ff2c30c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47704667"
---
# <a name="syssecuritypolicies-transact-sql"></a>Sys.security_policies (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Retourne une ligne pour chaque stratégie de sécurité dans la base de données.  
  
|Nom de colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|NAME|**sysname**|Nom de la stratégie de sécurité, unique dans la base de données.|  
|object_id|**Int**|ID de la stratégie de sécurité.|  
|principal_id|**Int**|ID du propriétaire de la stratégie de sécurité, tel qu'enregistré dans la base de données. NULL si le propriétaire est déterminé par le schéma.|  
|schema_id|**Int**|ID du schéma où réside l'objet.|  
|parent_object_id|**Int**|Identificateur de l'objet auquel appartient la stratégie. Doit être égal à 0.|  
|Type|**vachar(2)**|Doit être **SP**.|  
|type_desc|**nvarchar(60)**|**SECURITY_POLICY**.|  
|create_date|**datetime**|Date UTC de création de la stratégie de sécurité.|  
|modify_date|**datetime**|Date UTC de dernière modification de la stratégie de sécurité.|  
|is_ms_shipped|**bit**|Toujours false.|  
|is_enabled|**bit**|État de spécification de stratégie de sécurité :<br /><br /> 0 = désactivé<br /><br /> 1 = activé|  
|is_not_for_replication|**bit**|La stratégie a été créée avec l'option NOT FOR REPLICATION.|  
|uses_database_collation|**bit**|Utilise le même classement que la base de données.|  
|is_schemabinding_enabled|**bit**|État de la liaison au schéma pour la stratégie de sécurité :<br /><br /> 0 ou NULL = activé<br /><br /> 1 = désactivé|  
  
## <a name="permissions"></a>Permissions  
 Les principaux avec le **ALTER ANY SECURITY POLICY** autorisation ont accès à tous les objets dans cette vue de catalogue, ainsi que toute personne ayant **VIEW DEFINITION** sur l’objet.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité au niveau des lignes](../../relational-databases/security/row-level-security.md)   
 [sys.security_predicates &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-security-predicates-transact-sql.md)   
 [CREATE SECURITY POLICY &#40;Transact-SQL&#41;](../../t-sql/statements/create-security-policy-transact-sql.md)   
 [Affichages catalogue de sécurité &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [Affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Principaux &#40;moteur de base de données&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)  
  
  
