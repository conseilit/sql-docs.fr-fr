---
title: Modifier des statistiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], modifying
- modifying statistics
ms.assetid: b06299ca-ed52-411a-b245-45eac4628c99
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 0532f2b9ab931eccda5403501a6fe74b3603525c
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48165839"
---
# <a name="modify-statistics"></a>Modifier des statistiques
  Vous pouvez modifier des statistiques existantes dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **Dans cette rubrique**  
  
-   **Avant de commencer :**  
  
     [Sécurité](#Security)  
  
-   **Pour modifier des statistiques, utilisez :**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Avant de commencer  
  
###  <a name="Security"></a> Sécurité  
  
####  <a name="Permissions"></a> Permissions  
 Exigences :  
  
-   L'utilisateur doit disposer de l'autorisation ALTER sur la table ou la vue.  
  
-   L’utilisateur doit être le propriétaire de la table ou de la vue indexée ou être membre d’un des rôles suivants : rôle serveur fixe **sysadmin** , rôle de base de données fixe **db_owner** ou rôle de base de données fixe **db_ddladmin** .  
  
##  <a name="SSMSProcedure"></a> Utilisation de SQL Server Management Studio  
  
#### <a name="to-modify-statistics"></a>Pour modifier des statistiques  
  
1.  Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer la base de données dans laquelle vous souhaitez modifier une statistique.  
  
2.  Cliquez sur le signe plus (+) pour développer le dossier **Tables** .  
  
3.  Cliquez sur le signe plus (+) pour développer la table dans laquelle vous souhaitez modifier une statistique.  
  
4.  Cliquez sur le signe plus (+) pour développer le dossier **Statistiques** .  
  
5.  Cliquez avec le bouton droit sur l’objet de statistiques à modifier et sélectionnez **Propriétés**.  
  
6.  Dans la boîte de dialogue **Propriétés des statistiques** *statistics_name* dialog box, on the **General** page, click **Add**, **Remove**, **Move Up**, or **Move Down**, or any combination, to alter the properties of the statistics. Gardez à l'esprit que l'emplacement d'une colonne dans la grille **Colonnes de statistiques** peut avoir une incidence notable sur l'utilité des statistiques.  
  
7.  Cliquez sur **OK**.  
  
##  <a name="TsqlProcedure"></a> Utilisation de Transact-SQL  
 **Pour modifier des statistiques**  
  
 Cette tâche ne peut pas être effectuée à l'aide d'instructions Transact-SQL. Pour modifier des statistiques à l'aide de Transact-SQL, vous devez d'abord supprimer les statistiques existantes, puis les recréer avec les nouveaux attributs.  
  
 Pour plus d’informations, consultez [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) et [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).  
  
  
