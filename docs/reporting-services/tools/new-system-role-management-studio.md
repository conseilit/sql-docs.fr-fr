---
title: "Nouveau rôle système (Management Studio) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.reportserver.newsystemrole.f1
ms.assetid: 7b4a0b98-975b-478a-8359-7db39ccbb347
caps.latest.revision: 28
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: f4917fea7fbaa0f652287a08e0a3a5727feaad9e
ms.contentlocale: fr-fr
ms.lasthandoff: 08/09/2017

---
# <a name="new-system-role-management-studio"></a>Nouveau rôle système (Management Studio)
  Utilisez cette page pour créer une définition de rôle au niveau système. Une définition de rôle système spécifie un ensemble de tâches au niveau système qui s'appliquent à l'ensemble du serveur de rapports.  
  
> [!NOTE]  
>  Les définitions de rôles sont utilisées uniquement sur un serveur de rapports qui s'exécute en mode natif. Si le serveur de rapports est configuré pour l'intégration SharePoint, cette page n'est pas disponible.  
  
## <a name="options"></a>Options  
 **Nom**  
 Tapez le nom de la définition de rôle. Un nom de définition de rôle doit être unique dans l'espace de noms du serveur de rapports. Le nom doit contenir un caractère alphanumérique au minimum. Il peut également comporter des espaces et quelques symboles. N'utilisez pas les caractères suivants dans le nom :  
  
 ; ? : @ & = + , $ / * < >  
  
 " /  
  
 **Description**  
 Fournit une description qui explique l'utilisation du rôle et énumère les éléments pris en charge par ce dernier.  
  
 **Tâche**  
 Sélectionnez les tâches au niveau système qui peuvent être effectuées par ce rôle. Vous ne pouvez pas créer de nouvelles tâches ni modifier les tâches existantes qui sont prises en charge par [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Vous ne pouvez pas choisir des tâches au niveau élément pour la définition d'un rôle système.  
  
 **Description de la tâche**  
 Affiche une description de la tâche qui énumère les opérations ou les autorisations prises en charge par cette dernière.  
  
## <a name="see-also"></a>Voir aussi  
 [Serveur de rapports dans l’aide de Management Studio (F1)](../../reporting-services/tools/report-server-in-management-studio-f1-help.md)   
 [Définitions de rôles](../../reporting-services/security/role-definitions.md)  
  
  
