---
title: Élément InvalidXmlCharacters (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- InvalidXmlCharacters Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- InvalidXmlCharacters
helpviewer_keywords:
- InvalidXmlCharacters element
ms.assetid: 92b1210c-1075-4f2f-a2c4-dfdc6d7e5c05
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 0832f4138adc3f278af0d735b70251590fb3ba41
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48059636"
---
# <a name="invalidxmlcharacters-element-assl"></a>Élément InvalidXmlCharacters (ASSL)
  Spécifie la méthode de traitement des caractères XML dans les données sources qui ne sont pas valides.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<DataItem>  
   ...  
   <InvalidXmlCharacters>...</InvalidXmlCharacters>  
   ...  
</DataItem  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|*Conserver*|  
|Cardinalité|0-1 : élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Élément parent|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Éléments enfants|None|  
  
## <a name="remarks"></a>Notes  
 La valeur de cet élément est limitée à l'une des chaînes du tableau suivant.  
  
|Valeur|Description|  
|-----------|-----------------|  
|*Conserver*|Les caractères XML non valides sont conservés.|  
|*Supprimer*|Les caractères XML non valides sont supprimés.|  
|*Remplacer*|Les caractères XML non valides sont remplacés par des points d'interrogation (?)|  
  
 L’énumération qui correspond aux valeurs autorisées pour `InvalidXmlCharacters` dans l’objet d’objets AMO (Analysis Management) modèle est <xref:Microsoft.AnalysisServices.InvalidXmlCharacters>.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40;ASSL&#41;](properties-assl.md)  
  
  
