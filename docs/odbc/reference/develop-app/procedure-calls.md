---
title: Appels de procédure | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- escape sequences [ODBC], procedure calls
- procedure calls [ODBC]
ms.assetid: 145130cc-40e7-4722-8417-dff131084752
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 775b48eb5a7f2089d65c6e9548a986b2f7b9bec7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47826107"
---
# <a name="procedure-calls"></a>Appels de procédure
Un *procédure* est un objet exécutable stocké sur la source de données. Généralement, il s'agit d'une ou plusieurs instructions SQL qui ont été précompilées. La séquence d’échappement pour appeler une procédure est  
  
 **{**[**? =**]**appeler** *nom de la procédure*[**(**[*paramètre*] [**,**[*paramètre*]]... **)**]**}**  
  
 où *nom de la procédure* Spécifie le nom d’une procédure et *paramètre* spécifie un paramètre de procédure.  
  
 Pour plus d’informations sur la séquence d’échappement de l’appel de procédure, consultez [séquence d’échappement de Call procédure](../../../odbc/reference/appendixes/procedure-call-escape-sequence.md) dans l’annexe c : SQL grammaire.  
  
 Une procédure peut avoir zéro, un ou plusieurs paramètres. Elle peut également retourner une valeur, comme indiqué par le marqueur de paramètre facultatif **? =** au début de la syntaxe. Si *paramètre* est une entrée ou un paramètre d’entrée/sortie, il peut être un littéral ou un marqueur de paramètre. Toutefois, applications interopérables doivent toujours utiliser des marqueurs de paramètres, car certaines sources de données n’acceptent pas les valeurs de paramètre literal. Si *paramètre* est un paramètre de sortie, il doit être un marqueur de paramètre. Marqueurs de paramètres doivent être liés avec **SQLBindParameter** avant l’appel de procédure instruction est exécutée.  
  
 Les paramètres d'entrée et d'entrée/sortie peuvent être omis dans les appels de procédure. Si une procédure est appelée avec des parenthèses mais sans paramètres, tels que {appeler *nom de la procédure*()}, le pilote instruit la source de données à utiliser la valeur par défaut pour le premier paramètre. Si la procédure n’a pas de tous les paramètres, cela peut entraîner l’échec de la procédure. Si une procédure est appelée sans parenthèses, telles que {appeler *nom de la procédure*}, le pilote n’envoie pas les valeurs de paramètre.  
  
 Des littéraux peuvent être spécifiés comme paramètres d'entrée et d'entrée/sortie dans les appels de procédure. Par exemple, supposons que la procédure **InsertOrder** a cinq paramètres d’entrée. L’appel suivant à **InsertOrder** omet le premier paramètre, fournit un littéral pour le deuxième paramètre et utilise un marqueur de paramètre pour le troisième, la quatrième et cinquième paramètres :  
  
```  
{call InsertOrder(, 10, ?, ?, ?)}   // Not interoperable!  
```  
  
 Notez que si un paramètre est omis, la virgule qui le sépare des autres paramètres doit toujours apparaître. Si un paramètre d'entrée ou d'entrée/sortie est omis, la procédure utilise la valeur par défaut du paramètre. Une autre façon de spécifier que la valeur par défaut d’un paramètre d’entrée ou d’entrée/sortie consiste à définir la valeur de la mémoire tampon de longueur / d’indicateur lié au paramètre à SQL_DEFAULT_PARAM.  
  
 Si un paramètre d’entrée/sortie est omis ou si un littéral est fourni pour le paramètre, le pilote ignore la valeur de sortie. De la même façon, si le marqueur de paramètre pour la valeur de retour d'une procédure est omis, le pilote ignore la valeur de retour. Enfin, si une application spécifie un paramètre de valeur de retour pour une procédure qui ne renvoie pas de valeur, le pilote affecte la valeur SQL_NULL_DATA à la mémoire tampon de l'indicateur/longueur associée au paramètre.  
  
 Supposons que la procédure PARTS_IN_ORDERS crée un jeu de résultats qui contient une liste de commandes qui contiennent un numéro de référence particulier. Le code suivant appelle cette procédure pour le numéro de référence 544 :  
  
```  
SQLUINTEGER   PartID;  
SQLINTEGER    PartIDInd = 0;  
  
// Bind the parameter.  
SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_SLONG, SQL_INTEGER, 0, 0,  
                  &PartID, 0, PartIDInd);  
  
// Place the department number in PartID.  
PartID = 544;  
  
// Execute the statement.  
SQLExecDirect(hstmt, "{call PARTS_IN_ORDERS(?)}", SQL_NTS);  
```  
  
 Pour déterminer si une source de données prend en charge les procédures, une application appelle **SQLGetInfo** avec l’option SQL_PROCEDURES.  
  
 Pour plus d’informations sur les procédures, consultez [procédures](../../../odbc/reference/develop-app/procedures-odbc.md).
