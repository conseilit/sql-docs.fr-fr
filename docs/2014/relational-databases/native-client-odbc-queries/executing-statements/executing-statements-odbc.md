---
title: Exécution d’instructions (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC]
- ODBC applications, statements
- statements [ODBC], executing
ms.assetid: 063fc40d-ff81-490d-9c9b-2faefb729f37
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4d3d25e94926e3b87dab198c567c1f813732a2f9
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48180269"
---
# <a name="executing-statements-odbc"></a>Exécution d'instructions (ODBC)
  Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client propose différentes méthodes pour exécuter des instructions SQL dans un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] base de données :  
  
-   Exécution directe  
  
-   Exécution préparée  
  
 L’exécution directe implique génération d’une chaîne de caractères contenant un [!INCLUDE[tsql](../../../includes/tsql-md.md)] instruction et sa soumission pour exécution en utilisant le **SQLExecDirect** (fonction). L'exécution préparée implique la génération d'une chaîne de caractères contenant une instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] et son exécution en deux étapes. La première étape utilise la [SQLPrepare, fonction](http://go.microsoft.com/fwlink/?LinkId=59360) (fonction) pour analyser et compiler le plan d’exécution de l’instruction dans le [!INCLUDE[ssDE](../../../includes/ssde-md.md)]. La deuxième étape utilise la **SQLExecute** fonction à exécuter le plan d’exécution préparé précédemment. Cela permet de réduire la charge d'analyse et de compilation pour chaque exécution. L'exécution préparée est couramment utilisée par les applications pour exécuter de manière répétée la même instruction SQL paramétrable.  
  
 Les exécutions directe et préparée peuvent exécuter une instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] unique ou un lot d'instructions SQL, ou elles peuvent appeler une procédure stockée.  
  
## <a name="in-this-section"></a>Dans cette section  
  
-   [Exécution directe](direct-execution.md)  
  
-   [Exécution préparée](prepared-execution.md)  
  
-   [Procédures](procedures.md)  
  
-   [Lots d’instructions](batches-of-statements.md)  
  
-   [Effets des options ISO](effects-of-iso-options.md)  
  
## <a name="see-also"></a>Voir aussi  
 [L’exécution de requêtes &#40;ODBC&#41;](../executing-queries-odbc.md)  
  
  
