---
title: L’état de synchronisation des données d’une base de données de disponibilité n’est pas sain | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 89f95d15-33c6-4768-bccd-9dbf8c4f49a9
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: dc9f7dadf5a395c8b0973566e03d4868f82b4863
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48087912"
---
# <a name="data-synchronization-state-of-some-availability-database-is-not-healthy"></a>L'état de synchronisation des données d'une base de données de disponibilité n'est pas sain
    
## <a name="introduction"></a>Introduction  
  
|||  
|-|-|  
|**Nom de la stratégie**|État de synchronisation des données du réplica de disponibilité|  
|**Problème**|L'état de synchronisation des données d'une base de données de disponibilité n'est pas sain.|  
|**Catégorie**|**Avertissement**|  
|**Facette**|Réplica de disponibilité|  
  
## <a name="description"></a>Description  
 Cette stratégie vérifie l'état de synchronisation des données de la base de données de disponibilité (également appelée « réplica de base de données »). La stratégie se trouve dans un état non sain lorsque l'état de synchronisation de données est NOT SYNCHRONIZING ou que l'état du réplica de base de données à validation synchrone n'est pas SYNCHRONIZED.  
  
> [!NOTE]  
>  Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], vous trouverez des informations sur les causes et les solutions possibles dans la page [L’état de synchronisation des données d’une base de données de disponibilité n’est pas sain](http://go.microsoft.com/fwlink/p/?LinkId=220863) sur le wiki TechNet.  
  
## <a name="possible-causes"></a>Causes possibles  
 Au moins une base de données de disponibilité sur le réplica a un état de synchronisation des données non sain. S'il s'agit d'un réplica de disponibilité en validation asynchrone, toutes les bases de données de disponibilité doivent être dans l'état SYNCHRONIZING. S'il s'agit d'un réplica de disponibilité à validation synchrone, toutes les bases de données de disponibilité doivent être dans l'état SYNCHRONIZED. Ce problème peut avoir les causes suivantes :  
  
-   Le réplica de disponibilité est peut-être déconnecté.  
  
-   Le déplacement des données est peut-être suspendu.  
  
-   La base de données n'est peut-être pas accessible.  
  
-   Il peut exister un problème de délai temporaire en raison de la latence réseau ou de la charge sur le réplica principal ou secondaire.  
  
## <a name="possible-solution"></a>Solution possible  
 Résolvez tout problème de connexion ou de suspension du déplacement des données. Vérifiez les événements liés à ce problème à l'aide de SQL Server Management Studio et recherchez l'erreur de base de données. Suivez les étapes de résolution spécifiques à cette erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble des groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
