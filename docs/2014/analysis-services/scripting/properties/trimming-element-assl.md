---
title: Élément Trimming (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- Trimming Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- Trimming
helpviewer_keywords:
- Trimming element
ms.assetid: 8b3bbf89-8309-4d00-9aea-a5918f0c7027
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 250394f67c79eec799f75dd0b6f590f6bff8f988
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48198779"
---
# <a name="trimming-element-assl"></a>Élément Trimming (ASSL)
  Spécifie comment les données de la source de données sont tronquées.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<DataItem>  
   ...  
   <Trimming>...</Trimming>  
   ...  
</DataItem>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|*Oui*|  
|Cardinalité|0-1 : élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Élément parent|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Éléments enfants|None|  
  
## <a name="remarks"></a>Notes  
 La valeur de cet élément est limitée à l'une des chaînes répertoriées dans le tableau suivant.  
  
|Valeur|Description|  
|-----------|-----------------|  
|*Gauche*|Les données sont tronquées à gauche.|  
|*Oui*|Les données sont tronquées à droite.|  
|*LeftRight*|Les données sont tronquées à gauche et à droite.|  
|*Aucun*|Les données ne sont pas tronquées.|  
  
 L’énumération qui correspond aux valeurs autorisées pour `Trimming` dans l’objet d’objets AMO (Analysis Management) modèle est <xref:Microsoft.AnalysisServices.Trimming>.  
  
 L’élément qui correspond au parent de `Trimming` dans l’objet d’objets AMO (Analysis Management) modèle est <xref:Microsoft.AnalysisServices.DataItem>.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40;ASSL&#41;](properties-assl.md)  
  
  
