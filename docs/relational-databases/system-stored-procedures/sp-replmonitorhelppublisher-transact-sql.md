---
title: sp_replmonitorhelppublisher (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- replication
ms.topic: language-reference
f1_keywords:
- sp_replmonitorhelppublisher_TSQL
- sp_replmonitorhelppublisher
helpviewer_keywords:
- sp_replmonitorhelppublisher
ms.assetid: 171501fe-4b74-4647-96c3-7691c777e01b
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 43d00ff95085627dfc1821b7b0cb83a2635eecda
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47828173"
---
# <a name="spreplmonitorhelppublisher-transact-sql"></a>sp_replmonitorhelppublisher (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne les informations sur l'état actuel d'un ou plusieurs serveurs de publication associés à un serveur de distribution. Cette procédure stockée, utilisée pour surveiller la réplication, est exécutée sur la base de données du serveur de distribution.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_replmonitorhelppublisher [ [ @publisher = ] 'publisher' ]  
    [ , [ @refreshpolicy = ] refreshpolicy ]  
```  
  
## <a name="arguments"></a>Arguments  
 [ **@publisher** =] **'***publisher***'**  
 Nom du serveur de publication dont l'état fait l'objet d'une surveillance. *serveur de publication* est **sysname**, avec NULL comme valeur par défaut. Si sa valeur est NULL, des informations sont retournées sur tous les serveurs de publication qui utilisent le serveur de distribution.  
  
 [  **@refreshpolicy=** ] *refreshpolicy*  
 À usage interne uniquement  
  
## <a name="result-sets"></a>Jeux de résultats  
  
|Nom de colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|**publisher** (serveur de publication)|**sysname**|Nom d'un serveur de publication.|  
|**distribution_db**|**sysname**|Nom de la base de données de distribution utilisée par un serveur de publication donné.|  
|**status**|**Int**|État maximal de tous les agents de réplication associés aux publications sur ce serveur de publication. Il peut avoir l'une des valeurs suivantes.<br /><br /> **1** = démarré<br /><br /> **2** = a réussi<br /><br /> **3** = en cours<br /><br /> **4** = inactif<br /><br /> **5** = reprise<br /><br /> **6** = Échec|  
|**avertissement**|**Int**|Avertissement de seuil maximal généré par un abonnement appartenant à une publication sur ce serveur de publication, qui peut représenter le résultat d'une opération OR logique d'une ou plusieurs des valeurs suivantes.<br /><br /> **1** = expiration – un abonnement à une publication transactionnelle n’a pas été synchronisé dans le seuil de période de rétention.<br /><br /> **2** = latency - le temps nécessaire pour répliquer des données à partir d’un serveur de publication transactionnelle à l’abonné dépasse le seuil, en secondes.<br /><br /> **4** = mergeexpiration – un abonnement à une publication de fusion n’a pas été synchronisé dans le seuil de période de rétention.<br /><br /> **8** = mergefastrunduration - le temps nécessaire pour effectuer la synchronisation d’un abonnement de fusion dépasse le seuil, en secondes, via une connexion réseau rapide.<br /><br /> **16** = mergeslowrunduration - le temps nécessaire pour effectuer la synchronisation d’un abonnement de fusion dépasse le seuil, en secondes, via une connexion réseau lente ou accès à distance.<br /><br /> **32** = mergefastrunspeed – la vitesse de transmission de lignes pendant la synchronisation d’un abonnement de fusion a échoué à maintenir le taux du seuil, en lignes par seconde, via une connexion réseau rapide.<br /><br /> **64** = mergeslowrunspeed – la vitesse de transmission de lignes pendant la synchronisation d’un abonnement de fusion a échoué à maintenir le taux du seuil, en lignes par seconde, via une connexion réseau lente ou accès à distance.|  
|**PublicationCount**|**Int**|Nombre de publications appartenant au serveur de publication.|  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="remarks"></a>Notes  
 **sp_replmonitorhelppublisher** est utilisé avec tous les types de réplication.  
  
## <a name="permissions"></a>Permissions  
 Seuls les membres de la **sysadmin** rôle serveur fixe sur le serveur de distribution ou les membres de la **db_owner** ou **replmonitor** des rôles de base de données fixe dans la base de données de distribution peuvent Exécutez **sp_replmonitorhelppublisher**.  
  
## <a name="see-also"></a>Voir aussi  
 [Surveiller la réplication par programmation](../../relational-databases/replication/monitor/programmatically-monitor-replication.md)  
  
  
