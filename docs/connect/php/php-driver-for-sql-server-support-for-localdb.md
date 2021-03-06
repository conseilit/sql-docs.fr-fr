---
title: Prise en charge de la base de données locale | Microsoft Docs
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: d315ad6a-0d50-4093-80c2-2f11217237c2
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2009d434b5faa3bf9cc63d5f9005ebe31be14d2a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47728527"
---
# <a name="support-for-localdb"></a>Prise en charge de la base de données locale

[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

LocalDB est une version légère de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est disponible depuis [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]. Cette rubrique explique comment se connecter à une base de données dans une instance LocalDB.

## <a name="remarks"></a>Notes 

Pour plus d’informations sur la base de données locale, y compris comment installer LocalDB et configurer votre instance de base de données locale, consultez le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rubrique de la documentation en ligne sur [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Express LocalDB.

En bref, base de données locale vous permet de :

-   Utiliser **sqllocaldb.exe i** pour déterminer le nom de l'instance par défaut.

-   Utiliser le mot clé de chaîne de connexion **AttachDBFilename** pour spécifier le fichier de base de données auquel le serveur doit se rattacher. Lorsque vous utilisez **AttachDBFilename**, si vous ne spécifiez pas le nom de la base de données avec le mot clé de chaîne de connexion **Database** , la base de données est supprimée de l'instance LocalDB lorsque l'application se ferme.

-   Spécifiez une instance LocalDB dans votre chaîne de connexion. Par exemple, Voici un exemple de chaîne de connexion SQLSRV :

    ```php
    $conn = sqlsrv_connect( '(localdb)\\v11.0',
        array( 'Database'=>'myData'));

    $conn = sqlsrv_connect( '(localdb)\\v11.0',
        array('AttachDBFileName'=>'c:\\myData.MDF','Database'=>'myData'));

    $conn = sqlsrv_connect( '(localdb)\\v11.0',
        array('AttachDBFileName'=>'c:\\myData.MDF'));
    ```

    Voici un exemple de chaîne de connexion PDO_SQLSRV :  

    ```php
    $conn = new PDO( 'sqlsrv:server=(localdb)\\v11.0;'
        . 'Database=myData', NULL, NULL);

    $conn = new PDO( 'sqlsrv:server=(localdb)\\v11.0;'
        . 'AttachDBFileName=c:\\myData.MDF;Database=myData ',
        NULL, NULL);

    $conn = new PDO( 'sqlsrv:server=(localdb)\\v11.0;'
        . 'AttachDBFileName=c:\\myData.MDF', NULL, NULL);  
    ```

Si nécessaire, vous pouvez créer une instance LocalDB avec sqllocaldb.exe. Vous pouvez également utiliser sqlcmd.exe pour ajouter et modifier des bases de données dans une instance LocalDB. Par exemple, `sqlcmd -S (localdb)\v11.0`. (Lors de l’exécution dans IIS, vous avez besoin pour s’exécuter sous le compte approprié pour obtenir les mêmes résultats que lorsque vous exécutez en ligne de commande ; consultez [à l’aide de LocalDB avec IIS complet, partie 2 : la propriété d’Instance](http://blogs.msdn.com/b/sqlexpress/archive/2011/12/09/using-localdb-with-full-iis-part-2-instance-ownership.aspx) pour plus d’informations.)

Chaînes de connexion exemple à l’aide du pilote SQLSRV qui se connectent à une base de données dans une base de données locale d’une instance appelée myInstance nommée sont les suivantes :

```php
$conn = sqlsrv_connect( '(localdb)\\myInstance',
    array( 'Database'=>'myData'));
```

Chaînes de connexion exemple l’utilisation du pilote PDO_SQLSRV qui se connectent à une base de données dans une base de données locale d’une instance appelée myInstance nommée sont les suivantes :  
  
```php
$conn = new PDO( 'sqlsrv:server=(localdb)\\myInstance;'
    . 'database=myData', NULL, NULL);
```

Pour obtenir des instructions sur l’installation de base de données locale, consultez le [LocalDB documentation](../../database-engine/configure-windows/sql-server-2016-express-localdb.md). Si vous utilisez sqlcmd.exe pour modifier des données dans votre instance de base de données locale, vous devez le [utilitaire sqlcmd](../../tools/sqlcmd-utility.md).

## <a name="see-also"></a> Voir aussi

[Connexion au serveur](../../connect/php/connecting-to-the-server.md)
