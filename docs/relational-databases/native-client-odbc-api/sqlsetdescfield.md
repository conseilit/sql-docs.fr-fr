---
title: SQLSetDescField | Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetDescField function
ms.assetid: de4bed15-15be-4825-994c-1046255e725a
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 6659f2abe2a167ece55aa8d6a9bbc99065f56613
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47606758"
---
# <a name="sqlsetdescfield"></a>SQLSetDescField
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  SQLSetDescField peut être utilisé pour définir les champs de descripteur pour les paramètres table et les colonnes de paramètre table. Pour plus d’informations sur les champs disponibles, consultez [champs de descripteur de paramètre table-Valued](../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) et [champs de descripteur pour les colonnes constituant des paramètres table-Valued](../../relational-databases/native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).  
  
## <a name="remarks"></a>Notes  
 Les colonnes de paramètre table sont disponibles uniquement lorsque le champ d'en-tête de descripteur SQL_SOPT_SS_PARAM_FOCUS est défini sur l'ordinal d'un enregistrement pour lequel SQL_DESC_TYPE a la valeur SQL_SS_TABLE. Pour plus d’informations sur SQL_SOPT_SS_PARAM_FOCUS, consultez [SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md).  
  
 Si une tentative est effectuée pour définir SQL_SOPT_SS_PARAM_FOCUS à l’ordinal d’un paramètre qui n’est pas un paramètre table, SQLSetStmtAttr retourne SQL_ERROR et un enregistrement de diagnostic est créé avec SQLSTATE = HY024 et le message « valeur d’attribut non valide ». SQL_SOPT_SS_PARAM_FOCUS n'est pas modifié quand SQL_ERROR est retourné.  
  
 La définition de SQL_SOPT_SS_PARAM_FOCUS sur 0 restaure l'accès aux enregistrements de descripteurs pour les paramètres.  
  
 Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).  
  
## <a name="sqlsetdescfield-support-for-enhanced-date-and-time-features"></a>Prise en charge par SQLSetDescField des fonctionnalités de date et heure améliorées  
 Les fonctionnalités de date/heure ont été améliorées dans ODBC. Pour plus d’informations sur le champ de descripteur disponible pour les types date/heure de nouveau, consultez [Parameter and Result Metadata](../../relational-databases/native-client-odbc-date-time/metadata-parameter-and-result.md).  
  
 Pour plus d’informations, consultez [améliorations Date / heure &#40;ODBC&#41;](../../relational-databases/native-client-odbc-date-time/date-and-time-improvements-odbc.md).  
  
## <a name="sqlsetdescfield-support-for-large-clr-udts"></a>Prise en charge par SQLSetDescField des grands types CLR définis par l'utilisateur  
 SQLSetDescField prend en charge les types CLR volumineux définis par l’utilisateur (UDT). Pour plus d’informations, consultez [Large CLR User-Defined Types &#40;ODBC&#41;](../../relational-databases/native-client/odbc/large-clr-user-defined-types-odbc.md).  
  
## <a name="sqlsetdescfield-support-for-sparse-columns"></a>Prise en charge par SQLSetDescField des colonnes éparses  
 SQLSetDecField peut être utilisé pour définir SQL_SOPT_SS_NAME_SCOPE dans le descripteur de paramètre d’application (APD) sur les valeurs SQL_SS_NAME_SCOPE_EXTENDED et SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.  
  
 Pour plus d’informations, consultez [Sparse Columns Support &#40;ODBC&#41;](../../relational-databases/native-client/odbc/sparse-columns-support-odbc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [SQLSetDescField](http://go.microsoft.com/fwlink/?LinkId=80705)   
 [Détails de l’implémentation d’API ODBC](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
