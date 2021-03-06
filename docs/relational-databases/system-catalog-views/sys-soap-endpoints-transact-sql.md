---
title: Sys.soap_endpoints (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- soap_endpoints_TSQL
- sys.soap_endpoints
- soap_endpoints
- sys.soap_endpoints_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.soap_endpoints catalog view
ms.assetid: f50dcbfc-02ed-4a19-9c07-c78a5a1b3224
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 29bb67908dc0f2946aa92738ab83c1d43a884f81
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47791187"
---
# <a name="syssoapendpoints-transact-sql"></a>sys.soap_endpoints (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 Contient une ligne pour chaque point de terminaison du serveur qui supporte une charge utile de type SOAP. Pour chaque ligne dans cette vue, il existe une ligne correspondante avec le même **endpoint_id** dans le **sys.http_endpoints** affichage catalogue qui contient les métadonnées de configuration de HTTP.  
  
 
|Nom de colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|**< colonnes héritées >**||Pour obtenir la liste des colonnes qui hérite de cette vue, consultez [sys.endpoints &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-endpoints-transact-sql.md).|  
|**is_sql_language_enabled**|**bit**|1 = TRAITEMENTS = L'option ENABLED a été spécifiée, ce qui signifie que les traitements SQL ad-hoc sont autorisées sur le point de terminaison.|  
|**wsdl_generator_procedure**|**nvarchar(776)**|Nom en trois parties de la procédure stockée qui implémente cette méthode.<br /><br /> Les noms des méthodes requièrent une syntaxe stricte en trois parties. Les noms composés d'une, de deux ou de quatre parties ne sont pas autorisés.|  
|**default_database**|**sysname**|Nom de la base de données par défaut indiqué dans l'option DATABASE =.<br /><br /> NULL = DEFAULT a été spécifié.|  
|**default_namespace**|**nvarchar(384)**|L’espace de noms par défaut spécifié dans l’espace de noms = option, ou `http://tempuri.org` si la valeur par défaut a été spécifiée à la place.|  
|**default_result_schema**|**tinyint**|Valeur par défaut de l'option SCHEMA =.<br /><br /> 0 = AUCUN<br /><br /> 1 = STANDARD|  
|**default_result_schema_desc**|**nvarchar(60)**|Description de la valeur par défaut de l'option SCHEMA =.<br /><br /> Aucune<br /><br /> STANDARD|  
|**is_xml_charset_enforced**|**bit**|0 = CHARACTER_SET = L'option SQL a été spécifiée.<br /><br /> 1 = CHARACTER_SET = L'option XML a été spécifiée.|  
|**is_session_enabled**|**bit**|0 = SESSION = L'option DISABLE a été spécifiée.<br /><br /> 1 = SESSION = L'option ENABLED a été spécifiée.|  
|**session_timeout**|**Int**|Valeur spécifiée dans l'option SESSION_TIMEOUT =.|  
|**login_type**|**nvarchar(60)**|Type d'authentification autorisé sur ce point de terminaison.<br /><br /> WINDOWS<br /><br /> MIXED|  
|**header_limit**|**Int**|Taille maximale pouvant être autorisée pour l'en-tête SOAP.|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Vues de catalogue des points de terminaison &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql.md)   
 [Affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
