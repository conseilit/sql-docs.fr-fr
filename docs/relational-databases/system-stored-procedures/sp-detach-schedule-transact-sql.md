---
title: sp_detach_schedule (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_detach_schedule
- sp_detach_schedule_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_detach_schedule
ms.assetid: 9a1fc335-1bef-4638-a33a-771c54a5dd19
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 9a7ba1ee6a8fae84d0371c30758fcd2be1098b60
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47649267"
---
# <a name="spdetachschedule-transact-sql"></a>sp_detach_schedule (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Supprime l'association entre une planification et un travail.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_detach_schedule   
     { [ @job_id = ] job_id | [ @job_name = ] 'job_name' } ,  
       { [ @schedule_id = ] schedule_id | [ @schedule_name = ] 'schedule_name' } ,  
     [ @delete_unused_schedule = ] delete_unused_schedule   
```  
  
## <a name="arguments"></a>Arguments  
 [  **@job_id=** ] *job_id*  
 Numéro d'identification du travail à partir duquel supprimer la planification. *job_id* est **uniqueidentifier**, avec NULL comme valeur par défaut.  
  
 [  **@job_name=** ] **'***nom_travail***'**  
 Nom du travail à partir duquel supprimer la planification. *job_name* est **sysname**, avec NULL comme valeur par défaut.  
  
> [!NOTE]  
>  Soit *job_id* ou *nom_travail* doit être spécifié, mais ne peut pas être spécifiés.  
  
 [  **@schedule_id=** ] *id_de_la_planification*  
 Numéro d'identification de la planification à supprimer du travail. *id_de_la_planification* est **int**, avec NULL comme valeur par défaut.  
  
 [  **@schedule_name=** ] **'***nom_de_la_planification***'**  
 Nom de la planification à supprimer du travail. *nom_de_la_planification* est **sysname**, avec NULL comme valeur par défaut.  
  
> [!NOTE]  
>  Soit *id_de_la_planification* ou *nom_de_la_planification* doit être spécifié, mais ne peut pas être spécifiés.  
  
 [ **@delete_unused_schedule=** ] *delete_unused_schedule*  
 Spécifie si les planifications de travail inutilisées doivent être supprimées. *delete_unused_schedule* est **bits**, avec une valeur par défaut **0**, ce qui signifie que toutes les planifications sont conservées, même si aucun travail ne référencez-les. Si la valeur **1**, les planifications de travail inutilisées sont supprimées si aucun travail n’y fait référence.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="result-sets"></a>Jeux de résultats  
 None  
  
## <a name="permissions"></a>Permissions  
 Par défaut, les membres du rôle serveur fixe **sysadmin** peuvent exécuter cette procédure stockée. Les autres utilisateurs doivent disposer de l'un des rôles de base de données fixes suivants de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans la base de données **msdb** :  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 Notez que le propriétaire du travail peut joindre un travail à une planification et détacher un travail d'une planification sans être le propriétaire de la planification. Toutefois, une planification ne peut pas être supprimée si le détachement la conserve sans travaux, à moins que l'appelant ne soit le propriétaire de la planification.  
  
 Pour en savoir plus sur les autorisations de ces rôles, consultez [Rôles de base de données fixes de l'Agent SQL Server](../../ssms/agent/sql-server-agent-fixed-database-roles.md).  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] effectue une vérification pour déterminer si l'utilisateur est propriétaire de la planification. Seuls les membres de la **sysadmin** rôle serveur fixe peut dissocier les planifications des travaux appartenant à un autre utilisateur.  
  
## <a name="examples"></a>Exemples  
 L'exemple ci-dessous supprime l'association entre une planification `'NightlyJobs'` et un travail `'BackupDatabase'`.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_detach_schedule  
    @job_name = 'BackupDatabase',  
    @schedule_name = 'NightlyJobs' ;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [sp_add_schedule &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md)   
 [sp_attach_schedule &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql.md)   
 [sp_delete_schedule &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-delete-schedule-transact-sql.md)  
  
  
