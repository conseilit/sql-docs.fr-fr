---
title: Déployer une application de la couche Données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.deploydacwizard.updateconfiguration.f1
- sql12.swb.deploydacwizard.selectdac.f1
- sql12.swb.deploydacwizard.deploydac.f1
- sql12.swb.deploydacwizard.introduction.f1
- sql12.swb.deploydacwizard.summary.f1
helpviewer_keywords:
- Deploy data-tier application
- deploy DAC
- data-tier application [SQL Server], deploy
- How to [DAC], deploy
- wizard [DAC], deploy
ms.assetid: c117af35-aa53-44a5-8034-fa8715dc735f
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ad76099b7cc6386e20b8c46f300298a13492f32b
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48104929"
---
# <a name="deploy-a-data-tier-application"></a>Déployer une application de la couche Données
  Vous pouvez déployer une application de la couche Données (DAC) sur une instance existante du [!INCLUDE[ssDE](../../includes/ssde-md.md)] ou de [!INCLUDE[ssSDS](../../includes/sssds-md.md)] à l'aide d'un Assistant ou d'un script PowerShell. Le processus de déploiement inscrit une instance DAC en stockant la définition de la DAC dans la base de données système **msdb** (**master** dans [!INCLUDE[ssSDS](../../includes/sssds-md.md)]), crée une base de données, puis remplit la base de données avec tous les objets de base de données définis dans la DAC.  
  
-   **Avant de commencer :**  [Utilitaire SQL Server](#SQLUtility), [Options et paramètres de base de données](#DBOptSettings), [Limitations et restrictions](#LimitationsRestrictions), [Conditions préalables](#Prerequisites), [Sécurité](#Security), [Autorisations](#Permissions)  
  
-   **Pour déployer une DAC en utilisant :**  [l’Assistant Déployer une application de la couche Données](#UsingDeployDACWizard), [PowerShell](#DeployDACPowerShell)  
  
##  <a name="BeforeBegin"></a> Avant de commencer  
 Un même package DAC peut être déployé plusieurs fois sur une instance unique du [!INCLUDE[ssDE](../../includes/ssde-md.md)] , mais les déploiements doivent être exécutés un par un. Le nom d'instance DAC spécifié pour chaque déploiement doit être unique dans l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
###  <a name="SQLUtility"></a> Utilitaire SQL Server  
 Si vous déployez une DAC dans une instance gérée du moteur de base de données, la DAC déployée est incorporée dans l'utilitaire SQL Server lorsque le jeu d'éléments de collecte de l'utilitaire est envoyé de l'instance au point de contrôle de l'utilitaire. La DAC sera ensuite présente dans le nœud **Applications de la couche Données déployées** dans l’ [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** and reported in the **Applications de la couche Données déployées** details page.  
  
###  <a name="DBOptSettings"></a> Options et paramètres de bases de données  
 Par défaut, la base de données créée pendant le déploiement aura tous les paramètres par défaut de l'instruction CREATE DATABASE, sauf pour les exceptions suivantes :  
  
-   Le classement et le niveau de compatibilité de la base de données sont définis avec les valeurs définies dans le package DAC. Un package DAC créé à partir d'un projet de base de données dans les outils de développement de SQL Server utilise les valeurs définies dans le projet de base de données. Un package extrait d'une base de données existante utilise les valeurs de la base de données d'origine.  
  
-   Vous pouvez ajuster quelques-uns des paramètres de la base de données, tels que le nom de la base de données et les chemins d'accès aux fichiers, dans la page **Mettre à jour la configuration** . Vous ne pouvez pas définir les chemins d'accès aux fichiers lors du déploiement vers [!INCLUDE[ssSDS](../../includes/sssds-md.md)].  
  
 Certaines options de base de données, telles que TRUSTWORTHY, DB_CHAINING et HONOR_BROKER_PRIORITY, ne peuvent pas être ajustées dans le cadre du processus de déploiement. Des propriétés physiques, telles que le nombre de groupes de fichiers ou le nombre et la taille des fichiers, ne peuvent pas être modifiées dans le cadre du processus de déploiement. Une fois le déploiement terminé, vous pouvez utiliser l'instruction ALTER DATABASE, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell pour personnaliser la base de données.  
  
###  <a name="LimitationsRestrictions"></a> Limitations et restrictions  
 Une DAC peut être déployée vers [!INCLUDE[ssSDS](../../includes/sssds-md.md)]ou une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] qui exécute [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) ou version ultérieure. Si vous créez une DAC à l'aide d'une version ultérieure, elle peut contenir des objets non pris en charge par [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]. Vous ne pouvez pas déployer ces DAC vers les instances de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].  
  
###  <a name="Prerequisites"></a> Conditions préalables  
 Nous vous recommandons de ne pas déployer un package DAC provenant de sources inconnues ou non approuvées. De tels packages peuvent contenir du code malveillant susceptible d'exécuter un code Transact-SQL indésirable ou de provoquer des erreurs en modifiant le schéma. Avant d'utiliser un package provenant d'une source inconnue ou non approuvée, décompressez la DAC et vérifiez le code, par exemple les procédures stockées ou autre code défini par l'utilisateur. Pour plus d’informations sur la façon de procéder à ces vérifications, consultez [Valider un package DAC](validate-a-dac-package.md).  
  
###  <a name="Security"></a> Sécurité  
 Pour améliorer la sécurité, les connexions d'authentification SQL Server sont stockées dans un package DAC sans mot de passe. Lorsque le package est déployé ou mis à niveau, la connexion est créée en tant que connexion désactivée avec un mot de passe généré. Pour activer les connexions, connectez-vous à l'aide d'une connexion qui possède l'autorisation ALTER ANY LOGIN et utilisez ALTER LOGIN pour activer la connexion et affecter un nouveau mot de passe pouvant être communiqué à l'utilisateur. Cela n'est pas nécessaire pour les connexions d'authentification Windows car leurs mots de passe ne sont pas gérés par SQL Server.  
  
####  <a name="Permissions"></a> Permissions  
 Une DAC ne peut être déployée que par les membres des rôles serveur fixes **sysadmin** ou **serveradmin** , ou par les connexions ayant le rôle serveur fixe **dbcreator** et disposant d'autorisations ALTER ANY LOGIN. Le compte d’administrateur système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intégré nommé **sa** peut aussi déployer une DAC. Le déploiement d'une DAC avec des connexions à [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requiert l'appartenance aux rôles loginmanager ou serveradmin. Le déploiement d'une DAC sans connexions à [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requiert l'appartenance aux rôles dbmanager ou serveradmin.  
  
##  <a name="UsingDeployDACWizard"></a> À l’aide de l’Assistant déployer une couche de données Application  
 **Pour déployer une DAC à l’aide d’un Assistant**  
  
1.  Dans l' **Explorateur d'objets**, développez le nœud pour l'instance vers laquelle vous voulez déployer la DAC.  
  
2.  Cliquez avec le bouton droit sur le nœud **Bases de données** , puis sélectionnez **Déployer une application de la couche Données...**.  
  
3.  Renseignez les boîtes de dialogue de l'Assistant :  
  
    -   [Page Introduction](#Introduction)  
  
    -   [Sélectionnez la Page du Package DAC](#Select_dac_package)  
  
    -   [Page Vérifier la stratégie](#Review_policy)  
  
    -   [Page de Configuration de mise à jour](#Update_configuration)  
  
    -   [Page Résumé](#Summary)  
  
    -   [Page déployer](#Deploy)  
  
##  <a name="Introduction"></a> Page Introduction  
 Cette page décrit les étapes de déploiement d'une application de la couche Données.  
  
 **Ne plus afficher cette page.** - Cochez la case pour ne plus afficher la page à l'avenir.  
  
 **Suivant >** : passe à la page **Sélectionner le package DAC**.  
  
 **Annuler** : met fin à l’Assistant sans déployer de DAC.  
  
##  <a name="Select_dac_package"></a> Sélectionnez la Page du Package DAC  
 Utilisez cette page pour spécifier le package DAC qui contient l'application de la couche Données à déployer. La page passe par trois états.  
  
### <a name="select-the-dac-package"></a>Sélectionner le package DAC  
 Utilisez l'état initial de la page pour choisir le package DAC à déployer. Le package de la DAC doit être un fichier de package de DAC valide et doit avoir une extension .dacpac.  
  
 **Package DAC** : spécifie le chemin et le nom de fichier du package DAC qui contient l’application de la couche Données à déployer. Vous pouvez sélectionner le bouton **Parcourir** à droite de la zone pour accéder à l'emplacement du package de DAC.  
  
 **Nom de l’application** : zone en lecture seule qui affiche le nom affecté à la DAC au moment où elle a été créée ou extraite d’une base de données.  
  
 **Version** : zone en lecture seule qui affiche la version affectée au moment où la DAC a été créée ou extraite d’une base de données.  
  
 **Description** : zone en lecture seule qui affiche la description écrite au moment où la DAC a été créée ou extraite d’une base de données.  
  
 **\< Précédent** : renvoie à la page **Introduction** .  
  
 **Suivant >** : affiche une barre de progression dès que l’Assistant confirme que le fichier sélectionné est un package DAC valide.  
  
 **Annuler** : met fin à l’Assistant sans déployer la DAC.  
  
### <a name="validating-the-dac-package"></a>Validation du package DAC  
 Affiche une barre de progression quand l'Assistant confirme que le fichier sélectionné est un package DAC valide. Si le package DAC est validé, l'Assistant passe à la dernière version de la page **Sélectionner un package** où vous pouvez examiner les résultats de la validation. Si le fichier n'est pas un package DAC valide, l'Assistant reste sur la page **Sélectionner le package DAC**. Sélectionnez un autre package DAC valide ou annulez l'Assistant et générez un nouveau package DAC.  
  
 **Validation du contenu de la DAC** : barre de progression qui indique l’état actuel de la validation.  
  
 **\< Précédent** -retourne à son état initial de la **sélectionner un Package** page.  
  
 **Suivant >** : passe à la dernière version de la page **Sélectionner un package**.  
  
 **Annuler** : met fin à l’Assistant sans déployer la DAC.  
  
##  <a name="Review_policy"></a> Page Vérifier la stratégie  
 Utilisez cette page pour vérifier les résultats de l'évaluation de la stratégie de sélection du serveur de la DAC, si la DAC a une stratégie. La stratégie de sélection du serveur de la DAC est facultative et est affectée à la DAC lorsque celle-ci est créée dans Visual Studio. La stratégie utilise les facettes de la stratégie de sélection du serveur pour spécifier les conditions que doit remplir une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] pour héberger la DAC.  
  
 **Résultats de l’évaluation des conditions de stratégie** : rapport en lecture seule indiquant si les conditions de la stratégie de déploiement de la DAC sont remplies. Les résultats de l'évaluation de chaque condition sont indiqués sur des lignes distinctes.  
  
 Les stratégies de sélection du serveur suivantes ont toujours la valeur False lors du déploiement d'une DAC vers [!INCLUDE[ssSDS](../../includes/sssds-md.md)]: version de système d'exploitation, langue, canaux nommés activés, plateforme et tcp activé.  
  
 **Ignorez les violations de stratégie** : utilisez cette case à cocher pour poursuivre le déploiement en cas d’échec d’une ou de plusieurs des conditions de stratégie. Ne sélectionnez cette option que si vous êtes sûr que toutes les conditions qui ont échoué n'empêcheront pas l'opération de la DAC de réussir.  
  
 **\< Précédent** -retourne à la **sélectionner un Package** page.  
  
 **Suivant >** : passe à la page **Mettre à jour la configuration**.  
  
 **Annuler** : met fin à l’Assistant sans déployer la DAC.  
  
##  <a name="Update_configuration"></a> Page de Configuration de mise à jour  
 Utilisez cette page pour spécifier les noms de l'instance DAC déployée et de la base de données créées par le déploiement, et pour définir des options de base de données.  
  
 **Nom de la base de données** : spécifie le nom de la base de données qui sera créée par le déploiement. La valeur par défaut est le nom de la base de données source d'où la DAC a été extraite. Le nom doit être unique dans l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et respecter les règles des identificateurs du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .  
  
 Si vous modifiez le nom de la base de données, les noms du fichier de données et des fichiers journaux changeront pour correspondre à la nouvelle valeur.  
  
 Le nom de la base de données est également utilisé comme nom de l'instance de la DAC. Le nom de l’instance est affiché sur le nœud de la DAC sous le nœud **Applications de la couche Données** dans l’ **Explorateur d’objets**ou sous le nœud **Applications de la couche Données déployées** dans l’ **Explorateur de l’utilitaire**.  
  
 Les options suivantes ne s'appliquent pas à [!INCLUDE[ssSDS](../../includes/sssds-md.md)]et ne sont pas affichées lors du déploiement vers [!INCLUDE[ssSDS](../../includes/sssds-md.md)].  
  
 **Utiliser l’emplacement de la base de données par défaut** : sélectionnez cette option pour créer les fichiers de données et les fichiers journaux de la base de données dans l’emplacement par défaut de l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Les noms de fichier seront composés à partir du nom de la base de données.  
  
 **Spécifier les fichiers de base de données** : sélectionnez cette option pour spécifier un emplacement ou un nom différent pour les fichiers de données et les fichiers journaux.  
  
 **Nom et chemin d’accès du fichier de données** : spécifie le chemin complet et le nom de fichier de la base de données. La zone est renseignée avec le chemin d'accès et le nom de fichier par défaut. Modifiez la chaîne dans la zone pour modifier la valeur par défaut ou utilisez le bouton Parcourir pour accéder au dossier où le fichier de données sera placé.  
  
 **Nom et chemin d’accès du fichier journal** : spécifie le chemin complet et le nom du fichier journal. La zone est renseignée avec le chemin d'accès et le nom de fichier par défaut. Modifiez la chaîne dans la zone pour modifier la valeur par défaut ou utilisez le bouton **Parcourir** pour accéder au dossier où le fichier journal sera placé.  
  
 **\< Précédent** -retourne à la **sélectionner le Package DAC** page.  
  
 **Suivant >** : passe à la page **Résumé**.  
  
 **Annuler** : met fin à l’Assistant sans déployer la DAC.  
  
##  <a name="Summary"></a> Page Résumé  
 Utilisez cette page pour vérifier les mesures que l'Assistant prendra lors du déploiement de la DAC.  
  
 **Les paramètres suivants seront utilisés pour déployer votre DAC.** - Vérifiez les informations affichées pour vous assurer que les actions prises seront correctes. La fenêtre affiche le package DAC que vous avez sélectionné et le nom que vous avez sélectionné pour l'instance DAC déployée. La fenêtre affiche également les paramètres qui seront utilisés lors de la création de la base de données associée à la DAC.  
  
 **\< Précédent** -vous renvoie à la **Configuration mise à jour** page pour modifier vos sélections.  
  
 **Suivant >** : déploie la DAC et affiche les résultats dans la page **Déployer une DAC**.  
  
 **Annuler** : met fin à l’Assistant sans déployer la DAC.  
  
##  <a name="Deploy"></a> Page déployer  
 Cette page signale la réussite ou l'échec de l'opération de déploiement.  
  
 **Déploiement de la DAC** : signale la réussite ou l’échec de chaque action entreprise pour déployer la DAC. Examinez les informations pour déterminer la réussite ou l'échec de chaque action. Toute action pour laquelle une erreur s'est produite aura un lien dans la colonne **Résultat** . Sélectionnez le lien pour consulter le rapport de d'erreur de cette action.  
  
 **Enregistrer le rapport** : sélectionnez ce bouton pour enregistrer le rapport de déploiement dans un fichier HTML. Le fichier signale l'état de chaque action, notamment toutes les erreurs générées par chacune des actions. Le dossier par défaut est le dossier SQL Server Management Studio\DAC Packages dans le dossier Documents de votre compte Windows.  
  
 **Terminer** : met fin à l’Assistant.  
  
##  <a name="DeployDACPowerShell"></a> Utilisation de PowerShell  
 **Pour déployer une DAC à l’aide de la méthode Install() dans un script PowerShell**  
  
1.  Créez un objet serveur SMO et affectez-lui l'instance à laquelle vous voulez déployer la DAC.  
  
2.  Ouvrir un `ServerConnection` de l’objet et de se connecter à la même instance.  
  
3.  Utilisez `System.IO.File` pour charger le fichier de package DAC.  
  
4.  Utilisez `add_DacActionStarted` et `add_DacActionFinished` pour vous abonner aux événements de déploiement de la DAC.  
  
5.  Définir le `DatabaseDeploymentProperties`.  
  
6.  Utilisez la méthode `DacStore.Install` pour déployer la DAC.  
  
7.  Fermez le flux de fichier utilisé pour lire le fichier de package DAC.  
  
### <a name="example-powershell"></a>Exemple (PowerShell)  
 L'exemple suivant déploie une DAC nommée MyApplication sur une instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)]en utilisant une définition de DAC d'un package de MyApplication.dacpac.  
  
```  
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = get-item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Load the DAC package file.  
$dacpacPath = "C:\MyDACs\MyApplication.dacpac"  
$fileStream = [System.IO.File]::Open($dacpacPath,[System.IO.FileMode]::OpenOrCreate)  
$dacType = [Microsoft.SqlServer.Management.Dac.DacType]::Load($fileStream)  
  
## Subscribe to the DAC deployment events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Deploy the DAC and create the database.  
$dacName  = "MyApplication"  
$evaluateTSPolicy = $true  
$deployProperties = New-Object Microsoft.SqlServer.Management.Dac.DatabaseDeploymentProperties($serverconnection,$dacName)  
$dacstore.Install($dacType, $deployProperties, $evaluateTSPolicy)  
$fileStream.Close()  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Applications de la couche Données](data-tier-applications.md)   
 [Extraire une DAC d'une base de données](extract-a-dac-from-a-database.md)   
 [Identificateur de la base de données](../databases/database-identifiers.md)  
  
  
