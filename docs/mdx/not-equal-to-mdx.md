---
title: '&lt;&gt; (Différent de) (MDX) | Documents Microsoft'
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: ac3241e7d6acd8ba883cdd59f9410f4a0fd9187d
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34742328"
---
# <a name="ltgt-not-equal-to-mdx"></a>&lt;&gt; (Différent de) (MDX)


  Exécute une opération de comparaison qui détermine si la valeur d'une expression MDX est différente de la valeur d'une autre expression MDX.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
MDX_Expression <> MDX_Expression  
```  
  
#### <a name="parameters"></a>Paramètres  
 *MDX_Expression*  
 Expression MDX valide.  
  
## <a name="return-value"></a>Valeur de retour  
 Valeur booléenne basée sur les conditions suivantes :  
  
-   **true** si les deux paramètres sont non null et que le premier paramètre n’est pas égal au deuxième paramètre.  
  
-   **false** si les deux paramètres sont non null et que le premier paramètre est égal au second paramètre.  
  
-   NULL si l'un ou l'autre ou les deux paramètres ont une valeur NULL.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des opérateurs MDX &#40;MDX&#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
