---
title: Métadonnées du jeu à l’aide de résultat | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 5e37529a-30db-48c8-b90a-ae9657d0f6b0
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0e0d42d02d6c288b1d82df6925219ce9787f39b0
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47728667"
---
# <a name="using-result-set-metadata"></a>Utilisation des métadonnées du jeu de résultats

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

Pour pouvoir interroger un jeu de résultats afin d’obtenir des informations sur les colonnes qu’il contient, le [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] implémente la classe [SQLServerResultSetMetaData](../../connect/jdbc/reference/sqlserverresultsetmetadata-class.md). Cette classe contient plusieurs méthodes retournant des informations sous la forme d'une valeur unique.

Pour créer un objet SQLServerResultSetMetaData, vous pouvez utiliser la [getMetaData](../../connect/jdbc/reference/getmetadata-method-sqlserverresultset.md) méthode de la [SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md) classe.

Dans l’exemple suivant, une connexion ouverte à la [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)] base de données est transmise à la fonction, la méthode getMetaData de la classe SQLServerResultSet est utilisée pour retourner un objet SQLServerResultSetMetaData et puis diverses méthodes de la Objet SQLServerResultSetMetaData servent à afficher des informations sur le nom et type de données des colonnes contenues dans le jeu de résultats.

[!code[JDBC#UsingResultSetMetaData1](../../connect/jdbc/codesnippet/Java/using-result-set-metadata_1.java)]

## <a name="see-also"></a> Voir aussi

[Gestion des métadonnées avec le pilote JDBC](../../connect/jdbc/handling-metadata-with-the-jdbc-driver.md)
