---
title: GRANT - Octroyer des autorisations sur un assembly (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/12/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- granting permissions [SQL Server], assemblies
- assemblies [CLR integration], permissions
- GRANT statement, assemblies
ms.assetid: dce1e027-f859-4967-bdda-16a95ae460d0
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 1b1c6938730ff21e70790dddbcb20653878c53e2
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47678977"
---
# <a name="grant-assembly-permissions-transact-sql"></a>GRANT - Autorisations sur un assembly (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Accorde des autorisations sur un assembly.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
GRANT { permission [ ,...n ] } ON ASSEMBLY :: assembly_name  
    TO database_principal [ ,...n ]  
    [ WITH GRANT OPTION ]  
    [ AS granting_principal ]  
```  
  
## <a name="arguments"></a>Arguments  
 *permission*  
 Spécifie une autorisation qu'il est possible d'accorder sur un assembly. Voir ci-dessous.  
  
 ON ASSEMBLY **::***assembly_name*  
 Spécifie l'assembly sur lequel l'autorisation est accordée. Le qualificateur d'étendue "::" est indispensable.  
  
 *database_principal*  
 Spécifie le principal auquel l'autorisation est accordée. Il peut s'agir :  
  
-   d'un utilisateur de base de données ;  
-   d'un rôle de base de données ;  
-   d'un rôle d'application ;  
-   d'un utilisateur de base de données mappé sur une connexion Windows ;  
-   d'un utilisateur de base de données mappé sur un groupe Windows ;  
-   d'un utilisateur de base de données mappé sur un certificat ;  
-   d'un utilisateur de base de données mappé à une clé asymétrique ;  
-   d'un utilisateur de base de données qui n'est pas mappé sur le principal d'un serveur.  
  
GRANT OPTION  
 Indique que le principal a également la possibilité d'accorder l'autorisation spécifiée à d'autres principaux.  
  
AS *granting_principal*  
 Spécifie un principal dont le principal qui exécute cette requête dérive son droit d'accorder l'autorisation. Il peut s'agir :  
  
-   d'un utilisateur de base de données ;  
-   d'un rôle de base de données ;  
-   d'un rôle d'application ;  
-   d'un utilisateur de base de données mappé sur une connexion Windows ;  
-   d'un utilisateur de base de données mappé sur un groupe Windows ;  
-   d'un utilisateur de base de données mappé sur un certificat ;  
-   d'un utilisateur de base de données mappé à une clé asymétrique ;  
-   d'un utilisateur de base de données qui n'est pas mappé sur le principal d'un serveur.  
  
## <a name="remarks"></a>Notes   
 Un assembly est un élément sécurisable au niveau base de données contenu par la base de données parente dans la hiérarchie des autorisations. Les autorisations les plus particulières et les plus limitées qu'il est possible d'accorder sur un assembly sont mentionnées ci-dessous, ainsi que les autorisations plus générales qui les englobent implicitement.  
  
|Autorisation sur un assembly|Impliquée par une autorisation sur un assembly|Impliquée par une autorisation de base de données|  
|-------------------------|------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|ALTER|CONTROL|ALTER ANY ASSEMBLY|  
|REFERENCES|CONTROL|REFERENCES|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="permissions"></a>Permissions  
 Le fournisseur d'autorisations (ou le principal spécifié avec l'option AS) doit posséder l'autorisation elle-même avec l'option GRANT OPTION ou une autorisation plus élevée qui implique l'autorisation accordée.  
  
 En cas d'utilisation de l'option AS, ces critères s'appliquent.  
  
|AS *granting_principal*|Autres autorisations nécessaires|  
|------------------------------|------------------------------------|  
|Utilisateur de base de données|Autorisation IMPERSONATE sur l’utilisateur, appartenance au rôle de base de données fixe **db_securityadmin**, appartenance au rôle de base de données fixe **db_owner** ou appartenance au rôle serveur fixe **sysadmin**.|  
|Utilisateur de base de données mappé à une connexion Windows|Autorisation IMPERSONATE sur l’utilisateur, appartenance au rôle de base de données fixe **db_securityadmin**, appartenance au rôle de base de données fixe **db_owner** ou appartenance au rôle serveur fixe **sysadmin**.|  
|Utilisateur de base de données mappé à un groupe Windows|Appartenance au groupe Windows, appartenance au rôle de base de données fixes **db_securityadmin**, appartenance au rôle de base de données fixe **db_owner** ou appartenance au rôle serveur fixe **sysadmin**.|  
|Utilisateur de base de données mappé à un certificat|Appartenance au rôle de base de données fixe **db_securityadmin**, appartenance au rôle de base de données fixe **db_owner** ou appartenance au rôle serveur fixe **sysadmin**.|  
|Utilisateur de base de données mappé à une clé asymétrique|Appartenance au rôle de base de données fixe **db_securityadmin**, appartenance au rôle de base de données fixe **db_owner** ou appartenance au rôle serveur fixe **sysadmin**.|  
|Utilisateur de base de données qui n'est mappé sur aucun principal d'un serveur|Autorisation IMPERSONATE sur l’utilisateur, appartenance au rôle de base de données fixe **db_securityadmin**, appartenance au rôle de base de données fixe **db_owner** ou appartenance au rôle serveur fixe **sysadmin**.|  
|Rôle de base de données|Autorisation ALTER sur le rôle, appartenance au rôle de base de données fixe **db_securityadmin**, appartenance au rôle de base de données fixe **db_owner** ou appartenance au rôle serveur fixe **sysadmin**.|  
|Rôle d'application|Autorisation ALTER sur le rôle, appartenance au rôle de base de données fixe **db_securityadmin**, appartenance au rôle de base de données fixe **db_owner** ou appartenance au rôle serveur fixe **sysadmin**.|  
  
 Les propriétaires d'objets peuvent accorder des autorisations sur les objets qu'ils possèdent. Les principaux ayant l'autorisation CONTROL sur un élément sécurisable peuvent accorder une autorisation sur cet élément.  
  
 Les bénéficiaires de l’autorisation CONTROL SERVER, comme les membres du rôle serveur fixe **sysadmin**, peuvent accorder n’importe quelle autorisation sur n’importe quel sécurisable du serveur. Les bénéficiaires de l’autorisation CONTROL sur une base de données, comme les membres du rôle de base de données fixe **db_owner**, peuvent accorder n’importe quelle autorisation sur n’importe quel sécurisable de la base de données. Les détenteurs de l'autorisation CONTROL sur un schéma peuvent accorder une autorisation sur n'importe quel objet dans ce schéma.  
  
## <a name="see-also"></a> Voir aussi  
 [GRANT &#40;Transact-SQL&#41;](../../t-sql/statements/grant-transact-sql.md)   
 [Autorisations &#40;moteur de base de données&#41;](../../relational-databases/security/permissions-database-engine.md)   
 [Principaux &#40;moteur de base de données&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [CREATE CERTIFICATE &#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)   
 [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-asymmetric-key-transact-sql.md)   
 [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-application-role-transact-sql.md)   
 [Hiérarchie de chiffrement](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  
