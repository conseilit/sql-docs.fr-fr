---
title: Élément (XMLA) des résultats | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- results Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- microsoft.xml.analysis.results
- urn:schemas-microsoft-com:xml-analysis#results
- http://schemas.microsoft.com/analysisservices/2003/engine#results
helpviewer_keywords:
- results element
ms.assetid: 3249a17a-7bfa-4753-b605-8f611ba7ae2b
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e99728941db468f361535fa675281f880ad3133a
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48091359"
---
# <a name="results-element-xmla"></a>Élément results (XMLA)
  Contient une collection d'éléments [root](root-element-xmla.md) retournée par la méthode [Execute](../xml-elements-methods-execute.md) employée avec la commande [Batch](../xml-elements-commands/batch-element-xmla.md) .  
  
 **Namespace** http://schemas.microsoft.com/analysisservices/2003/xmla-multipleresults  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<return>  
   <results>  
      <root>...</root>  
   </results>  
</return>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|None|  
|Valeur par défaut|None|  
|Cardinalité|0-1 : élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[retour](return-element-xmla.md)|  
|Éléments enfants|[Racine](root-element-xmla.md)|  
  
## <a name="remarks"></a>Notes  
 Si une commande `Batch` est exécutée par la méthode `Execute`, l'élément `return` contient un élément `results` unique au lieu d'un élément `root` unique. Le contenu de l'élément `results` dépend des paramètres utilisés pour exécuter la commande `Batch`.  
  
 Pour les commandes `Batch` non transactionnelles, l'élément `results` contient un élément `root` pour chacune des commandes exécutées par la commande `Batch`, que ces commandes réussissent ou échouent. Pour les commandes `Batch` transactionnelles, l'élément `results` contient un seul élément `root` contenant les informations d'erreur de la commande qui a échoué dans la commande `Batch`.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40;XMLA&#41;](xml-elements-properties.md)  
  
  
