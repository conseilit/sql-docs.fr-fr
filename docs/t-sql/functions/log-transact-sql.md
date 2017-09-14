---
title: LOG (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 07/29/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- LOG
- LOG_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- float expressions
- logarithm of expression
- LOG function
ms.assetid: f7c39511-cd84-4362-93ba-0d93655217ee
caps.latest.revision: 42
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 4531f8e411dbe24a67a6fd5d6ac987fcb2d90c18
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="log-transact-sql"></a>LOG (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retourne le logarithme népérien de l’objet **float** expression dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-- Syntax for SQL Server  
  
LOG ( float_expression [, base ] )  
```  
  
```  
-- Syntax for Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
LOG ( float_expression )  
```  
  
## <a name="arguments"></a>Arguments  
 *expression*  
 Est un [expression](../../t-sql/language-elements/expressions-transact-sql.md) de type **float** ou d’un type qui peut être implicitement converti en **float**.  
  
 *base*  
 Argument entier facultatif qui définit la base du logarithme.  
  
**S’applique aux**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] via[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]
  
## <a name="return-types"></a>Types de retour  
 **float**  
  
## <a name="remarks"></a>Notes  
 Par défaut, **LOG()** renvoie le logarithme népérien. En commençant par [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], vous pouvez modifier la base du logarithme une autre valeur à l’aide de l’option *base* paramètre.  
  
 Le logarithme népérien est le logarithme de base **e**, où **e** est une constante irrationnelle approximativement égale à 2,718281828.  
  
 Le logarithme naturel de la valeur exponentielle d’un nombre est le nombre lui-même : journal (EXP (  *n*  )) =  *n* . La valeur exponentielle du logarithme naturel d’un nombre est le nombre lui-même : EXP (journal (  *n*  )) =  *n* .  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-calculating-the-logarithm-for-a-number"></a>A. Calcul du logarithme d'un nombre  
 L’exemple suivant calcule le `LOG` spécifié **float** expression.  
  
```  
DECLARE @var float = 10;  
SELECT 'The LOG of the variable is: ' + CONVERT(varchar, LOG(@var));  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
-------------------------------------  
The LOG of the variable is: 2.30259  
  
(1 row(s) affected)  
```  
  
### <a name="b-calculating-the-logarithm-of-the-exponent-of-a-number"></a>B. Calcul du logarithme de l'exposant d'un nombre  
 L'exemple suivant calcule le logarithme (`LOG`) de l'exposant d'un nombre.  
  
```  
SELECT LOG (EXP (10));  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
----------------------------------  
10  
(1 row(s) affected)  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="c-calculating-the-logarithm-for-a-number"></a>C. Calcul du logarithme d’un nombre  
 L’exemple suivant calcule le `LOG` spécifié **float** expression.  
  
```  
SELECT LOG(10);  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `----------------`  
  
 `2.30`  
  
### <a name="d-calculating-the-logarithm-of-the-exponent-of-a-number"></a>D. Calcul du logarithme de l’exposant d’un nombre  
 L'exemple suivant calcule le logarithme (`LOG`) de l'exposant d'un nombre.  
  
```  
SELECT LOG(EXP (10));  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `---------`  
  
 `10.00`  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions mathématiques &#40; Transact-SQL &#41;](../../t-sql/functions/mathematical-functions-transact-sql.md)   
 [EXP &#40; Transact-SQL &#41;](../../t-sql/functions/exp-transact-sql.md)   
 [LOG10 &#40; Transact-SQL &#41;](../../t-sql/functions/log10-transact-sql.md)  
  
  

