---
title: Afficher les propriétés de clés étrangères | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], attributes
- displaying foreign keys attributes
- viewing foreign keys attributes
ms.assetid: b0e57cb7-9b26-4b96-b76a-1f59f5f498c5
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 82f2809c1676edf002aa4b6bd7d03bef19ebe51a
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48157749"
---
# <a name="view-foreign-key-properties"></a>Afficher les propriétés de clés étrangères
  Vous pouvez consulter les attributs de clé étrangère d'une relation dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **Dans cette rubrique**  
  
-   **Avant de commencer :**  
  
     [Sécurité](#Security)  
  
-   **Pour consulter les attributs de clé étrangère d'une table spécifique, utilisez :**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Avant de commencer  
  
###  <a name="Security"></a> Sécurité  
  
####  <a name="Permissions"></a> Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).  
  
##  <a name="SSMSProcedure"></a> Utilisation de SQL Server Management Studio  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a>Pour consulter les attributs de clé étrangère d'une relation dans une table spécifique  
  
1.  Ouvrez le Concepteur de tables pour la table contenant la clé étrangère que vous souhaitez afficher, cliquez avec le bouton droit dans le Concepteur de tables puis, dans le menu contextuel, choisissez **Relations** .  
  
2.  Dans la boîte de dialogue **Relations de clé étrangère** , sélectionnez la relation possédant les propriétés à afficher.  
  
 Si les colonnes clés étrangères sont en relation avec une clé primaire, les colonnes clés primaires sont identifiées dans le **Concepteur de tables** par un symbole de clé primaire dans le sélecteur de ligne.  
  
##  <a name="TsqlProcedure"></a> Utilisation de Transact-SQL  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a>Pour consulter les attributs de clé étrangère d'une relation dans une table spécifique  
  
1.  Dans l' **Explorateur d'objets**, connectez-vous à une instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.  
  
3.  Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**. L'exemple retourne toutes les clés étrangères et leurs propriétés pour la table `HumanResources.Employee` dans l'exemple de base de données.  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT   
        f.name AS foreign_key_name  
       ,OBJECT_NAME(f.parent_object_id) AS table_name  
       ,COL_NAME(fc.parent_object_id, fc.parent_column_id) AS constraint_column_name  
       ,OBJECT_NAME (f.referenced_object_id) AS referenced_object  
       ,COL_NAME(fc.referenced_object_id, fc.referenced_column_id) AS referenced_column_name  
       ,is_disabled  
       ,delete_referential_action_desc  
       ,update_referential_action_desc  
    FROM sys.foreign_keys AS f  
    INNER JOIN sys.foreign_key_columns AS fc   
       ON f.object_id = fc.constraint_object_id   
    WHERE f.parent_object_id = OBJECT_ID('HumanResources.Employee');  
    ```  
  
 Pour plus d’informations, consultez [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) et [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).  
  
###  <a name="TsqlExample"></a>  
