---
title: "Extension de Packages avec des objets personnalisés | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: 26616eb8-9e80-434d-b22a-ece1b00f449d
caps.latest.revision: 36
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: e10fbab75eca8556e36734c1c0ad3828b8b09404
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="extending-packages-with-custom-objects"></a>Extension de packages avec des objets personnalisés
  Si vous constatez que les composants fournis dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ne satisfont pas vos besoins, vous pouvez étendre la puissance d'[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en codant vos propres extensions. Vous disposez de deux options distinctes pour étendre vos packages : vous pouvez écrire du code dans les puissants wrappers fournis par la tâche de script et le composant Script, ou vous pouvez entièrement créer des extensions [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personnalisées, dérivées des classes de base fournies par le modèle objet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
 Cette section explore l'option la plus avancée des deux : l'extension de packages à l'aide d'objets personnalisés.  
  
 Lorsque votre solution [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personnalisée exige davantage de flexibilité que celle fournie par la tâche de script ou le composant Script, ou lorsque vous avez besoin d'un composant réutilisable dans plusieurs packages, le modèle objet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] vous permet de créer des tâches personnalisées, des composants de flux de données et d'autres objets de package en code managé.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Développement d’objets personnalisés pour Integration Services](../../integration-services/extending-packages-custom-objects/developing-custom-objects-for-integration-services.md)  
 Présente les objets personnalisés qui peuvent être créés pour [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] et résume les étapes et les paramètres essentiels.  
  
 [Persistance des objets personnalisés](../../integration-services/extending-packages-custom-objects/persisting-custom-objects.md)  
 Examine la persistance par défaut des objets personnalisés et le processus d'implémentation de la persistance personnalisée.  
  
 [Génération, déploiement et débogage d’objets personnalisés](../../integration-services/extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md)  
 Présente les méthodes les plus usuelles pour créer, déployer et tester les différents types d'objets personnalisés.  
  
 [Développement d’une tâche personnalisée](../../integration-services/extending-packages-custom-objects/task/developing-a-custom-task.md)  
 Décrit le processus de codage d'une tâche personnalisée.  
  
 [Développement d’un gestionnaire de connexions personnalisé](../../integration-services/extending-packages-custom-objects/connection-manager/developing-a-custom-connection-manager.md)  
 Décrit le processus de codage d'un gestionnaire de connexions personnalisé.  
  
 [Développement d’un fournisseur de journal personnalisé](../../integration-services/extending-packages-custom-objects/log-provider/developing-a-custom-log-provider.md)  
 Décrit le processus du codage d'un module fournisseur d'informations personnalisé.  
  
 [Développement d’un énumérateur ForEach personnalisé](../../integration-services/extending-packages-custom-objects/foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 Décrit le processus de codage d'un énumérateur personnalisé.  
  
 [Développement d’un composant de flux de données personnalisées](../../integration-services/extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md)  
 Explique comment programmer des sources, des transformations et des destinations de flux de données personnalisées.  
  
## <a name="reference"></a>Référence  
 [Integration Services Error and Message Reference](../../integration-services/integration-services-error-and-message-reference.md)  
 Répertorie les codes d'erreur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] prédéfinis avec leur nom symbolique et leur description.  
  
## <a name="related-sections"></a>Sections connexes  
 [Extension de Packages avec des scripts](../../integration-services/extending-packages-scripting/extending-packages-with-scripting.md)  
 Explique comment étendre le flux de contrôle à l'aide de la tâche de script, ou comment étendre le flux de données à l'aide du composant Script.  
  
 [Génération de Packages par programme](../../integration-services/building-packages-programmatically/building-packages-programmatically.md)  
 Décrit comment créer, configurer, exécuter, charger, enregistrer et gérer des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] par programme.  
  
## <a name="see-also"></a>Voir aussi  
 [Comparaison des Solutions de script et des objets personnalisés](../../integration-services/extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)   
 [SQL Server Integration Services](../../integration-services/sql-server-integration-services.md)  
  
  