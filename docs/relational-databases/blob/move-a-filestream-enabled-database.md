---
title: Déplacer une base de données compatible FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], moving a FILESTREAM-enabled database
ms.assetid: dd4d270d-9283-431a-aa6b-e571fced1893
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 9343cbe31b5d77cf9a91a513d61c6aca2d21408a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47693457"
---
# <a name="move-a-filestream-enabled-database"></a>Déplacer une base de données compatible FILESTREAM
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Cette rubrique montre comment déplacer une base de données compatible FILESTREAM.  
  
> [!NOTE]  
>  Les exemples de cette rubrique exigent la base de données Archive créée dans [Créer une base de données compatible FILESTREAM](../../relational-databases/blob/create-a-filestream-enabled-database.md).  
  
### <a name="to-move-a-filestream-enabled-database"></a>Pour déplacer une base de données compatible FILESTREAM  
  
1.  Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez sur **Nouvelle requête** pour ouvrir l’Éditeur de requête.  
  
2.  Copiez le script [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant dans l’Éditeur de requête, puis cliquez sur **Exécuter**. Ce script affiche l'emplacement des fichiers de base de données physiques utilisés par la base de données FILESTREAM.  
  
    ```sql  
    USE Archive  
    GO  
    SELECT type_desc, name, physical_name from sys.database_files  
    ```  
  
3.  Copiez le script [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant dans l’Éditeur de requête, puis cliquez sur **Exécuter**. Ce code met la base de données `Archive` hors connexion.  
  
    ```sql  
    USE master  
    EXEC sp_detach_db Archive  
    GO  
    ```  
  
4.  Créez le dossier `C:\moved_location`dans lequel vous allez placer les fichiers et les dossiers listés à l'étape 2.  
  
5.  Copiez le script [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant dans l’Éditeur de requête, puis cliquez sur **Exécuter**. Ce script met la base de données `Archive` en ligne.  
  
    ```sql  
    CREATE DATABASE Archive ON  
    PRIMARY ( NAME = Arch1,  
        FILENAME = 'c:\moved_location\archdat1.mdf'),  
    FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
        FILENAME = 'c:\moved_location\filestream1')  
    LOG ON  ( NAME = Archlog1,  
        FILENAME = 'c:\moved_location\archlog1.ldf')  
    FOR ATTACH  
    GO  
    ```  
  
## <a name="see-also"></a> Voir aussi  
 [sp_detach_db &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-detach-db-transact-sql.md)  
  
  
