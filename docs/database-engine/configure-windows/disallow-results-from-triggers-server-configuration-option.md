---
title: disallow results from triggers (option de configuration de serveur) | Microsoft Docs
ms.custom: 
ms.date: 03/02/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- triggers [SQL Server], result sets
- result sets [SQL Server], triggers
- disallow results from triggers option
ms.assetid: 47149073-307d-47a5-b7d2-66a737d3231d
caps.latest.revision: 30
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: ffca61b6490783e1721b6d66a01549b343e0422a
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="disallow-results-from-triggers-server-configuration-option"></a>disallow results from triggers (option de configuration de serveur)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  L’option **disallow results from triggers** permet de spécifier si les déclencheurs doivent ou non retourner des ensembles de résultats. Les déclencheurs qui renvoient des jeux de résultats peuvent provoquer un comportement inattendu des applications qui ne sont pas conçues pour interagir avec eux.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] Nous vous conseillons de définir cette valeur sur 1.  
  
 L’option **disallow results from triggers** est activée quand la valeur 1 lui est attribuée. La valeur par défaut de cette option est 0 (désactivé). Si cette option est définie sur 1 (activé), toute tentative de la part d'un déclencheur de renvoyer un ensemble de résultats échoue, tandis l'utilisateur obtient le message d'erreur suivant :  
  
 « Msg 524, Niveau 16, État 1, Procédure \<nom_procédure>, Ligne \<n°_ligne>  
  
 « Un déclencheur a retourné un ensemble de résultats et l'option de serveur « disallow_results_from_triggers » a la valeur TRUE. »  
  
 L’option **disallow results from triggers** s’applique au niveau de l’instance [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et détermine le comportement de tous les déclencheurs qui existent au sein de l’instance.  
  
 L’option **disallow results from triggers** est une option avancée. Si vous utilisez la procédure stockée système **sp_configure** pour changer sa valeur, vous ne pouvez modifier l’option disallow results from triggers que si l’option **show advanced options** a la valeur 1. Le paramètre prend effet immédiatement (sans redémarrage du serveur).  
  
## <a name="see-also"></a>Voir aussi  
 [RECONFIGURE &#40;Transact-SQL&#41;](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [Options de configuration de serveur &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)  
  
  
