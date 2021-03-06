---
title: Administrer une base de données du serveur de rapports (SSRS en mode natif) | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], databases
- renaming databases
- report server database
- databases [Reporting Services], administering
- reportservertempdb
- reportserver database
ms.assetid: 97b2e1b5-3869-4766-97b9-9bf206b52262
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 21f641d9bb33c918e8194ac7ed02af8c4c9469db
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48193259"
---
# <a name="administer-a-report-server-database-ssrs-native-mode"></a>Administrer une base de données du serveur de rapports (SSRS en mode natif)
  Un déploiement de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] utilise deux bases de données relationnelles [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour le stockage interne. Par défaut, les bases de données ont pour nom respectif Reportserver et ReportServerTempdb. La base de données ReportServerTempdb est créée à l'aide de la base de données du serveur de rapports primaire et sert à stocker les données temporaires, les informations de session et les rapports mis en mémoire cache.  
  
 Dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], les tâches d'administration de base de données consistent à sauvegarder et à restaurer les bases de données du serveur de rapports et à gérer les clés de chiffrement qui permettent de chiffrer et de déchiffrer les données sensibles.  
  
 Pour administrer les bases de données du serveur de rapports, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] met une série d’outils à votre disposition.  
  
-   Pour sauvegarder ou restaurer la base de données du serveur de rapports ou encore la déplacer ou la récupérer, vous pouvez utiliser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], les commandes [!INCLUDE[tsql](../../includes/tsql-md.md)] ou les utilitaires d’invite de commandes de base de données. Pour obtenir des instructions, consultez [Déplacement des bases de données du serveur de rapports vers un autre ordinateur &#40;SSRS en mode natif&#41;](moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) dans la documentation en ligne de SQL Server.  
  
-   Pour copier le contenu d'une base de données dans une autre base de données du serveur de rapports, vous pouvez attacher une copie d'une base de données du serveur de rapports et l'utiliser avec une autre instance du serveur de rapports. Ou encore, vous pouvez créer et exécuter un script qui utilise des appels SOAP pour recréer le contenu du serveur de rapports dans une nouvelle base de données. Vous pouvez utiliser l’utilitaire **rs** pour exécuter le script.  
  
-   Pour gérer les connexions entre le serveur de rapports et la base de données connexe et pour déterminer quelle base de données utilise une instance de serveur de rapports particulière, utilisez la page Installation de la base de données dans l'outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Pour en savoir plus sur la connexion de serveur de rapports à la base de données de serveur de rapports, consultez [configurer une connexion de base de données de serveur de rapports &#40;Gestionnaire de Configuration de SSRS&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md).  
  
## <a name="sql-server-login-and-database-permissions"></a>Autorisations de compte de connexion et de base de données SQL Server  
 Les bases de données du serveur de rapports sont utilisées en interne par le serveur de rapports. Les connexions à une base de données sont opérées par le service Report Server. Vous devez utiliser l’outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] pour configurer la connexion du serveur de rapports à la base de données du serveur de rapports.  
  
 Les informations d’identification de la connexion du serveur de rapports à la base de données peuvent être celles du compte de service, d’un compte d’utilisateur local ou de domaine Windows ou d’un utilisateur de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Vous devez choisir un compte existant pour la connexion ; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ne crée pas de comptes à votre place.  
  
 Une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à la base de données du serveur de rapports est créée automatiquement pour le compte que vous spécifiez.  
  
 Les autorisations d'accès à la base de données sont également configurées automatiquement. L’outil de Configuration de Reporting Services attribue l’utilisateur de compte ou de la base de données de la `Public` et `RSExecRole` rôles pour les bases de données de serveur de rapports. Le `RSExecRole` fournit les autorisations pour accéder aux tables de base de données et d’exécuter des procédures stockées. Le `RSExecRole` est créé dans master et msdb lorsque vous créez la base de données de serveur de rapports. Le `RSExecRole` est un membre de la `db_owner` rôle pour les bases de données, ce qui permet de mettre à jour son propre schéma pour prendre en charge un processus de mise à niveau automatique, le serveur de rapports.  
  
## <a name="naming-conventions-for-the-report-server-databases"></a>Conventions d'affectation des noms pour les bases de données du serveur de rapports  
 Au moment de créer la base de données primaire, le nom de la base de données doit respecter les règles spécifiées pour les [identificateurs de la base de données](../../relational-databases/databases/database-identifiers.md). La base de données temporaire utilise toujours le même nom que la base de données primaire du serveur de rapports mais avec le suffixe Tempdb. Vous ne pouvez pas choisir un autre nom pour la base de données temporaire.  
  
 Le changement de nom des bases de données de serveur de rapports n'est pas pris en charge car ces bases de données sont considérées comme des composants internes. Renommer des bases de données de serveur de rapports entraîne des erreurs. Si vous renommez la base de données primaire, un message d'erreur explique que les noms des bases de données ne sont plus synchronisés. Si vous renommez la base de données ReportServerTempdb, l'erreur interne suivante se produit ultérieurement lorsque vous exécutez les rapports :  
  
 « Une erreur interne s'est produite sur le serveur de rapports. Consultez le journal des erreurs pour plus d'informations. (rsInternalError)  
  
 Nom d'objet 'ReportServerTempDB.dbo.PersistedStream' non valide. »  
  
 Cette erreur se produit car le nom ReportServerTempdb est stocké en interne et utilisé par des procédures stockées pour effectuer des opérations internes. Renommer la base de données temporaire empêche le bon fonctionnement des procédures stockées.  
  
## <a name="enabling-snapshot-isolation-on-the-report-server-database"></a>Activation de l'isolement d'instantané sur la base de données du serveur de rapports  
 Vous ne pouvez pas activer l'isolement d'instantané sur la base de données du serveur de rapports. Si l'isolement d'instantané est activé, l'erreur suivante s'affiche : « Le rapport sélectionné n'est pas prêt pour être affiché. Le rendu du rapport n'est pas terminé ou son instantané n'est pas disponible ».  
  
 Si vous n’avez pas intentionnellement activé l’isolement d’instantané, il est possible que l’attribut ait été défini par une autre application ou que l’isolement d’instantané soit activé sur la base de données **model** ; dans ce dernier cas, toutes les nouvelles bases de données héritent du paramètre.  
  
 Pour désactiver l'isolement d'instantané sur la base de données du serveur de rapports, démarrez Management Studio, ouvrez une nouvelle fenêtre de requête, collez puis exécutez le script suivant :  
  
```  
ALTER DATABASE ReportServer  
SET ALLOW_SNAPSHOT_ISOLATION OFF  
ALTER DATABASE ReportServerTempdb  
SET ALLOW_SNAPSHOT_ISOLATION OFF  
ALTER DATABASE ReportServer  
SET READ_COMMITTED_SNAPSHOT OFF  
ALTER DATABASE ReportServerTempDb  
SET READ_COMMITTED_SNAPSHOT OFF  
```  
  
## <a name="about-database-versions"></a>À propos des versions de base de données  
 Dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], aucune information explicite n’est disponible sur la version de la base de données. Toutefois, comme les versions des bases de données sont toujours synchronisées avec les versions des produits, vous pouvez utiliser les informations de version d'un produit pour savoir quand la version de base de données a changé. Informations de version de produit pour [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sont indiquées dans les informations de version de fichier qui s’affiche dans les fichiers journaux, dans les en-têtes de tous les appels SOAP, et lorsque vous vous connectez à l’URL de serveur de rapports (par exemple, lorsque vous ouvrez un navigateur pour http://localhost/reportserver).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestionnaire de Configuration de Reporting Services &#40;en Mode natif&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)   
 [Créer une base de données du serveur de rapports en Mode natif &#40;Gestionnaire de Configuration de SSRS&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)   
 [Configurer le compte de Service Report Server &#40;Gestionnaire de Configuration de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)   
 [Configurer une connexion de base de données de serveur de rapports &#40;Gestionnaire de Configuration de SSRS&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)   
 [Créer une base de données de serveur de rapports &#40;Gestionnaire de Configuration de SSRS&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)   
 [Opérations de sauvegarde et de restauration pour Reporting Services](../install-windows/backup-and-restore-operations-for-reporting-services.md)   
 [Serveur de base de données rapports &#40;SSRS en Mode natif&#41;](report-server-database-ssrs-native-mode.md)   
 [Serveur de rapports Reporting Services &#40;mode natif&#41;](reporting-services-report-server-native-mode.md)   
 [Stocker des données chiffrées du serveur de rapports &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md)   
 [Configurer et gérer les clés de chiffrement &#40;Gestionnaire de Configuration de SSRS&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md)  
  
  
