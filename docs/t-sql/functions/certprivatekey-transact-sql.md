---
title: CERTPRIVATEKEY (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- CERTPRIVATEKEY
- CERTPRIVATEKEY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- CERTPRIVATEKEY
ms.assetid: 33e0f01e-39ac-46da-94ff-fe53b1116df4
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 3d5605a133c4edb9a54b919522d17ffd65478a82
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47652097"
---
# <a name="certprivatekey-transact-sql"></a>CERTPRIVATEKEY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

Cette fonction retourne la clé privée d’un certificat au format binaire. Cette fonction accepte trois arguments.
-   Un ID de certificat.  
-   Un mot de passe de chiffrement utilisé pour chiffrer les bits de clé privée retournés par la fonction. Cette approche n’expose pas les clés en texte clair aux utilisateurs.  
-   Un mot de passe de déchiffrement facultatif. Un mot de passe de déchiffrement spécifié est utilisé pour déchiffrer la clé privée du certificat. Sinon, la clé principale de la base de données est utilisée.  
  
Seuls les utilisateurs qui ont accès à la clé privée du certificat peuvent utiliser cette fonction. Cette fonction retourne la clé privée au format PVK.
  
## <a name="syntax"></a>Syntaxe  
  
```sql
CERTPRIVATEKEY   
    (  
          cert_ID   
        , ' encryption_password '   
      [ , ' decryption_password ' ]  
    )  
```  
  
## <a name="arguments"></a>Arguments  
*certificate_ID*  
**certificate_id** du certificat. Obtenez cette valeur à partir de sys.certificates ou à l’aide de la fonction [CERT_ID &#40;Transact-SQL&#41;](../../t-sql/functions/cert-id-transact-sql.md). *cert_id* a le type de données **int**.
  
*encryption_password*  
Mot de passe utilisé pour chiffrer la valeur binaire retournée.
  
*decryption_password*  
Mot de passe utilisé pour déchiffrer la valeur binaire retournée.
  
## <a name="return-types"></a>Types de retour
**varbinary**
  
## <a name="remarks"></a>Notes   
Les fonctions **CERTENCODED** et **CERTPRIVATEKEY** sont utilisées ensemble pour retourner les différentes parties d’un certificat sous forme binaire.
  
## <a name="permissions"></a>Permissions  
**CERTPRIVATEKEY** est disponible publiquement.
  
## <a name="examples"></a>Exemples  
  
```sql
CREATE DATABASE TEST1;  
GO  
USE TEST1  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'Use 5tr0ng P^55Words'  
GO  
CREATE CERTIFICATE Shipping04   
WITH SUBJECT = 'Sammamish Shipping Records',   
EXPIRY_DATE = '20401031';  
GO  
SELECT CERTPRIVATEKEY(CERT_ID('Shipping04'), 'jklalkaa/; uia3dd');  
```  
  
Pour obtenir un exemple plus complexe qui utilise **CERTPRIVATEKEY** et **CERTENCODED** afin de copier un certificat dans une autre base de données, consultez l’exemple B de la rubrique [CERTENCODED &#40;Transact-SQL&#41;](../../t-sql/functions/certencoded-transact-sql.md).
  
## <a name="see-also"></a>Voir aussi
[Fonctions de sécurité &#40;Transact-SQL&#41;](../../t-sql/functions/security-functions-transact-sql.md)  
[CREATE CERTIFICATE &#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)
[Fonctions de sécurité &#40;Transact-SQL&#41;](../../t-sql/functions/security-functions-transact-sql.md)
[sys.certificates &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-certificates-transact-sql.md)
  
  
