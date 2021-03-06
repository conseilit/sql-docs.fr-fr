---
title: Rôle d’installation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
ms.assetid: c7e9db15-89f2-4d4d-8860-1e64c5821c4d
author: heidisteen
ms.author: heidist
manager: craigg
ms.openlocfilehash: 77a3e61d36ce9661a9b01095c868c7d54de81f0a
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48130559"
---
# <a name="setup-role"></a>Rôle d'installation
  Utilisez cette page pour spécifier s'il convient d'utiliser la page Sélection de fonctionnalités pour sélectionner des fonctionnalités individuelles, ou de procéder à l'installation à l'aide d'un rôle d'installation.  
  
 Un `setup role` est une sélection fixe de toutes les fonctionnalités et des composants partagés qui sont requis pour implémenter une configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prédéfinie.  
  
## <a name="options"></a>Options  
 **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation de fonctionnalités**  
 Choisissez cette option pour sélectionner des fonctionnalités individuelles et des composants partagés. Les fonctionnalités de l'instance incluent les services de moteur de base de données, Analysis Services (mode natif) et Reporting Services.  
  
 **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerPivot pour SharePoint**  
 Choisissez cette option pour installer les composants serveur Analysis Services dans une batterie de serveurs SharePoint 2010. Cette option déploie le service système PowerPivot et le serveur Analysis Services dans une batterie, ce qui active le traitement des requêtes et des données à grande échelle pour les classeurs Excel publiés qui contiennent des données [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] incorporées.  
  
 Vous pouvez éventuellement ajouter une instance de moteur de base de données relationnelle à votre installation si vous voulez qu'elle héberge des bases de données dans une batterie SharePoint. Si la batterie est déjà configurée, vous pouvez ignorer cette option.  
  
 Une fois l'installation terminée, vous devez configurer le logiciel à l'aide de l'une des méthodes suivantes : outil de configuration PowerPivot, applets de commande PowerShell ou Administration centrale de SharePoint 2010. Contrairement aux versions antérieures, le programme d'installation n'effectue plus les tâches de configuration pour une installation PowerPivot.  
  
 Une installation basée sur les rôles n'inclut pas l'application cliente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerPivot pour Excel. L'application cliente est installée séparément.  
  
 **Toutes les fonctionnalités avec les valeurs par défaut**  
 Choisissez ce rôle d'installation pour installer toutes les fonctionnalités qui sont disponibles pour cette version. Notez que PowerPivot pour SharePoint est exclu de ce rôle. Vous devez utiliser le rôle d'installation PowerPivot pour SharePoint pour installer cette fonctionnalité.  
  
 Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] est configuré pour démarrer à l’aide de la **NT AUTHORITY\NETWORK SERVICE** compte. L’utilisateur actuel sera configuré en tant que membre de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **sysadmin** rôle. Les valeurs définies par cette option peuvent être remplacées en spécifiant des paramètres de ligne de commande supplémentaires.  
  
 Lorsque le système d'exploitation n'est pas un contrôleur de domaine, par défaut, le moteur de base de données et Reporting Services utiliseront le compte NTAUTHORITY\NETWORK SERVICE, Integration Services utilisera le compte NTAUTHORITY\NETWORK SERVICE et le Lanceur de démon de filtre de texte intégral SQL utilisera le compte NTAUTHORITY\LOCAL SERVICE.  
  
## <a name="see-also"></a>Voir aussi  
 [Installation de PowerPivot pour SharePoint](http://go.microsoft.com/fwlink/?LinkId=206906)   
 [Configurations matérielle et logicielle requises (PowerPivot pour SharePoint](http://go.microsoft.com/fwlink/?LinkId=216823)   
 [Sélection de fonctionnalités](../../../2014/sql-server/install/feature-selection.md)  
  
  
