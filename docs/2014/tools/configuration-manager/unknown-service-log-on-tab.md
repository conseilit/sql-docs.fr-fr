---
title: Service inconnu (onglet Ouvrir une session) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- configmgr-client
ms.topic: conceptual
ms.assetid: e9b35cb5-d8ae-42ea-b59e-deedc99c4823
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 8d72dbd993c3944131e80ad4ba6215cee3d3cf2e
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48147477"
---
# <a name="unknown-service-log-on-tab"></a>Service inconnu (onglet Ouvrir une session)
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas en mesure d'identifier ce service.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reçoit des informations de service émanant du fournisseur WMI installé sur l'ordinateur exécutant le service. Une erreur s'est produite lors de la lecture des propriétés du service ou celles-ci sont incomplètes. Pour résoudre le problème, essayez de fermer puis de rouvrir le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ou vérifiez le fournisseur WMI installé sur l'ordinateur exécutant le service.  
  
 Le fournisseur WMI est un composant Windows. Pour plus d'informations sur la manière de vérifier les autorisations sur le fournisseur WMI, consultez « Procédure : configurer WMI pour afficher l'état du serveur dans les outils SQL Server », dans la documentation en ligne.  
  
 Si vous pensez que vous examinez le service approprié, utilisez l'onglet **Ouvrir une session** de la boîte de dialogue **Propriétés de Service inconnu** pour spécifier le compte utilisé par ce service, ainsi que pour démarrer et arrêter le service.  
  
## <a name="options"></a>Options  
 **Compte système local**  
 Spécifie un compte système local, qui ne requiert pas de mot de passe. Toutefois, le compte système local peut empêcher le service d'interagir avec les autres serveurs, en fonction des privilèges accordés au compte.  
  
 **Ce compte**  
 Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification Windows. Nous vous recommandons d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services. Pour plus d'informations sur la sélection d'un compte, consultez « Configuration des comptes de service Windows » dans la documentation en ligne de SQL Server.  
  
 **Nom du compte**  
 Spécifie le nom de compte d'utilisateur local ou de domaine.  
  
 **Mot de passe**  
 Tapez le mot de passe du compte.  
  
 **Confirmer le mot de passe**  
 Tapez de nouveau le mot de passe du compte.  
  
 **Démarrer**  
 Démarrez le service.  
  
 **Arrêter**  
 Arrête le service.  
  
 **Suspendre**  
 Suspend le service.  
  
 **Reprendre**  
 Reprend un service suspendu.  
  
  
