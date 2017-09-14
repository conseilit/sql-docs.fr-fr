---
title: Extensions Reporting Services | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- SQL Server Reporting Services, extending
- extensions [Reporting Services], about extensions
- SSIS, extending
- Reporting Services, extending
- extensions [Reporting Services]
ms.assetid: 2bf17ae4-2292-4a58-a1f0-56e99abd9b69
caps.latest.revision: 45
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: 37adf4c09f7f23294572a17631240ad88f51fc9e
ms.contentlocale: fr-fr
ms.lasthandoff: 08/12/2017

---
# <a name="reporting-services-extensions"></a>Extensions Reporting Services
  L'architecture modulaire de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] est conçue à des fins d'extensibilité. Une API de code managé est disponible afin de vous permettre de développer, installer et gérer facilement des extensions consommées par de nombreux composants [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Vous pouvez créer privé ou des assemblys partagés à l’aide de la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] et ajouter de nouvelles [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] fonctionnalités pour répondre aux besoins de votre entreprise en constante évolution.  
  
 L'architecture d'extensibilité unique de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] permet aux développeurs d'étendre des fonctionnalités spécifiques du produit et de ses composants. Il existe actuellement une prise en charge générale pour étendre les fonctions de traitement de données de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. L'API de traitement de données comprend des constructions et des conventions du fournisseur de données [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] couramment utilisées, qui permettent aux développeurs d'ajouter des fonctions de traitement de données supplémentaires à [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Ces extensions pour le traitement des données ajoutent des fonctionnalités au serveur de rapports et au Concepteur de rapports, ce qui se traduit par une intégration transparente des données personnalisées aux rapports.  
  
 Une autre extension prise en charge est l'extension de remise. L'API de remise est entièrement intégrée à l'architecture [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], ce qui permet d'utiliser une grande variété de mécanismes de remise lors de l'envoi de notifications de rapport aux utilisateurs. Vous pouvez étendre le serveur de rapports pour fournir une remise personnalisée aux utilisateurs et vous pouvez étendre les pages de gestion d'abonnement du Gestionnaire de rapports pour prendre en charge les abonnements qui utilisent des extensions de remise personnalisées.  
  
 Une autre extension du serveur de rapports, RDCE (Report Definition Customization Extension), peut personnaliser dynamiquement une définition de rapport avant que celle-ci ne soit passée au moteur de traitement. Vous pouvez personnaliser des rapports en fonction de facteurs tels que des utilisateurs ou des langues. Par exemple, vous pouvez implémenter des vues adaptées à différents utilisateurs, tels que des responsables ou des membres d'un service, ou vous pouvez personnaliser un rapport pour générer une disposition différente selon qu'il est rendu en français ou en arabe.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Considérations sur la sécurité pour les extensions](../../reporting-services/extensions/security-considerations-for-extensions.md)  
 Décrit les problèmes de sécurité relatifs au développement et au déploiement d'extensions [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
 [Mise en œuvre d’une extension pour le traitement des données](../../reporting-services/extensions/data-processing/implementing-a-data-processing-extension.md)  
 Décrit les spécifications et les étapes relatives à l'implémentation d'une extension pour le traitement des données pour [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
 [Mise en œuvre d'une extension de remise](../../reporting-services/extensions/delivery-extension/implementing-a-delivery-extension.md)  
 Décrit les spécifications et les étapes relatives à l'implémentation d'une extension de remise pour [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
 [Mise en œuvre d'une extension de rendu](../../reporting-services/extensions/rendering-extension/implementing-a-rendering-extension.md)  
 Contient une introduction au développement d'extensions de rendu.  
  
 [Implémentation d'une extension de sécurité](../../reporting-services/extensions/security-extension/implementing-a-security-extension.md)  
 Décrit les spécifications et les étapes relatives à l'implémentation d'une extension de sécurité [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
 [Bibliothèque d’Extension de Reporting Services](../../reporting-services/extensions/reporting-services-extension-library.md)  
 Contient la référence de programmation pour la bibliothèque API d'extension pour les fonctionnalités d'extensibilité de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
  