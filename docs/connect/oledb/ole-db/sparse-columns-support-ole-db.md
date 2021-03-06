---
title: Prise en charge des colonnes éparses (OLE DB) | Microsoft Docs
description: Prise en charge des colonnes éparses (OLE DB)
ms.custom: ''
ms.date: 06/12/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: oledb|ole-db
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: reference
author: pmasl
ms.author: pelopes
manager: craigg
ms.openlocfilehash: 1cfbd5bce17c658a7dff33bc7a590a22d525c193
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MTE75
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43018188"
---
# <a name="sparse-columns-support-ole-db"></a>Prise en charge des colonnes éparses (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  Cette rubrique fournit des informations sur le pilote OLE DB pour la prise en charge de SQL Server pour les colonnes éparses. Pour plus d’informations sur les colonnes éparses, consultez [prise en charge des colonnes éparses dans OLE DB Driver pour SQL Server](../../oledb/features/sparse-columns-support-in-oledb-driver-for-sql-server.md). [Afficher les métadonnées de colonne et de catalogue pour les colonnes éparses (OLE DB)](../../oledb/ole-db-how-to/display-column-and-catalog-metadata-for-sparse-columns-ole-db.md)  
  
## <a name="ole-db-statement-metadata"></a>Métadonnées d'instruction OLE DB  
 À partir de [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], une nouvelle valeur d'indicateur DBCOLUMNFLAGS, DBCOLUMNFLAGS_SS_ISCOLUMNSET, est disponible. Cette valeur doit être définie pour les colonnes qui sont des valeurs **column_set**. L’indicateur DBCOLUMNFLAGS peut être récupéré via la *dwFlags* paramètre de IColumnsInfo::GetColumnsInfo et la colonne DBCOLUMN_FLAGS de l’ensemble de lignes retourné par IColumnsRowset::GetColumnsRowset.  
  
## <a name="ole-db-catalog-metadata"></a>Métadonnées de catalogue OLE DB  
 Deux colonnes supplémentaires spécifiques à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ont été ajoutées à DBSCHEMA_COLUMNS.  
  
|Nom de colonne|Type de données|Valeur/commentaires|  
|-----------------|---------------|---------------------|  
|SS_IS_SPARSE|DBTYPE_BOOL|Si la colonne est une colonne éparse, la valeur est VARIANT_TRUE ; sinon, VARIANT_FALSE.|  
|SS_IS_COLUMN_SET|DBTYPE_BOOL|Si la colonne est la colonne **column_set** éparse, la valeur est VARIANT_TRUE ; sinon, VARIANT_FALSE.|  
  
 Deux ensembles de lignes de schéma supplémentaires ont également été ajoutés. Ces ensembles de lignes ont la même structure que DBSCHEMA_COLUMNS mais retournent un contenu différent. DBSCHEMA_COLUMNS_EXTENDED retourne toutes les colonnes, indépendamment de l’appartenance à **column_set**. DBSCHEMA_SPARSE_COLUMN_SET retourne seulement les colonnes qui sont membres du **column_set** épars.  
  
## <a name="ole-db-datatypecompatibility-behavior"></a>Comportement OLE DB de DataTypeCompatibility  
 Comportement avec **DataTypeCompatibility = 80** (dans la chaîne de connexion) est cohérent avec un [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] client, comme suit :  
  
-   Les nouveaux ensembles de lignes de schéma ne sont pas visibles, et il n'y a pas de lignes pour eux dans l'ensemble de lignes d'ensembles de lignes de schéma.  
  
-   Les nouvelles colonnes de l'ensemble de lignes COLUMNS ne sont pas visibles.  
  
-   DBCOLUMNFLAGS_SS_ISCOLUMNSET n’est pas défini pour les colonnes de **column_set**.  
  
-   DBCOMPUTEMODE_NOTCOMPUTED est défini pour les colonnes de **column_set**.  
  
## <a name="ole-db-support-for-sparse-columns"></a>Prise en charge OLE DB des colonnes éparses  
 Les interfaces OLE DB suivantes ont été modifiés dans OLE DB Driver pour SQL Server prendre en charge les colonnes éparses :  
  
|Type ou fonction membre|Description|  
|-----------------------------|-----------------|  
|IColumnsInfo::GetColumnsInfo|Une nouvelle valeur d’indicateur DBCOLUMNFLAGS, DBCOLUMNFLAGS_SS_ISCOLUMNSET, est définie pour les colonnes de **column_set** dans *dwFlags*.<br /><br /> DBCOLUMNFLAGS_WRITE est défini pour les colonnes de **column_set**.|  
|IColumsRowset::GetColumnsRowset|Une nouvelle valeur d’indicateur DBCOLUMNFLAGS, DBCOLUMNFLAGS_SS_ISCOLUMNSET, est définie pour les colonnes de **column_set** dans DBCOLUMN_FLAGS.<br /><br /> DBCOLUMN_COMPUTEMODE est défini sur DBCOMPUTEMODE_DYNAMIC pour les colonnes de **column_set**.|  
|IDBSchemaRowset::GetSchemaRowset|DBSCHEMA_COLUMNS retourne deux nouvelles colonnes : SS_IS_COLUMN_SET et SS_IS_SPARSE.<br /><br /> DBSCHEMA_COLUMNS retourne seulement les colonnes qui ne sont pas membres d’un **column_set**.<br /><br /> Deux nouveaux ensembles de lignes de schéma ont été ajoutés : DBSCHEMA_COLUMNS_EXTENDED retourne toutes les colonnes, indépendamment du caractère épars de l’appartenance à **column_set**. DBSCHEMA_SPARSE_COLUMN_SET retourne seulement les colonnes qui sont membres d’un **column_set**. Ces nouveaux ensembles de lignes ont les mêmes colonnes et restrictions que DBSCHEMA_COLUMNS.|  
|IDBSchemaRowset::GetSchemas|IDBSchemaRowset::GetSchemas inclut les GUID des nouveaux ensembles de lignes DBSCHEMA_COLUMNS_EXTENDED et DBSCHEMA_SPARSE_COLUMN_SET dans la liste des ensembles de lignes de schéma disponibles.|  
|ICommand::Execute|Si **select \* from** *table* est utilisé, il retourne toutes les colonnes qui ne sont pas membres du **column_set** épars, plus une colonne XML qui contient les valeurs de toutes les colonnes non Null membres du **column_set** épars, le cas échéant.|  
|IOpenRowset::OpenRowset|IOpenRowset::OpenRowset retourne un ensemble de lignes avec les mêmes colonnes que ICommand::Execute, avec un **sélectionnez \***  requête sur la même table.|  
|ITableDefinition|Il n’y a aucune modification de cette interface pour les colonnes éparses ou les colonnes d’un **column_set**. Les applications qui doivent effectuer des modifications de schéma doivent exécuter le [!INCLUDE[tsql](../../../includes/tsql-md.md)] approprié directement.|  
  
## <a name="see-also"></a> Voir aussi  
 [Programmation OLE DB Driver pour SQL Server](../../oledb/ole-db/oledb-driver-for-sql-server-programming.md)  
  
  
