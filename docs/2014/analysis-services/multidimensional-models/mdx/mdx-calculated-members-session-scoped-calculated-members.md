---
title: Création d’une Session spécifique de membres (MDX) calculés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- CREATE MEMBER statement
- session-scoped calculated members [MDX]
ms.assetid: 2875ed89-2c26-4645-8ed9-8848479d110f
caps.latest.revision: 29
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 79e6466c7f514b3453f8840a72dc0028a215259b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37249859"
---
# <a name="creating-session-scoped-calculated-members-mdx"></a>Création de membres calculés au niveau de la session (MDX)
  Pour créer un membre calculé disponible dans l’ensemble d’une session MDX (Multidimensional Expressions), vous utilisez l’instruction [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member). Un membre calculé créé à l'aide de l'instruction CREATE MEMBER n'est supprimé qu'après la fermeture de la session MDX.  
  
 Comme décrit dans cette rubrique, la syntaxe de l'instruction CREATE MEMBER est explicite et conviviale.  
  
> [!NOTE]  
>  Pour plus d’informations sur les membres calculés, consultez [Création de membres calculés dans MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).  
  
## <a name="create-member-syntax"></a>Syntaxe CREATE MEMBER  
 Utilisez la syntaxe suivante pour ajouter l'instruction CREATE MEMBER à l'instruction MDX :  
  
```  
CREATE [SESSION] MEMBER [<cube-name>.]<fully-qualified-member-name> AS <expression> [,<property-definition-list>]  
<cube name> ::= CURRENTCUBE | <Cube Name>  
<property-definition-list> ::= <property-definition>  
  | <property-definition>, <property-definition-list>  
<property-definition> ::= <property-identifier> = <property-value>  
<property-identifier> ::= VISIBLE | SOLVEORDER | SOLVE_ORDER | FORMAT_STRING | NON_EMPTY_BEHAVIOR <ole db member properties>  
```  
  
 Dans la syntaxe de l'instruction CREATE MEMBER, la valeur `fully-qualified-member-name` est le nom complet du membre calculé. Ce nom comprend la dimension ou le niveau auquel le membre calculé est associé. La valeur `expression` retourne la valeur du membre calculé après l'évaluation de la valeur de l'expression.  
  
## <a name="create-member-example"></a>Exemple de syntaxe CREATE MEMBER  
 L'exemple suivant utilise l'instruction CREATE MEMBER pour créer le membre calculé `LastFourStores` . Ce dernier retourne la somme des unités vendues dans les quatre derniers magasins et sera disponible tout au long de la session du cube.  
  
```  
Create Session Member [Store].[Measures].LastFourStores as   
sum(([Stores].[ByLocation].Lag(3) :  
[Stores].[ByLocation].NextMember), [Measures].[Units Sold])  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’étendue de requête des membres calculés &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md)  
  
  