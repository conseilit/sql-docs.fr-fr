---
title: Propriétés du serveur (page Général) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.general.f1
ms.assetid: 23537d52-4356-450f-a671-5921cef2431f
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: af0db1ac3d03fa03ea7bb3267656597d164c5302
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48222207"
---
# <a name="server-properties-general-page"></a>Propriétés du serveur (page Général)
  Utilisez cette page pour afficher ou modifier le titre utilisé dans le Gestionnaire de rapports, activer ou désactiver Mes rapports, sélectionner une définition de rôle pour la sécurité de Mes rapports, et activer ou désactiver le contrôle d'impression du client.  
  
 Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], se connecter à une instance de serveur de rapports, cliquez sur le nom de serveur de rapports, puis sélectionnez **propriétés**.  
  
 Le mode serveur détermine les propriétés de serveur que vous pouvez définir. Si vous gérez un serveur de rapports configuré pour le mode intégré SharePoint, vous ne pouvez pas activer Mes rapports ou définir le titre d'application pour le Gestionnaire de rapports.  
  
## <a name="options"></a>Options  
 **Nom**  
 Tapez le nom de l'application, qui s'affiche dans le Gestionnaire de rapports. Par défaut, il s’agit de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Le nom que vous spécifiez s'affiche uniquement dans le Gestionnaire de rapports.  
  
 **Version**  
 Cette propriété est en lecture seule. Spécifie la version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que vous utilisez.  
  
 **Édition**  
 Cette propriété est en lecture seule. Spécifie l'instance de serveur de rapports actuelle. Le Gestionnaire de rapports n’est pas disponible dans certaines éditions de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).  
  
 **Mode d'authentification**  
 Cette propriété est en lecture seule. Elle identifie les types de demandes d'authentification acceptés par l'instance de serveur de rapports. Pour changer le mode d'authentification, vous devez modifier le fichier RSReportServer.config. Pour plus d’informations, consultez [Authentification avec le serveur de rapports](../security/authentication-with-the-report-server.md).  
  
 **URL**  
 Cette propriété est en lecture seule. Indique l'URL vers le service Web Report Server. Cette valeur est spécifiée dans l’outil de configuration [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] . Pour plus d’informations, consultez [Configurer une URL &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/configure-a-url-ssrs-configuration-manager.md).  
  
 **Activer un dossier Mes rapports pour chaque utilisateur**  
 Mettez Mes rapports à la disposition des utilisateurs. Cette option est disponible uniquement pour les serveurs de rapports en mode natif.  
  
 **Sélectionner le rôle à appliquer à chaque dossier Mes Rapports**  
 Spécifiez une définition de rôle à utiliser pour la sécurité de Mes rapports. La définition de rôle identifie l'ensemble des tâches qui sont prises en charge dans chaque dossier Mes rapports.  
  
 **Activer le téléchargement pour le contrôle d’impression client ActiveX**  
 Définit le `EnableClientPrinting` propriété système du serveur de rapports. Si vous activez l'impression côté client, les utilisateurs qui disposent d'autorisations d'administrateur local peuvent télécharger un contrôle ActiveX signé pour imprimer les rapports HTML. Pour plus d’informations, consultez [activer et désactiver l’impression côté Client pour Reporting Services](../report-server/enable-and-disable-client-side-printing-for-reporting-services.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Définir les propriétés du serveur de rapports &#40;Management Studio&#41;](set-report-server-properties-management-studio.md)   
 [Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md)   
 [Activer et désactiver Mes rapports](../report-server/enable-and-disable-my-reports.md)   
 [Aide du serveur de rapports dans Management Studio accessible par la touche F1](report-server-in-management-studio-f1-help.md)   
 [Sécuriser Mes Rapports](../security/secure-my-reports.md)  
  
  
