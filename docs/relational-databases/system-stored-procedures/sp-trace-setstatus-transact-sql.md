---
title: sp_trace_setstatus (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_trace_setstatus_TSQL
- sp_trace_setstatus
dev_langs:
- TSQL
helpviewer_keywords:
- sp_trace_setstatus
ms.assetid: 29e7a7d7-b9c1-414a-968a-fc247769750d
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 2a350cf6b7f37aca830f4c74c23ce214f86376f6
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47702387"
---
# <a name="sptracesetstatus-transact-sql"></a>sp_trace_setstatus (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Modifie l'état actuel de la trace spécifiée.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Utilisez plutôt des événements étendus.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_trace_setstatus [ @traceid = ] trace_id , [ @status = ] status  
```  
  
## <a name="arguments"></a>Arguments  
 [  **@traceid=** ] *trace_id*  
 ID de la trace à modifier. *trace_id* est **int**, sans valeur par défaut. L’utilisateur emploie cette *trace_id* valeur à identifier, modifier et contrôler la trace. Pour plus d’informations sur la récupération de la *trace_id*, consultez [sys.fn_trace_getinfo &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql.md).  
  
 [  **@status=** ] *état*  
 Indique l'action à implémenter sur la trace. *état* est **int**, sans valeur par défaut.  
  
 Le tableau ci-après répertorie les états qui peuvent être spécifiés.  
  
|État|Description|  
|------------|-----------------|  
|**0**|Arrête la trace spécifiée.|  
|**1**|Démarre la trace spécifiée.|  
|**2**|Ferme la trace spécifiée et supprime sa définition du serveur.|  
  
> [!NOTE]  
>  Une trace doit d'abord être arrêtée avant d'être fermée. de la même façon qu'elle doit d'abord être arrêtée et fermée avant de pouvoir être consultée.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 Le tableau suivant décrit les valeurs de code que les utilisateurs peuvent recevoir à la fin de l'exécution de la procédure stockée.  
  
|Code de retour|Description|  
|-----------------|-----------------|  
|**0**|Aucune erreur.|  
|**1**|Erreur inconnue.|  
|**8**|L'état spécifié n'est pas valide.|  
|**9**|Le descripteur de trace spécifié n'est pas valide.|  
|**13**|Mémoire insuffisante. Renvoyé lorsqu'il n'y a pas assez de mémoire pour exécuter l'action spécifiée.|  
  
 Si la trace est déjà dans l’état spécifié, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retournera **0**.  
  
## <a name="remarks"></a>Notes  
 Paramètres de Trace de SQL toutes les procédures stockées (**sp_trace_xx**) sont strictement typés. Si ces paramètres ne sont pas appelés avec des types de données appropriés pour les paramètres d'entrée tels qu'ils sont spécifiés dans la description de l'argument, la procédure stockée renvoie une erreur.  
  
 Pour obtenir un exemple d’utilisation de procédures stockées de trace, consultez [Créer une trace &#40;Transact-SQL&#41;](../../relational-databases/sql-trace/create-a-trace-transact-sql.md).  
  
## <a name="permissions"></a>Permissions  
 L'utilisateur doit disposer de l'autorisation ALTER TRACE.  
  
## <a name="see-also"></a>Voir aussi  
 [sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-trace-geteventinfo-transact-sql.md)   
 [sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql.md)   
 [sp_trace_generateevent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql.md)   
 [sp_trace_setevent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)   
 [sp_trace_setfilter &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql.md)   
 [Trace SQL](../../relational-databases/sql-trace/sql-trace.md)  
  
  
