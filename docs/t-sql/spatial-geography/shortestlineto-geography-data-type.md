---
title: "ShortestLineTo (Type de données geography) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ShortestLineTo_TSQL
- ShortestLineTo
dev_langs:
- TSQL
helpviewer_keywords:
- ShortestLineTo method (geography)
ms.assetid: 9d7c9885-5d1b-49ae-af31-5ef9fb8acaba
caps.latest.revision: 10
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: acb6d16fbf1413a81a05582bc203a7e768b70c75
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="shortestlineto-geography-data-type"></a>ShortestLineTo (type de données geography)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Retourne un **LineString** instance avec deux points qui représentent la distance la plus courte entre les deux **geography** instances. La longueur de la **LineString** instance retournée est la distance entre les deux **geography** instances.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.ShortestLineTo ( geography_other )  
```  
  
## <a name="arguments"></a>Arguments  
 *geography_other*  
 Spécifie le deuxième **geography** de l’instance qui l’appelle **geography** instance essaie de déterminer la distance la plus courte.  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **geography**  
  
 Type de retour CLR : **SqlGeography**  
  
## <a name="remarks"></a>Notes  
 La méthode retourne un **LineString** instance avec les points de terminaison sur les bordures des deux planifications **geography** instances comparées. La longueur de la **LineString** retournée est égale à la distance la plus courte entre les deux **geography** instances. Vide **LineString** instance est retournée lorsque les deux **geography** instances croisent.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-calling-shortestlineto-on-non-intersecting-instances"></a>A. Appel de ShortestLineTo() sur des instances qui ne se croisent pas  
 Cet exemple recherche la distance la plus courte entre une instance `CircularString` et une instance `LineString` et retourne l'instance `LineString` qui connecte les deux points :  
  
 `DECLARE @g1 geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';`  
  
 `DECLARE @g2 geography = 'LINESTRING(-119.119263 46.183634, -119.273071 47.107523, -120.640869 47.569114, -122.200928 47.454094)';`  
  
 `SELECT @g1.ShortestLineTo(@g2).ToString();`  
  
### <a name="b-calling-shortestlineto-on-intersecting-instances"></a>B. Appel de ShortestLineTo() sur des instances qui se croisent  
 Cet exemple retourne une instance `LineString` vide du fait que l'instance `LineString` croise l'instance `CircularString` :  
  
 `DECLARE @g1 geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';`  
  
 `DECLARE @g2 geography = 'LINESTRING(-119.119263 46.183634, -119.273071 47.107523, -120.640869 47.569114, -122.348 47.649, -122.681 47.655)';`  
  
 `SELECT @g1.ShortestLineTo(@g2).ToString();`  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes étendues sur les Instances Geography](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)  
  
  