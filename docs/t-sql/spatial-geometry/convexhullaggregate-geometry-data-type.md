---
title: "ConvexHullAggregate (Type de données geometry) | Documents Microsoft"
ms.custom: 
ms.date: 08/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- ConvexHullAggregate method (geometry)
ms.assetid: ca3d3b55-e02d-4599-8817-a54f5e047db8
caps.latest.revision: 13
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: df18875ed28cce014ac5aeb9c871cdfde5efa442
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="convexhullaggregate-geometry-data-type"></a>ConvexHullAggregate (type de données geometry)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

Retourne une forme convexe pour un ensemble donné de **geometry** objets.
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
ConvexHullAggregate ( geometry_operand )  
```  
  
## <a name="arguments"></a>Arguments  
 *geometry_operand*  
 Est un **geometry** colonne de table de type qui représente un ensemble d’objets géométriques.  
  
## <a name="return-types"></a>Types de retour  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]type de retour : **geometry**  
  
## <a name="exception"></a>Exception  
 Lève un `FormatException` en présence de valeurs d'entrée qui ne sont pas valides. Consultez [STIsValid &#40; Type de données geometry &#41;](../../t-sql/spatial-geometry/stisvalid-geometry-data-type.md)  
  
## <a name="remarks"></a>Notes  
 Méthode renvoie **null** lorsque l’entrée est vide ou l’entrée a des SRID différents. Consultez [identificateurs de référence spatiale &#40; SRID &#41;](../../relational-databases/spatial/spatial-reference-identifiers-srids.md)  
  
 Méthode ignore **null** entrées.  
  
> [!NOTE]  
>  Méthode renvoie **null** si toutes les valeurs entrées sont **null**.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant retourne une forme convexe du jeu d'objets géométriques dans une colonne de variable de table.  
  
 `-- Setup table variable for ConvexHullAggregate example`  
  
 `DECLARE @Geom TABLE`  
  
 `(`  
  
 `shape geometry,`  
  
 `shapeType nvarchar(50)`  
  
 `)`  
  
 `INSERT INTO @Geom(shape,shapeType) VALUES('CURVEPOLYGON(CIRCULARSTRING(2 3, 4 1, 6 3, 4 5, 2 3))', 'Circle'),`  
  
 `('POLYGON((1 1, 4 1, 4 5, 1 5, 1 1))', 'Rectangle');`  
  
 `-- Perform ConvexHullAggregate on @Geom.shape column`  
  
 `SELECT geometry::ConvexHullAggregate(shape).ToString()`  
  
 `FROM @Geom;`  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes de géométrie statiques étendues](../../t-sql/spatial-geometry/extended-static-geometry-methods.md)  
  
  

