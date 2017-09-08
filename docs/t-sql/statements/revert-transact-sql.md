---
title: "Rétablir (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 07/26/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- REVERT_TSQL
- REVERT
dev_langs:
- TSQL
helpviewer_keywords:
- REVERT statement
- context switching [SQL Server], reverting
- reverting execution context
- REVERT WITH COOKIE statement
- execution context [SQL Server]
- COOKIE clause
ms.assetid: 4688b17a-dfd1-4f03-8db4-273a401f879f
caps.latest.revision: 28
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 2074ef0a9e434ac5c427c5438633c61ead0eb25a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="revert-transact-sql"></a>REVERT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Restaure le contexte d'exécution de l'appelant de la dernière instruction EXECUTE AS.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
REVERT  
    [ WITH COOKIE = @varbinary_variable ]  
```  
  
## <a name="arguments"></a>Arguments  
 WITH COOKIE = @*varbinary_variable*  
 Spécifie le cookie qui a été créé dans correspondante [EXECUTE AS](../../t-sql/statements/execute-as-transact-sql.md) instruction autonome. *@varbinary_variable*est **varbinary(100)**.  
  
## <a name="remarks"></a>Notes  
 REVERT peut figurer dans un module tel qu'une procédure stockée ou une fonction définie par l'utilisateur, mais aussi en tant qu'instruction autonome. À l'intérieur d'un module, REVERT s'applique uniquement aux instructions EXECUTE AS définies dans le module. Par exemple, la procédure stockée suivante exécute une instruction `EXECUTE AS` suivie d'une instruction `REVERT`.  
  
```  
CREATE PROCEDURE dbo.usp_myproc   
  WITH EXECUTE AS CALLER  
AS   
    SELECT SUSER_NAME(), USER_NAME();  
    EXECUTE AS USER = 'guest';  
    SELECT SUSER_NAME(), USER_NAME();  
    REVERT;  
    SELECT SUSER_NAME(), USER_NAME();  
GO  
```  
  
 Supposons que dans la session où la procédure stockée est exécutée, le contexte d'exécution de la session est explicitement modifié en `login1`, comme dans l'exemple ci-dessous.  
  
```  
  -- Sets the execution context of the session to 'login1'.  
EXECUTE AS LOGIN = 'login1';  
GO  
EXECUTE dbo.usp_myproc;   
```  
  
 L'instruction `REVERT` définie dans `usp`_`myproc` change le contexte d'exécution défini dans le module, mais elle n'affecte pas le contexte d'exécution défini à l'extérieur du module. Autrement dit, le contexte d'exécution de la session reste `login1`.  
  
 Lorsque REVERT est une instruction autonome, elle s'applique aux instructions EXECUTE AS définies dans un traitement ou une session. REVERT n'a aucun effet si l'instruction EXECUTE AS correspondante contient la clause WITH NO REVERT. Dans ce cas, le contexte d'exécution reste en vigueur jusqu'à la suppression de la session.  
  
## <a name="using-revert-with-cookie"></a>Utilisation de REVERT WITH COOKIE  
 L’exécution en instruction qui est utilisée pour définir le contexte d’exécution d’une session peut contenir la clause facultative WITH NO REVERT COOKIE = @*varbinary_variabl*e. Lorsque cette instruction est exécutée, la [!INCLUDE[ssDE](../../includes/ssde-md.md)] passe le cookie à @*varbinary_variabl*e. Le contexte d’exécution définie par cette instruction ne peut être restauré au contexte précédent si l’instruction REVERT WITH COOKIE = @*varbinary_variable* instruction contient le bon  *@varbinary_variable*  valeur.  
  
 Ce mécanisme est utile dans un environnement utilisant le groupement de connexions. Le groupement de connexions est la maintenance d'un groupe de connexions de base de données en vue de leur réutilisation par plusieurs utilisateurs finaux. Étant donné que la valeur passée à  *@varbinary_variable*  est connue uniquement de l’appelant de l’exécuter en tant qu’instruction (dans ce cas, l’application), l’appelant peut garantir que le contexte d’exécution qu’il établit ne peut pas être modifié par l’utilisateur final qui appelle l’application. Après restauration du contexte d'exécution, l'application peut changer de contexte au profit d'un autre principal.  
  
## <a name="permissions"></a>Permissions  
 Aucune autorisation n'est requise.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-using-execute-as-and-revert-to-switch-context"></a>A. Utilisation de EXECUTE AS et REVERT pour changer de contexte  
 L'exemple ci-dessous crée une pile de contextes d'exécution à l'aide de plusieurs principaux. L'instruction REVERT y est ensuite utilisée pour rendre le contexte d'exécution à l'appelant précédent. L'instruction REVERT est exécutée plusieurs fois en remontant dans la pile, jusqu'à ce que le contexte d'exécution revienne à l'appelant d'origine.  
  
```  
USE AdventureWorks2012;  
GO  
-- Create two temporary principals.  
CREATE LOGIN login1 WITH PASSWORD = 'J345#$)thb';  
CREATE LOGIN login2 WITH PASSWORD = 'Uor80$23b';  
GO  
CREATE USER user1 FOR LOGIN login1;  
CREATE USER user2 FOR LOGIN login2;  
GO  
-- Give IMPERSONATE permissions on user2 to user1  
-- so that user1 can successfully set the execution context to user2.  
GRANT IMPERSONATE ON USER:: user2 TO user1;  
GO  
-- Display current execution context.  
SELECT SUSER_NAME(), USER_NAME();  
-- Set the execution context to login1.   
EXECUTE AS LOGIN = 'login1';  
-- Verify that the execution context is now login1.  
SELECT SUSER_NAME(), USER_NAME();  
-- Login1 sets the execution context to login2.  
EXECUTE AS USER = 'user2';  
-- Display current execution context.  
SELECT SUSER_NAME(), USER_NAME();  
-- The execution context stack now has three principals: the originating caller, login1, and login2.  
-- The following REVERT statements will reset the execution context to the previous context.  
REVERT;  
-- Display the current execution context.  
SELECT SUSER_NAME(), USER_NAME();  
REVERT;  
-- Display the current execution context.  
SELECT SUSER_NAME(), USER_NAME();  
  
-- Remove the temporary principals.  
DROP LOGIN login1;  
DROP LOGIN login2;  
DROP USER user1;  
DROP USER user2;  
GO  
```  
  
### <a name="b-using-the-with-cookie-clause"></a>B. Utilisation de la clause WITH COOKIE  
 L’exemple suivant définit le contexte d’exécution d’une session à un utilisateur spécifié et spécifie le WITH NO REVERT COOKIE = @*varbinary_variabl*clause de e. L'instruction `REVERT` doit spécifier la valeur passée à la variable `@cookie` dans l'instruction `EXECUTE AS` pour ramener le contexte à l'appelant. Pour exécuter cet exemple, la connexion `login1` et l'utilisateur `user1` créés dans l'exemple A doivent exister.  
  
```  
DECLARE @cookie varbinary(100);  
EXECUTE AS USER = 'user1' WITH COOKIE INTO @cookie;  
-- Store the cookie somewhere safe in your application.  
-- Verify the context switch.  
SELECT SUSER_NAME(), USER_NAME();  
--Display the cookie value.  
SELECT @cookie;  
GO  
-- Use the cookie in the REVERT statement.  
DECLARE @cookie varbinary(100);  
-- Set the cookie value to the one from the SELECT @cookie statement.  
SET @cookie = <value from the SELECT @cookie statement>;  
REVERT WITH COOKIE = @cookie;  
-- Verify the context switch reverted.  
SELECT SUSER_NAME(), USER_NAME();  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [EXECUTE AS &#40; Transact-SQL &#41;](../../t-sql/statements/execute-as-transact-sql.md)   
 [Clause EXECUTE AS &#40;Transact-SQL&#41;](../../t-sql/statements/execute-as-clause-transact-sql.md)   
 [EXECUTE &#40;Transact-SQL&#41;](../../t-sql/language-elements/execute-transact-sql.md)   
 [SUSER_NAME &#40; Transact-SQL &#41;](../../t-sql/functions/suser-name-transact-sql.md)   
 [User_name &#40; Transact-SQL &#41;](../../t-sql/functions/user-name-transact-sql.md)   
 [CREATE LOGIN &#40;Transact-SQL&#41;](../../t-sql/statements/create-login-transact-sql.md)   
 [CREATE USER &#40;Transact-SQL&#41;](../../t-sql/statements/create-user-transact-sql.md)  
  
  
