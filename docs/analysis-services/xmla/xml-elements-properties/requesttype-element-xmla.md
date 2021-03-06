---
title: Élément RequestType (XMLA) | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 63c1a838d74745b5ef51f73b51e34c95e08a81ff
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37994791"
---
# <a name="requesttype-element-xmla"></a>Élément RequestType (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Détermine le type des métadonnées retournées par le [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) (méthode).  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Discover>  
   ...  
   <RequestType>...</RequestType>  
   ...  
</Discover>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques d’éléments  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|None|  
|Cardinalité|1-1 : élément requis qui apparaît une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Découvrir](../../../analysis-services/xmla/xml-elements-methods-discover.md)|  
|Éléments enfants|None|  
  
## <a name="remarks"></a>Notes  
 Le **RequestType** élément détermine l’ensemble de lignes de schéma à partir de laquelle le **Discover** méthode retourne les données. Cette énumération est limitée aux noms des ensembles de lignes de schéma pris en charge par Analysis Services. Pour plus d’informations sur les ensembles de lignes de schéma, consultez [Analysis Services Schema Rowsets](../../../analysis-services/schema-rowsets/analysis-services-schema-rowsets.md).  
  
> [!NOTE]  
>  Le **RequestType** élément énumère uniquement les noms d’ensemble de lignes de schéma. Une erreur se produit si le GUID de l'ensemble de lignes de schéma est utilisé.  
  
## <a name="see-also"></a>Voir aussi
 [Propriétés &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
