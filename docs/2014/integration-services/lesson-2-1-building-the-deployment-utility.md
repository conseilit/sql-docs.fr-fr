---
title: 'Étape 1 : Génération de l’utilitaire de déploiement | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
ms.assetid: 1ff4dcff-89b3-4b99-a725-5f7963e98abf
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: b2bbae058a0e3ecacaa4be9204a822451e1a0602
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48216005"
---
# <a name="step-1-building-the-deployment-utility"></a>Étape 1 : génération de l'utilitaire de déploiement
  Au cours de cette tâche, vous allez configurer et générer un utilitaire de déploiement pour le projet Didacticiel de déploiement.  
  
 Avant de générer l'utilitaire de déploiement, vous devez modifier les propriétés du projet Didacticiel de déploiement. La boîte de dialogue **Pages de propriétés du didacticiel de déploiement** vous permet de configurer ces propriétés. Dans cette boîte de dialogue, vous devez activer la possibilité de mettre à jour des configurations au cours du déploiement et spécifier que le processus de création génère un utilitaire de déploiement. Après avoir défini les propriétés, vous allez générer le projet.  
  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] fournit un jeu de fenêtres que vous pouvez utiliser pour déboguer les packages. Vous pouvez afficher les messages d'erreur, d'information et d'avertissement, effectuer le suivi du statut des packages lors de l'exécution ou afficher la progression et les résultats des processus de génération. Pour cette leçon, vous allez utiliser la fenêtre de sortie pour afficher la progression et les résultats de la génération de l'utilitaire de déploiement.  
  
### <a name="to-set-the-deployment-utility-properties"></a>Pour définir les propriétés de l'utilitaire de déploiement  
  
1.  Si [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] n’est pas déjà ouvert, dans le menu **Démarrer**, pointez sur **Tous les programmes**, puis sur **Microsoft SQL Server**et cliquez sur **Business Intelligence Development Studio**.  
  
2.  Dans le menu **Fichier** , cliquez successivement sur **Ouvrir**, sur **Projet/Solution**, sur le dossier **Didacticiel de déploiement** et sur **Ouvrir**, puis double-cliquez sur **Deployment Tutorial.sln**.  
  
3.  Dans l’Explorateur de solutions, cliquez avec le bouton droit sur Didacticiel de déploiement, puis cliquez sur **Propriétés**.  
  
4.  Dans la boîte de dialogue **Pages de propriétés du didacticiel de déploiement** , développez Propriétés de configuration et cliquez sur Utilitaire de déploiement.  
  
5.  Dans le volet droit de la **Pages de propriétés de didacticiel de déploiement** boîte de dialogue, vérifiez que `AllowConfigurationChanges` a la valeur `true`, affectez la valeur `CreateDeploymentUtility` à `true`et éventuellement mettre à jour la valeur par défaut `DeploymentOutputPath`.  
  
6.  Cliquez sur **OK**.  
  
### <a name="to-build-the-deployment-utility"></a>Pour générer l'utilitaire de déploiement  
  
1.  Dans l’Explorateur de solutions, cliquez sur **Didacticiel de déploiement**.  
  
2.  Dans le menu **Affichage** , cliquez sur **Sortie**. Par défaut, la fenêtre de sortie se trouve dans le coin inférieur gauche de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].  
  
3.  Dans le menu **Générer** , cliquez sur **Générer le didacticiel de déploiement**.  
  
4.  Dans la fenêtre de sortie, vérifiez les informations suivantes :  
  
     Génération démarrée : projet SQL Integration Services : incrémentiel ...  
  
     Création de l'utilitaire de déploiement...  
  
     Utilitaire de déploiement créé.  
  
     Fin de la génération -- 0 erreur, 0 avertissement  
  
     ========== Génération : 0 a réussi, 0 a échoué, 1 est à jour, 0 a été ignoré ==========  
  
5.  Dans le menu **Fichier** , cliquez sur **Quitter**. Si vous êtes invité à enregistrer les modifications apportées aux éléments du didacticiel de déploiement, cliquez sur **Oui**.  
  
## <a name="next-task-in-lesson"></a>Tâche suivante de la leçon  
 [Étape 2 : Vérification du bundle de déploiement](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
![Icône Integration Services (petite)](media/dts-16.gif "icône Integration Services (petite)")**rester jusqu'à la Date avec Integration Services** <br /> Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :<br /><br /> [Visitez la page Integration Services sur MSDN](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.  
  
## <a name="see-also"></a>Voir aussi  
 [Créer un utilitaire de déploiement](../../2014/integration-services/create-a-deployment-utility.md)  
  
  
