---
title: Sys.fn_helpcollations (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 08/23/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_helpcollations
- fn_helpcollations_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.fn_helpcollations function
- collations [SQL Server], supported
- fn_helpcollations function
ms.assetid: b5082e81-1fee-4e2c-b567-5412eaee41c1
author: rothja
ms.author: jroth
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: f781faaf571a9c97dfa141bb94e086368e12bd42
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47608758"
---
# <a name="sysfnhelpcollations-transact-sql"></a>sys.fn_helpcollations (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retourne une liste de tous les classements pris en charge.  
  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
fn_helpcollations ()  
```  
  
## <a name="tables-returned"></a>Tables retournées  
 **fn_helpcollations** renvoie les informations suivantes.  
  
|Nom de colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|Nom   |**sysname**|Nom de classement standard|  
|Description|**nvarchar(1000)**|Description du classement|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prend en charge les classements Windows. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prend également en charge un nombre limité (<80) de classements appelés classements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui ont été développés avant que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne prenne en charge les classements Windows. Les classements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont encore pris en charge à des fins de compatibilité descendante, mais ne doivent pas être utilisés pour les nouveaux travaux de développement. Pour plus d’informations sur le classement Windows, consultez [Nom de classement Windows &#40;Transact-SQL&#41;](../../t-sql/statements/windows-collation-name-transact-sql.md). Pour plus d’informations sur les classements, consultez [Prise en charge d’Unicode et du classement](../../relational-databases/collations/collation-and-unicode-support.md).  
  

## <a name="examples"></a>Exemples  
 L'exemple suivant retourne le nom de tous les classements commençant par la lettre `L` et correspondant à des classements de tri binaire.  
  
```  
SELECT Name, Description FROM fn_helpcollations()  
WHERE Name like 'L%' AND Description LIKE '% binary sort';  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```   
 Name                   Description  
 -------------------    ------------------------------------  
 Lao_100_BIN            Lao-100, binary sort  
 Latin1_General_BIN     Latin1-General, binary sort  
 Latin1_General_100_BIN Latin1-General-100, binary sort  
 Latvian_BIN            Latvian, binary sort  
 Latvian_100_BIN        Latvian-100, binary sort  
 Lithuanian_BIN         Lithuanian, binary sort  
 Lithuanian_100_BIN     Lithuanian-100, binary sort  
  
 (7 row(s) affected)  
 ```    
  
## <a name="see-also"></a>Voir aussi  
[COLLATE &#40;Transact-SQL&#41;](~/t-sql/statements/collations.md)   
[COLLATIONPROPERTY &#40;Transact-SQL&#41;](../../t-sql/functions/collation-functions-collationproperty-transact-sql.md)  
[Prise en charge du classement de base de données pour Azure SQL Data Warehouse](https://azure.microsoft.com/blog/database-collation-support-for-azure-sql-data-warehouse-2)  

