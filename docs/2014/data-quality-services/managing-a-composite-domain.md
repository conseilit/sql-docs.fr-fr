---
title: Gestion d’un domaine composite | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- data-quality-services
ms.topic: conceptual
ms.assetid: 47821eff-800b-4053-8d36-e42bbc267f54
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 9dd4bbcb2c2b610cfa91eea160f4194fa9df9e82
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48174489"
---
# <a name="managing-a-composite-domain"></a>Gestion d'un domaine composite
  Cette rubrique décrit l'utilisation des domaines composites dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS). Parfois un seul domaine ne représente pas les données d'un domaine de manière satisfaisante, et vous pouvez représenter les données uniquement en regroupant les domaines. Pour cela, vous créez un domaine composite. Un domaine composite comprend deux ou plusieurs domaines individuels et est mappé à un champ de données composé de plusieurs termes connexes qui ne sont pas analysés, mais sont inclus dans une même valeur composite. Chaque terme de la valeur est représenté par un seul domaine différent. Une fois que vous avez inclus les domaines individuels dans les domaines composites, et que vous avez ensuite mappé le domaine composite au champ de données, vous pouvez générer la connaissance dans la base de connaissances sur les données de ce champ lors de la génération de la connaissance dans les domaines individuels. Un domaine composite, comme un seul domaine, est une représentation sémantique des données d'un seul champ de données.  
  
 Les domaines uniques d'un domaine composite doivent avoir une zone commune de connaissance. Un exemple est une zone adresse qui a une rue, une ville, un état, un pays et un code postal. Les différents termes de ce champ peuvent avoir différents types de données. Pour gérer cela, vous mappez ces termes aux différents domaines individuels. Un autre exemple est un champ de nom complet qui contient le prénom, le deuxième prénom et le nom. Pour utiliser un domaine composite, vous devez pouvoir analyser les données du champ dans différents domaines individuels, en créant un domaine composite pour le champ et un domaine individuel pour une partie du champ.  
  
 Les domaines composites ont des fonctions différentes des domaines individuels. Vous ne pouvez pas modifier les valeurs du domaine composite – vous ne devez le faire que dans un domaine simple. Avec les domaines composites, vous pouvez utiliser les règles inter-domaines pour tester les valeurs des domaines simples du domaine composite. Vous pouvez également afficher les combinaisons de valeurs trouvées dans les domaines composites.  
  
## <a name="in-this-section"></a>Dans cette section  
 L'utilisation d'un domaine composite permet d'effectuer les opérations suivantes :  
  
|||  
|-|-|  
|Créer une représentation sémantique d'un champ de données composé de plusieurs termes connexes qui ne sont pas analysés|[Créer un domaine composite](../../2014/data-quality-services/create-a-composite-domain.md)|  
|Lorsque vous mappez les données complexes à un domaine composite, vous pouvez analyser les données selon la connaissance, en plus de l'analyse sur un séparateur. DQS essaie d'abord d'utiliser sa connaissance sur les domaines simples pour déterminer comment les parties de la chaîne complexe appartiennent aux domaines simples.|[Créer un domaine composite](../../2014/data-quality-services/create-a-composite-domain.md)|  
|Attachez un service de données de référence, tel que celui gérant les adresses, à un domaine composite.|[Attacher un domaine ou un domaine composite à des données de référence](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md)|  
|Créez une règle inter-domaines lorsque la valeur d'un domaine d'un domaine composite affecte la valeur des autres.|[Créer une règle inter-domaines](../../2014/data-quality-services/create-a-cross-domain-rule.md)|  
|Identifiez les combinaisons de valeur afin que DQS puisse rapporter leur fréquence.|[Utiliser les relations de valeur dans un domaine composite](../../2014/data-quality-services/use-value-relations-in-a-composite-domain.md)|  
  
## <a name="related-tasks"></a>Tâches associées  
  
|Description de la tâche|Rubrique|  
|----------------------|-----------|  
|Construction d'une base de connaissances par la découverte de la connaissance et la gestion interactive de la connaissance|[Construction d’une base de connaissances](../../2014/data-quality-services/building-a-knowledge-base.md)|  
|Importation ou exportation de la connaissance depuis ou vers une base de connaissances.|[Importation et exportation de connaissances](../../2014/data-quality-services/importing-and-exporting-knowledge.md)|  
|Création d'un seul domaine et ajout de connaissances au domaine.|[Gestion d’un domaine](../../2014/data-quality-services/managing-a-domain.md)|  
  
  
