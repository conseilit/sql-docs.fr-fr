---
title: GOTO (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- GOTO
- GOTO_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- skipping statements
- Transact-SQL statements, skipping
- labels [SQL Server]
- statements [SQL Server], skipping
- GOTO statement
ms.assetid: 589b6f8e-dc80-416f-9e74-48bed5337f58
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: d171b3907a5fc4b03efba41d4ab1574dc683aeb6
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47753509"
---
# <a name="goto-transact-sql"></a>GOTO (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Modifie le flux d'exécution vers une étiquette. Les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] faisant suite à une instruction GOTO sont ignorées et le traitement reprend à l'étiquette. Les instructions GOTO et les étiquettes peuvent être utilisées à n'importe quel endroit d'une procédure, d'un traitement d'instructions ou d'un bloc d'instructions. Les instructions GOTO peuvent être imbriquées.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Define the label:   
label:   
Alter the execution:  
GOTO label   
```  
  
## <a name="arguments"></a>Arguments  
 *label*  
 Point après lequel le traitement reprend si une instruction GOTO pointe sur cette étiquette. Les étiquettes doivent se conformer aux règles en vigueur pour les [identificateurs](../../relational-databases/databases/database-identifiers.md). Une étiquette peut servir à insérer des commentaires et ce, qu'il existe ou non une instruction GOTO.  
  
## <a name="remarks"></a>Notes   
 Une instruction GOTO peut exister au sein d'instructions conditionnelles de contrôle de flux, de blocs d'instructions ou de procédures mais ne peut pas pointer sur une étiquette située en dehors du traitement d'instructions. Le branchement GOTO peut pointer sur une étiquette dont la définition se trouve avant ou après l'instruction GOTO.  
  
## <a name="permissions"></a>Permissions  
 Par défaut, tout utilisateur reconnu a l'autorisation d'utiliser l'instruction GOTO.  
  
## <a name="examples"></a>Exemples  
 L'exemple ci-dessous illustre l'utilisation de `GOTO` comme mécanisme de branche.  
  
```  
DECLARE @Counter int;  
SET @Counter = 1;  
WHILE @Counter < 10  
BEGIN   
    SELECT @Counter  
    SET @Counter = @Counter + 1  
    IF @Counter = 4 GOTO Branch_One --Jumps to the first branch.  
    IF @Counter = 5 GOTO Branch_Two  --This will never execute.  
END  
Branch_One:  
    SELECT 'Jumping To Branch One.'  
    GOTO Branch_Three; --This will prevent Branch_Two from executing.  
Branch_Two:  
    SELECT 'Jumping To Branch Two.'  
Branch_Three:  
    SELECT 'Jumping To Branch Three.';  
```  
  
## <a name="see-also"></a> Voir aussi  
 [Langage de contrôle de flux &#40;Transact-SQL&#41;](~/t-sql/language-elements/control-of-flow.md)   
 [BEGIN...END &#40;Transact-SQL&#41;](../../t-sql/language-elements/begin-end-transact-sql.md)   
 [BREAK &#40;Transact-SQL&#41;](../../t-sql/language-elements/break-transact-sql.md)   
 [CONTINUE &#40;Transact-SQL&#41;](../../t-sql/language-elements/continue-transact-sql.md)   
 [IF...ELSE &#40;Transact-SQL&#41;](../../t-sql/language-elements/if-else-transact-sql.md)   
 [WAITFOR &#40;Transact-SQL&#41;](../../t-sql/language-elements/waitfor-transact-sql.md)   
 [WHILE &#40;Transact-SQL&#41;](../../t-sql/language-elements/while-transact-sql.md)  
  
  
