---
title: 'Comment : se connecter sur un Port spécifié | Microsoft Docs'
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- connecting to the server, specifying a port
ms.assetid: 65a154d1-375c-439b-a653-7815c9d70ff3
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b4d19077a4a0b676875a9b82acf529cc8720f31f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47680018"
---
# <a name="how-to-connect-on-a-specified-port"></a>Procédure : se connecter sur un port spécifié
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Cette rubrique explique comment se connecter à SQL Server sur un port spécifié avec le [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
### <a name="to-connect-on-a-specified-port"></a>Pour se connecter sur un port spécifié  
  
1.  Vérifiez le port sur lequel le serveur est configuré pour accepter les connexions. Pour plus d’informations sur la configuration d’un serveur pour qu’il accepte les connexions sur un port spécifique, consultez [Guide pratique pour configurer un serveur pour écouter un port TCP spécifique (Gestionnaire de configuration SQL Server)](../../database-engine/configure-windows/configure-a-server-to-listen-on-a-specific-tcp-port.md).  
  
2.  Ajoutez le port souhaité au paramètre *$serverName* de la fonction [sqlsrv_connect](../../connect/php/sqlsrv-connect.md). Séparez le nom du serveur et le port avec une virgule. Par exemple, les lignes de code suivantes utilisent le pilote SQLSRV pour illustrer comment se connecter à un serveur nommé *myServer* sur le port 1521 :  
  
    ```  
    $serverName = "myServer, 1521";  
    sqlsrv_connect( $serverName );  
    ```  
  
    Les lignes de code suivantes utilisent le pilote PDOSQL_SRV pour montrer comment se connecter à un serveur nommé *myServer* sur le port 1521 :  
  
    ```  
    $serverName = "(local), 1521";  
    $database = "AdventureWorks";  
    $conn = new PDO( "sqlsrv:server=$serverName;Database=$database", "", "");  
    ```  
  
## <a name="see-also"></a> Voir aussi  
[Connexion au serveur](../../connect/php/connecting-to-the-server.md)

[Guide de programmation pour les pilotes Microsoft pour PHP pour SQL Server](../../connect/php/programming-guide-for-php-sql-driver.md)

[Mise en route avec les pilotes Microsoft pour PHP pour SQL Server](../../connect/php/getting-started-with-the-php-sql-driver.md)

[Informations de référence sur l’API du pilote SQLSRV](../../connect/php/sqlsrv-driver-api-reference.md)

[Informations de référence sur le pilote PDO_SQLSRV](../../connect/php/pdo-sqlsrv-driver-reference.md)  
  
