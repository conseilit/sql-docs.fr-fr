---
title: Sys.database_filestream_options (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- database_filestream_options
- sys.database_filestream_options_TSQL
- database_filestream_options_TSQL
- sys.database_filestream_options
dev_langs:
- TSQL
helpviewer_keywords:
- sys.database_filestream_options catalog view
ms.assetid: 3383c607-0bbc-456a-ab37-7230f4cbf0e9
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 5fa771b34d4f5ec6711bd895e7a8109def332a3b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47662777"
---
# <a name="sysdatabasefilestreamoptions-transact-sql"></a>sys.database_filestream_options (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Affiche des informations relatives au niveau d'accès non transactionnel aux données FILESTREAM dans les FileTables activés. Contient une ligne pour chaque base de données dans l'instance SQL Server.  
  
 Pour plus d’informations sur les FileTables, consultez [FileTables &#40;SQL Server&#41;](../../relational-databases/blob/filetables-sql-server.md).  
  
  
|colonne|Type|Description|  
|------------|----------|-----------------|  
|**database_id**|**Int**|ID de la base de données. Cette valeur est unique dans l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|**directory_name**|**nvarchar(255)**|Répertoire au niveau de la base de données pour tous les espaces de noms FileTable.|  
|**non_transacted_access**|**tinyint**|Niveau d'accès non transactionnel aux données FILESTREAM activées. Le niveau d’accès est défini par l’option NON_TRANSACTED_ACCESS de la **CREATE DATABASE** ou **ALTER DATABASE** instruction.<br /><br /> Les valeurs possibles pour ce paramètre sont les suivantes :<br /><br /> 0 – Non activé. Il s'agit de la valeur par défaut. Ce niveau est défini en fournissant la valeur **OFF** pour le **NON_TRANSACTED_ACCESS** option.<br /><br /> 1 = Accès en lecture seule. Ce niveau est défini en fournissant la valeur **READ_ONLY** pour le **NON_TRANSACTED_ACCESS** option.<br /><br /> 3 – Accès total. Ce niveau est défini en fournissant la valeur **complète** pour le **NON_TRANSACTED_ACCESS** option.<br /><br /> 5 - En transition vers l'état READONLY<br /><br /> 6 – En transition vers l'état OFF (désactivé)|  
|**non_transacted_access_desc**|**nvarchar(60)**|Description du niveau d’accès non transactionnel identifié dans non_transacted_access.<br /><br /> Les valeurs possibles pour ce paramètre sont les suivantes :<br /><br /> NONE – Ceci est la valeur par défaut.<br /><br /> READ_ONLY<br /><br /> FULL<br /><br /> IN_TRANSITION_TO_READ_ONLY<br /><br /> IN_TRANSITION_TO_OFF|  
  
## <a name="see-also"></a>Voir aussi  
 [Activer les conditions préalables pour les FileTables](../../relational-databases/blob/enable-the-prerequisites-for-filetable.md)  
  
  
