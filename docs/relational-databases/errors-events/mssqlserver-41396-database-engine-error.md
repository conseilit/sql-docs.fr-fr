---
title: MSSQLSERVER_41396 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 41396 (Database Engine error)
ms.assetid: 4ff04042-8367-46f3-8a16-c94682d6eedb
caps.latest.revision: 8
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 1138b36fa3426407b29d928defe7a65179049db0
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver41396"></a>MSSQLSERVER_41396
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|ID d'événement|41396|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|MAX_SORT_ROWS_EXCEEDED|  
|Texte du message|L'opération de tri a dépassé la limite de la mémoire tampon. L'exécution de la procédure stockée a été abandonnée. Consultez la documentation en ligne de SQL Server pour plus d'informations.|  
  
## <a name="explanation"></a>Explication  
Les procédures stockées compilées en mode natif effectuent des opérations de tri en mémoire. Il existe une limite sur la taille du tampon de tri. Cette erreur indique que la taille du tampon de tri dépasse cette limite. L'opération de tri et l'exécution de la procédure stockée ont été abandonnées.  
  
La taille de chaque ligne ou entrée dans le tampon de tri est déterminée par le nombre de lignes triées ainsi que par le nombre de jointures et le nombre et le type de fonctions d'agrégation dans la requête. En simplifiant la requête, vous pouvez réduire la taille de chaque ligne, afin de pouvoir faire tenir plus de lignes dans le tampon de tri. La taille des lignes dans les tables de base n'affecte pas la taille de chaque ligne ou entrée dans le tampon de tri.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Sélectionnez moins de lignes ou diminuez la complexité de la requête en supprimant des jointures ou des fonctions d'agrégation.  
  
## <a name="see-also"></a>Voir aussi  
[OLTP en mémoire &#40;Optimisation en mémoire&#41;](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
