---
title: Prise en charge des types de paramètre table OLE DB | Microsoft Docs
description: Prise en charge des types de paramètre table OLE DB
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (OLE DB)
author: pmasl
ms.author: pelopes
manager: craigg
ms.openlocfilehash: e9e90a70089f3a9c2dcca20cbfe9deea43ca97b6
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47813487"
---
# <a name="ole-db-table-valued-parameter-type-support"></a>Prise en charge du type de paramètre table OLE DB
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  Cet article décrit la prise en charge du type OLE DB pour les paramètres table.  
  
## <a name="table-valued-parameter-rowset-object"></a>Objet d'ensemble de lignes de paramètre table  
 Vous pouvez créer un objet d'ensemble de lignes spécialisé pour des paramètres table. Vous créez l’objet d’ensemble de lignes de paramètre table à l’aide de ITableDefinitionWithConstraints::CreateTableWithConstraints ou IOpenRowset::OpenRowset. Pour ce faire, définissez le membre *eKind* du paramètre *pTableID* sur DBKIND_GUID_NAME, et fournissez CLSID_ROWSET_INMEMORY comme membre *guid*. Le nom du type de serveur pour le paramètre table doit être spécifié dans le *pwszName* membre *pTableID* lors de l’utilisation IOpenRowset::OpenRowset. L’objet d’ensemble de lignes de paramètre table se comporte comme un régulière OLE DB Driver pour objet de SQL Server.  
  
```  
const GUID CLSID_ROWSET_TVP =   
{0xc7ef28d5, 0x7bee, 0x443f, {0x86, 0xda, 0xe3, 0x98, 0x4f, 0xcd, 0x4d, 0xf9}};  
  
CoType RowsetTVP  
{  
[mandatory] interface IAccessor;  
[mandatory] interface IColumnsInfo;  
[mandatory] interface IConvertType;  
[mandatory] interface IRowset;  
[mandatory] interface IRowsetInfo;  
[optional]  interface IColumnsRowset;  
[optional]  interface IRowsetChange;  
[optional]  interface ISupportErrorInfo;  
};  
```  
  
## <a name="dbtypetable"></a>DBTYPE_TABLE  
 DBTYPE_TABLE est un nouveau type qui représente un type de table. Ce type spécifie des paramètres table dans différentes interfaces OLE DB où un DBTYPE est requis.  
  
```  
#define DBTYPE_TABLE (143)  
```  
  
 DBTYPE_TABLE a le même format que DBTYPE_IUNKNOWN. Il s’agit d’un pointeur vers un objet du tampon de données. Pour une spécification complète dans les liaisons, le consommateur remplit la mémoire tampon DBOBJECT, avec *iid* défini sur l’une des interfaces d’objet d’ensemble de lignes (IID_IRowset). Si aucun DBOBJECT n’est spécifié dans les liaisons, IID_IRowset est supposé.  
  
 Les conversions vers et à partir de DBTYPE_TABLE pour tout autre type ne sont pas prises en charge. IConvertType::CanConvert retourne S_FALSE pour les conversions non prises en charge, pour toute demande autre qu’une conversion DBTYPE_TABLE en DBTYPE_TABLE. Cela suppose DBCONVERTFLAGS_PARAMETER sur l’objet Command.  
  
## <a name="methods"></a>Méthodes  
 Pour plus d’informations sur les méthodes OLE DB qui prennent en charge les paramètres table, consultez [prennent en charge de Type de paramètre OLE DB Table-Valued &#40;méthodes&#41;](../../oledb/ole-db-table-valued-parameters/ole-db-table-valued-parameter-type-support-methods.md).  
  
## <a name="properties"></a>Propriétés  
 Pour plus d’informations sur les propriétés OLE DB qui prennent en charge les paramètres table, consultez [prennent en charge de Type de paramètre OLE DB Table-Valued &#40;propriétés&#41;](../../oledb/ole-db-table-valued-parameters/ole-db-table-valued-parameter-type-support-properties.md).  
  
## <a name="see-also"></a> Voir aussi  
 [Paramètres table &#40;OLE DB&#41;](../../oledb/ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)   
 [Utiliser les paramètres table &#40;OLE DB&#41;](../../oledb/ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
