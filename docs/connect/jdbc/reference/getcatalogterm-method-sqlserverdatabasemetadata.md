---
title: Méthode getCatalogTerm (SQLServerDatabaseMetaData) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDatabaseMetaData.getCatalogTerm
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 0aa5d372-16aa-4790-a8f6-f8b742798f8f
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 69559cff156c66d7ebbb0bf3675c3c3a455b2e0b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47811627"
---
# <a name="getcatalogterm-method-sqlserverdatabasemetadata"></a>méthode getCatalogTerm (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère le terme favori du fournisseur de base de données pour « catalog ».  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.lang.String getCatalogTerm()  
```  
  
## <a name="return-value"></a>Valeur retournée  
 Un **chaîne** qui contient le terme de catalogue.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes   
 Cette méthode getCatalogTerm est spécifiée par la méthode getCatalogTerm dans l’interface java.sql.DatabaseMetaData.  
  
 Lors de l’utilisation du [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] avec une base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], cette méthode retourne le terme « database ».  
  
## <a name="see-also"></a> Voir aussi  
 [SQLServerDatabaseMetaData, méthodes](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData, membres](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData, classe](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
