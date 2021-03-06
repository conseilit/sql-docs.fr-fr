---
title: sysmail_update_profile_sp (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysmail_update_profile_sp
- sysmail_update_profile_sp_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysmail_update_profile_sp
ms.assetid: eaedf7ce-a8d5-4ab9-99e0-d77d5be19e90
author: VanMSFT
ms.author: vanto
manager: craigg
ms.openlocfilehash: c979104c30ec9b134f2d73acb2d85ecd22490371
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47854203"
---
# <a name="sysmailupdateprofilesp-transact-sql"></a>sysmail_update_profile_sp (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Modifie la description ou le nom d'un profil de messagerie de base de données.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sysmail_update_profile_sp [ [ @profile_id = ] profile_id , ] [ [ @profile_name = ] 'profile_name' , ]  
    [ [ @description = ] 'description' ]  
```  
  
## <a name="arguments"></a>Arguments  
 [ **@profile_id** =] *profile_id*  
 Id de profil à mettre à jour. *profile_id* est **int**, avec NULL comme valeur par défaut. Au moins une des *profile_id* ou *profile_name* doit être spécifié. Si les deux arguments sont indiqués, la procédure modifie le nom du profil.  
  
 [ **@profile_name** =] **'***profile_name***'**  
 Nom du profil à mettre à jour ou nouveau nom pour le profil. *nom_profil* est **sysname**, avec NULL comme valeur par défaut. Au moins une des *profile_id* ou *profile_name* doit être spécifié. Si les deux arguments sont indiqués, la procédure modifie le nom du profil.  
  
 [ **@description** =] **'***description***'**  
 Nouvelle description du profil. *Description* est **nvarchar (256)**, avec NULL comme valeur par défaut.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="remarks"></a>Notes  
 Lorsque l'identificateur et le nom du profil sont tous les deux spécifiés, la procédure remplace le nom du profil par celui qui est fourni et met à jour la description. Lorsqu'un seul de ces arguments est indiqué, la procédure met simplement à jour la description du profil.  
  
 La procédure stockée **sysmail_update_profile_sp** est dans le **msdb** de base de données et est détenue par le **dbo** schéma. La procédure doit être exécutée avec un nom en trois parties si la base de données actuelle n’est pas **msdb**.  
  
## <a name="permissions"></a>Permissions  
 Autorisations d’exécution de cette procédure reviennent par défaut aux membres de la **sysadmin** rôle serveur fixe.  
  
## <a name="examples"></a>Exemples  
 **A. Modification de la description d’un profil**  
  
 L’exemple suivant modifie la description pour le profil nommé `AdventureWorks Administrator` dans le **msdb** base de données.  
  
```  
EXECUTE msdb.dbo.sysmail_update_profile_sp  
    @profile_name = 'AdventureWorks Administrator'  
    ,@description = 'Administrative mail profile.';  
```  
  
 **B. Modification du nom et la description d’un profil**  
  
 L'exemple suivant modifie le nom et la description du profil à l'aide de l'ID de profil `750`.  
  
```  
EXECUTE msdb.dbo.sysmail_update_profile_sp  
    @profile_id = 750  
    ,@profile_name = 'Operator'  
    ,@description = 'Profile to send alert e-mail to operators.';  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Messagerie de base de données](../../relational-databases/database-mail/database-mail.md)   
 [Objets de Configuration de messagerie de base de données](../../relational-databases/database-mail/database-mail-configuration-objects.md)   
 [Créer un compte de messagerie de base de données](../../relational-databases/database-mail/create-a-database-mail-account.md)   
 [Procédures stockées de messagerie de base de données &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)  
  
  
