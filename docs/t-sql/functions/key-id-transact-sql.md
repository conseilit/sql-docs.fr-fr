---
title: KEY_ID (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Key_ID
- Key_ID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- identification numbers [SQL Server], symmetric keys
- KEY_ID function
- symmetric keys [SQL Server], IDs
- IDs [SQL Server], symmetric keys
ms.assetid: d7309542-dbbe-41dc-b42e-5d9a1c8b4838
caps.latest.revision: 27
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: bb4684105e8f8e4a13c1df77437271c1e820dce2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="keyid-transact-sql"></a>KEY_ID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Renvoie l'ID d'une clé symétrique dans la base de données actuelle.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Key_ID ( 'Key_Name' )  
```  
  
## <a name="arguments"></a>Arguments  
 **'** *Key_Name* **'**  
 Nom de la clé symétrique dans la base de données.  
  
## <a name="return-types"></a>Types de retour  
 **int**  
  
## <a name="remarks"></a>Notes  
 Le nom d'une clé temporaire doit commencer par le signe #.  
  
## <a name="permissions"></a>Permissions  
 Les clés temporaires étant disponibles seulement dans la session où elles sont créées, aucune autorisation n'est nécessaire pour y accéder. Pour accéder à une clé non temporaire, l'appelant doit disposer d'une autorisation sur la clé et l'autorisation VIEW sur la clé ne doit pas lui avoir été refusée.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-returning-the-id-of-a-symmetric-key"></a>A. Renvoi de l'ID d'une clé symétrique  
 L'exemple suivant renvoie l'ID de la clé `ABerglundKey1`.  
  
```  
SELECT KEY_ID('ABerglundKey1');  
```  
  
### <a name="b-returning-the-id-of-a-temporary-symmetric-key"></a>B. Renvoi de l'ID d'une clé symétrique temporaire  
 L'exemple suivant renvoie l'ID d'une clé symétrique temporaire. Notez que `#` figure au début du nom de la clé.  
  
```  
SELECT KEY_ID('#ABerglundKey2');  
```  
  
## <a name="see-also"></a>Voir aussi  
 [KEY_GUID &#40; Transact-SQL &#41;](../../t-sql/functions/key-guid-transact-sql.md)   
 [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-symmetric-key-transact-sql.md)   
 [Sys.symmetric_keys &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql.md)   
 [sys.key_encryptions &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-key-encryptions-transact-sql.md)   
 [Hiérarchie de chiffrement](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  