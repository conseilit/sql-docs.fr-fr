---
title: Sys.fn_servershareddrives (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_servershareddrives
- fn_servershareddrives_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- fn_servershareddrives function
- shared drives [SQL Server]
- names [SQL Server], shared drives
- sys.fn_serversharedrives function
ms.assetid: ff01eff7-8cb6-460c-ba7a-6a52bda6d471
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: a9fe23ad67b8a8cc4e687badf8ef6f75d9363e3e
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47702317"
---
# <a name="sysfnservershareddrives-transact-sql"></a>sys.fn_servershareddrives (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Renvoie les noms des lecteurs partagés utilisés par le serveur cluster.  
  
> [!IMPORTANT]  
>  Cette fonction système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est fournie pour des raisons de compatibilité descendante. Nous vous recommandons d’utiliser [sys.dm_io_cluster_valid_path_names &#40;Transact-SQL&#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-io-cluster-valid-path-names-transact-sql.md) à la place.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
fn_servershareddrives()  
```  
  
## <a name="tables-returned"></a>Tables retournées  
 Si le serveur actuel est un serveur en cluster, **fn_servershareddrives** retourne le nom du lecteur des lecteurs partagés.  
  
 Si l’instance de serveur actuelle n’est pas un serveur en cluster, **fn_servershareddrives** retourne un ensemble de lignes vide.  
  
## <a name="remarks"></a>Notes  
 `fn_servershareddrives` renvoie la liste des lecteurs partagés qui sont utilisés par le serveur cluster. Ces lecteurs appartiennent au même groupe de cluster en tant que le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ressource. De plus, la ressource [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dépend de ces lecteurs.  
  
 Cette fonction permet d'identifier les lecteurs disponibles pour les utilisateurs.  
  
## <a name="permissions"></a>Permissions  
 L'utilisateur doit disposer de l'autorisation VIEW SERVER STATE pour l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant utilise `fn_servershareddrives` pour effectuer une requête sur une instance de serveur cluster :  
  
```  
SELECT * FROM fn_servershareddrives();  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 DriveName  
  
 -------\-  
  
 m  
  
 n  
  
## <a name="see-also"></a>Voir aussi  
 [Sys.dm_io_cluster_valid_path_names &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-io-cluster-valid-path-names-transact-sql.md)   
 [sys.dm_io_cluster_shared_drives &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-io-cluster-shared-drives-transact-sql.md)   
 [sys.fn_virtualservernodes &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-virtualservernodes-transact-sql.md)  
  
  
