---
title: Database Mail XPs (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Mail XPs option
- Database Mail [SQL Server], enabling
ms.assetid: e22c4e63-1792-473b-af11-14a7931ca9ed
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 9be979999553bb5fc930ddab573ec96f7ff17a4d
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48064749"
---
# <a name="database-mail-xps-server-configuration-option"></a>Database Mail XPs (option de configuration de serveur)
  Utilisez **l’option** pour activer la messagerie de base de données sur ce serveur. Les valeurs possibles sont les suivantes :  
  
-   **0** indique que la messagerie de base de données n’est pas disponible (valeur par défaut).  
  
-   **1** indique que la messagerie de base de données est disponible.  
  
 Le paramètre prend effet immédiatement, sans arrêt et redémarrage du serveur.  
  
 Après avoir activé la messagerie de base de données, vous devez configurer une base de données hôte afin qu'elle utilise la messagerie de base de données.  
  
 La configuration de la messagerie de base de données à l’aide de l’ **Assistant Configuration de la messagerie de base de données** active les procédures stockées étendues de la messagerie de base de données dans la base de données **msdb** . Si vous utilisez l’ **Assistant Configuration de la messagerie de base de données**, il n’est pas nécessaire d’utiliser l’exemple **sp_configure** ci-dessous.  
  
 Si l’option **Database Mail XPs** a la valeur 0, la messagerie de base de données ne démarre pas. Si elle est en cours d’exécution lorsque la valeur 0 est affectée à l’option, elle continue de s’exécuter et d’envoyer des messages jusqu’à ce qu’elle soit inactive pendant la durée configurée dans l’option **DatabaseMailExeMinimumLifeTime** .  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant active les procédures stockées étendues de la messagerie de base de données.  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Database Mail XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Messagerie de base de données](../../relational-databases/database-mail/database-mail.md)  
  
  
