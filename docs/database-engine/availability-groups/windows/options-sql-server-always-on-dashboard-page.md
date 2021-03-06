---
title: Options (SQL Server Always On, page Tableau de bord) | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Alwayson.Dashboard
ms.assetid: 4369b588-e982-4b57-80a1-beb2e879ce0b
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: d79165eae0ccbc1e5c442849c5df0ef83d4f1e90
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47773247"
---
# <a name="options-sql-server-always-on-dashboard-page"></a>Options (SQL Server Always On, page Tableau de bord)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Utilisez la page **Tableau de bord SQL Server Always On** de la boîte de dialogue [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Options** pour configurer le tableau de bord AlwaysOn.  
  
 **Pour accéder à cette page :**  
  
 Dans le menu **Outils** , cliquez sur **Options**, développez le dossier **SQL Server Always On** , puis cliquez sur **Tableau de bord**.  
  
## <a name="on-this-page"></a>Sur cette page  
 **Activez l'actualisation automatique.**  
 Cliquez pour activer l'actualisation automatique. Les options sont :  
  
-   Le champ **Intervalle d’actualisation (en secondes)** affiche le nombre de secondes auquel le tableau de bord sera actualisé. La valeur par défaut est 30. Lorsque l'actualisation automatique est activée, vous pouvez modifier ce champ afin de changer l'intervalle d'actualisation.  
  
-   Le **Nombre de nouvelles tentatives de connexion** affiche le nombre de fois que le tableau de bord essaie de se connecter à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge un réplica de disponibilité pour un groupe de disponibilité surveillé par le tableau de bord. La valeur par défaut est 65535. Lorsque l'actualisation automatique est activée, vous pouvez modifier ce champ afin de changer le nombre de nouvelles tentatives de connexion.  
  
 **Activez votre stratégie Always On définie par l’utilisateur.**  
 Si vous avez défini votre propre stratégie Always On, cliquez sur cette option pour activer cette stratégie.  
  
## <a name="see-also"></a> Voir aussi  
 [Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
