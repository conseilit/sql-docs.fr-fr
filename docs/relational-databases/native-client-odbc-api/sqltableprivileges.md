---
title: SQLTablePrivileges | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLTablePrivileges function
ms.assetid: 8cce22d5-28b1-4b50-a5bc-1de03e0ffd6b
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 99626265a59a5e31874610f7abbb3864c5e1fa79
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47708729"
---
# <a name="sqltableprivileges"></a>SQLTablePrivileges
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  **SQLTablePrivileges** peut être exécutée sur un curseur statique. Une tentative d’exécution **SQLTablePrivileges** sur un actualisable (commandé par keyset ou dynamique) retourne SQL_SUCCESS_WITH_INFO pour indiquer que le type de curseur a été modifié.  
  
 Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client prend en charge des informations de rapport pour les tables des serveurs liés en acceptant un nom en deux parties pour le *CatalogName* paramètre : *nom_serveur_lié.Nom_Catalogue*.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonction SQLTablePrivileges] (http://go.microsoft.com/fwlink/?LinkId=59373\)   
 [Détails de l’implémentation d’API ODBC](~/relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
