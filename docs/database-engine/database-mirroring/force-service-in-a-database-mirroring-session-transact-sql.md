---
title: "Forcer le service dans une session de mise en miroir de bases de données (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-high-availability
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forced service [SQL Server]
- database mirroring [SQL Server], forcing service
ms.assetid: 8b6ffe77-35f3-4e2a-a658-8a38a8e1c794
caps.latest.revision: 40
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 41aad1711fe5fb6743cfc6c1527f8c175fbf1d0c
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="force-service-in-a-database-mirroring-session-transact-sql"></a>Forcer le service dans une session de mise en miroir de bases de données (Transact-SQL)
  En mode haute performance et en mode haute sécurité sans basculement automatique, si le serveur principal tombe en panne alors que le serveur miroir est disponible, le propriétaire de la base de données peut rendre la base de données disponible en imposant le basculement (avec d'éventuelles pertes de données) vers la base de données miroir. Cette option est disponible uniquement si toutes les conditions suivantes sont remplies :  
  
-   Le serveur principal est hors service.  
  
-   WITNESS est défini à OFF ou est connecté au serveur miroir.  
  
> [!CAUTION]  
>  Le service forcé constitue strictement une méthode de récupération après sinistre. Le basculement forcé peut impliquer une perte de données. Par conséquent, ne forcez le basculement que si vous acceptez le risque d'une perte de données afin de restaurer immédiatement l'accès à la base de données. Dans le cas où un service forcé risque d'entraîner des pertes de données importantes, nous vous recommandons d'arrêter la mise en miroir et de resynchroniser manuellement les bases de données. Pour plus d’informations sur les risques de forcer le service, consultez [Modes de fonctionnement de la mise en miroir de bases de données](../../database-engine/database-mirroring/database-mirroring-operating-modes.md).  
  
 Un service forcé suspend la session et démarre un nouveau branchement de récupération. L'effet d'un service forcé est similaire à la suppression d'une mise en miroir et la récupération de la base de données principale initiale. Cependant, un service forcé facilite la resynchronisation des bases de données (avec possibilité de perte de données) à la reprise de la mise en miroir.  
  
### <a name="to-force-service-in-a-database-mirroring-session"></a>Pour forcer le basculement dans une session de mise en miroir de bases de données  
  
1.  Connectez-vous au serveur miroir.  
  
2.  Émettez l'instruction suivante :  
  
     ALTER DATABASE *<nom_base_de_données>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS  
  
     où *nom_base_de_données* spécifie la base de données mise en miroir.  
  
     Le serveur miroir devient immédiatement le serveur principal et la mise en miroir est suspendue.  
  
## <a name="see-also"></a>Voir aussi  
 [ALTER DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql.md)   
 [Modes de fonctionnement de la mise en miroir de bases de données](../../database-engine/database-mirroring/database-mirroring-operating-modes.md)  
  
  