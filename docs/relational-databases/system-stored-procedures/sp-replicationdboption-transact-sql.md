---
title: sp_replicationdboption (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- replication
ms.topic: language-reference
f1_keywords:
- sp_replicationdboption_TSQL
- sp_replicationdboption
helpviewer_keywords:
- sp_replicationdboption
ms.assetid: d021864e-3f21-4d1a-89df-6c1086f753bf
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: be7d8869c2f1b1453eab4efcf3c6145b6dafea9d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47781681"
---
# <a name="spreplicationdboption-transact-sql"></a>sp_replicationdboption (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Définit une option de base de données de réplication pour la base de données spécifiée. Cette procédure stockée est exécutée sur n'importe quelle base de données de l'abonné au niveau du serveur de publication ou de l'Abonné.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_replicationdboption [ @dbname= ] 'db_name'   
        , [ @optname= ] 'optname'   
        , [ @value= ] 'value'   
    [ , [ @ignore_distributor= ] ignore_distributor ]  
    [ , [ @from_scripting = ] from_scripting ]  
```  
  
## <a name="arguments"></a>Arguments  
 [**@dbname=**] **'***dbname***'**  
 Base de données pour laquelle l'option de base de données de réplication doit être définie. *db_name* est **sysname**, sans valeur par défaut.  
  
 [**@optname=**] **'***optname***'**  
 Option de base de données de réplication à activer ou à désactiver. *optname* est **sysname**, et peut prendre l’une des valeurs suivantes.  
  
|Valeur|Description|  
|-----------|-----------------|  
|**publication de fusion**|La base de données peut être utilisée pour les publications de fusion.|  
|**publier**|La base de données peut être utilisée pour les autres types de publications.|  
|**s’abonner**|La base de données est une base de données d'abonnement.|  
|**synchroniser avec la sauvegarde**|La base de données est activée pour la sauvegarde coordonnée. Pour plus d’informations, consultez [activer les sauvegardes coordonnées pour la réplication transactionnelle &#40;programmation Transact-SQL de la réplication&#41;](../../relational-databases/replication/administration/enable-coordinated-backups-for-transactional-replication.md).|  
  
 [  **@value=**] **'***valeur***'**  
 Indique si l'option de base de données de réplication doit être activée ou désactivée. *valeur* est **sysname**et peut être **true** ou **false**. Lorsque cette valeur est **false** et *optname* est **publication de fusion**, les abonnements à la base de données publiée de fusion sont également supprimés.  
  
 [  **@ignore_distributor=**] *ignore_distributor*  
 Indique si cette procédure stockée est exécutée sans se connecter au serveur de distribution. *ignore_distributor* est **bits**, avec une valeur par défaut **0**, ce qui signifie que le serveur de distribution doit être connecté à et mis à jour avec le nouvel état de la base de données de publication. La valeur **1** doit être spécifié uniquement si le serveur de distribution n’est pas accessible et **sp_replicationdboption** est utilisée pour désactiver la publication.  
  
 [  **@from_scripting=**] *from_scripting*  
 [!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="remarks"></a>Notes  
 **sp_replicationdboption** est utilisé dans la réplication de capture instantanée, la réplication transactionnelle et la réplication de fusion.  
  
 Cette procédure crée ou supprime des tables système de réplication spécifiques, des comptes de sécurité, etc., en fonction des options choisies. Définit la catégorie correspondante bit dans le **master.sysdatabases** (table système) et crée les tables système nécessaires.  
  
 Pour désactiver la publication, la base de données de publication doit être en ligne. Si un instantané existe pour la base de données de publication, elle doit être supprimée pour pouvoir désactiver la publication. Un instantané de base de données est une copie en lecture seule hors ligne d'une base de données et n'est pas lié à un instantané de réplication. Pour plus d’informations, consultez [Instantanés de base de données &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).  
  
## <a name="permissions"></a>Permissions  
 Seuls les membres de la **sysadmin** du rôle serveur fixe peuvent exécuter **sp_replicationdboption**.  
  
## <a name="see-also"></a>Voir aussi  
 [Configurer la publication et la distribution](../../relational-databases/replication/configure-publishing-and-distribution.md)   
 [Create a Publication](../../relational-databases/replication/publish/create-a-publication.md)   
 [Supprimer une Publication](../../relational-databases/replication/publish/delete-a-publication.md)   
 [Désactiver la publication et la distribution](../../relational-databases/replication/disable-publishing-and-distribution.md)   
 [Sys.sysdatabases &#40;Transact-SQL&#41;](../../relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql.md)   
 [Procédures stockées de réplication &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
