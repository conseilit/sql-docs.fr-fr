---
title: Afficher un journal d’audit SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: security
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- audits [SQL Server], viewing logs
- viewing audit logs
- logs [SQL Server], audit
ms.assetid: e8feaca0-7852-422b-895a-319b965d8d9b
caps.latest.revision: 12
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: bb33f72c7b3f5f7af6d15004ce6377cbc8d6ffe8
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37219039"
---
# <a name="view-a-sql-server-audit-log"></a>Afficher un journal d'audit SQL Server
  Cette rubrique explique comment afficher un journal d'audit SQL Server dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].  
  
 **Dans cette rubrique**  
  
-   **Avant de commencer :**  
  
     [Sécurité](#Security)  
  
-   **Pour afficher un journal d'audit SQL Server, utilisez :**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Avant de commencer  
  
###  <a name="Security"></a> Sécurité  
  
####  <a name="Permissions"></a> Permissions  
 Nécessite l’autorisation `CONTROL SERVER`.  
  
##  <a name="SSMSProcedure"></a> Utilisation de SQL Server Management Studio  
  
#### <a name="to-view-a-sql-server-audit-log"></a>Pour afficher un journal d'audit SQL Server  
  
1.  Dans l'Explorateur d'objets, développez le dossier **Sécurité** .  
  
2.  Développez le dossier **Audits** .  
  
3.  Cliquez avec le bouton droit sur le journal d’audit que vous souhaitez afficher et sélectionnez **Afficher les journaux d’audit**. Cette opération ouvre la boîte de dialogue **Visionneuse du fichier journal –***nom_serveur*. Pour plus d'informations, consultez [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).  
  
4.  Lorsque vous avez terminé, cliquez sur **Fermer**.  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] recommande d'afficher le journal d'audit à l'aide de la visionneuse du fichier journal. Toutefois, si vous créez un système de surveillance automatisé, les informations contenues dans le fichier d’audit peuvent être lues directement à l’aide de la fonction [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql). Si le fichier est lu directement, les données sont retournées dans un format légèrement différent (non traité). Pour plus d'informations, consultez **sys.fn_get_audit_file** .  
  
## <a name="see-also"></a>Voir aussi  
 [SQL Server Audit &#40moteur de base de données&#41;](sql-server-audit-database-engine.md)   
 [Écrire des événements d'audit SQL Server dans le journal de sécurité](write-sql-server-audit-events-to-the-security-log.md)  
  
  