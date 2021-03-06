---
title: PreConnect:Completed, classe d’événements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- PreConnect:Completed Event Class
ms.assetid: 7ed2f620-6511-4985-9961-d2927c2b1759
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 16720db613815d5c8cce501c1cee2d5d3cc9b3cb
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48150629"
---
# <a name="preconnectcompleted-event-class"></a>PreConnect:Completed, classe d’événements
  La classe d’événements PreConnect:Completed indique quand un déclencheur LOGON ou la fonction classifieur de Resource Governor finit de s’exécuter.  
  
## <a name="preconnectcompleted-event-class-data-columns"></a>Colonnes de données de la classe d'événements PreConnect:Completed  
  
|Nom de la colonne de données|Type de données|Description|ID de la colonne|Filtrable|  
|----------------------|---------------|-----------------|---------------|----------------|  
|EventClass|`int`|216|27|non|  
|SPID|`int`|ID du processus serveur qui déclenche cet événement.|12|Oui|  
|EventSubClass|`int`|1 pour la fonction classifieur définie par l'utilisateur.|21|Oui|  
|StartTime|`datetime`|Heure de démarrage de la fonction classifieur définie par l'utilisateur.|14|Oui|  
|EndTime|`datetime`|Heure de démarrage de la fonction classifieur définie par l'utilisateur.|15|Oui|  
|Duration|`bigint`|Temps en microsecondes utilisé par la fonction classifieur.|13|Oui|  
|ObjectID|`int`|ID de l'objet classifieur défini par l'utilisateur.|22|Oui|  
|Unité centrale|`int`|Utilisation de l'UC en millisecondes.|18|Oui|  
|Reads|`int`|Nombre de lectures logiques.|16|Oui|  
|Writes|`int`|Nombre d'écritures logiques.|17|Oui|  
|GroupID|`int`|ID du groupe de charges de travail classifié.|66|Oui|  
|Error|`int`|Dernier numéro d'erreur si la fonction classifieur définie par l'utilisateur ne peut pas s'exécuter.|31|Oui|  
|État|`int`|État de la dernière erreur.|30|Oui|  
|TargetUserName|`sysname`|Valeur de retour (nom de groupe de charges de travail) pour la fonction classifieur définie par l'utilisateur si le système ne peut pas trouver un groupe actif correspondant. Dans le cas contraire, cette colonne a la valeur NULL.|39|Oui|  
|ObjectName|`nvarchar(256)`|Nom en deux parties de la fonction classifieur définie par l'utilisateur. Par exemple, dbo.classifier.|34|Oui|  
  
## <a name="see-also"></a>Voir aussi  
 [Événements étendus](../extended-events/extended-events.md)   
 [PreConnect:Starting, classe d'événements](preconnect-starting-event-class.md)   
 [Resource Governor](../resource-governor/resource-governor.md)  
  
  
