---
title: Exemple de Diagnostic de pilote basé sur fichier | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- file-based driver diagnostic [ODBC]
- diagnostic information [ODBC], examples
- error messages [ODBC], diagnostic messages
ms.assetid: 0575fccd-4641-478d-a3cc-5a764e35bae2
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: decb09098cee4b9ab6473e3c622b9917a89e9b09
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47809317"
---
# <a name="file-based-driver-diagnostic-example"></a>Exemple de diagnostic d’un pilote basé sur des fichiers
Un pilote basé sur fichier agit comme un pilote ODBC et comme une source de données. Il peut donc générer des erreurs et avertissements à la fois en tant que composant dans une connexion ODBC et comme une source de données. Étant donné que c’est également le composant qui sert d’interface avec le Gestionnaire de pilotes, il met en forme et retourne les arguments pour **SQLGetDiagRec**.  
  
 Par exemple, si un pilote Microsoft® pour dBASE n’a pas pu allouer suffisamment de mémoire, elle peut retourner les valeurs suivantes à partir de **SQLGetDiagRec**:  
  
```  
SQLSTATE:         "HY001"  
Native Error:      42052  
Diagnostic Msg:   "[Microsoft][ODBC dBASE Driver]Unable to allocate sufficient memory."  
```  
  
 Parce que cette erreur n’est pas liée à la source de données, le pilote ajouté uniquement des préfixes pour le message de diagnostic pour le fournisseur ([Microsoft]) et le pilote ([ODBC pilote dBASE]).  
  
 Si le pilote n’a pas pu trouver le fichier Employee.dbf, elle peut retourner les valeurs suivantes à partir de **SQLGetDiagRec**:  
  
```  
SQLSTATE:         "42S02"  
Native Error:      -1305  
Diagnostic Msg:   "[Microsoft][ODBC dBASE Driver][dBASE]No such table or object"  
```  
  
 Étant donné que cette erreur a été liée à la source de données, le pilote ajouté le format de fichier de la source de données ([dBASE]) en tant que préfixe pour le message de diagnostic. Étant donné que le pilote a été également le composant connectée à la source de données, il ajouté des préfixes pour le fournisseur ([Microsoft]) et le pilote ([ODBC pilote dBASE]).
