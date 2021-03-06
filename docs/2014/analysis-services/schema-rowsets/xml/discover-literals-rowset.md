---
title: Ensemble de lignes DISCOVER_LITERALS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- DISCOVER_LITERALS
topic_type:
- apiref
helpviewer_keywords:
- DISCOVER_LITERALS rowset
ms.assetid: 1bf0a2e2-a419-4c25-b271-37dfa44de2ea
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e218c03cd6d2f8dbf06501dd18a2c4c3e4977eca
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48063211"
---
# <a name="discoverliterals-rowset"></a>Ensemble de lignes DISCOVER_LITERALS
  Retourne des informations sur les littéraux pris en charge par le fournisseur XMLA (XML for Analysis) [!INCLUDE[msCoName](../../../includes/msconame-md.md)], y compris les types de données et les valeurs.  
  
 Si vous appelez le [Discover](../../xmla/xml-elements-methods-discover.md) méthode avec le `DISCOVER_LITERALS` valeur d’énumération dans le [RequestType](../../xmla/xml-elements-properties/type-element-xmla.md) élément, le `Discover` méthode retourne la `DISCOVER_LITERALS` ensemble de lignes.  
  
## <a name="rowset-columns"></a>Colonnes de l'ensemble de lignes  
 Le `DISCOVER_LITERALS` ensemble de lignes contient les colonnes suivantes.  
  
|Nom de colonne|Indicateur de type|Longueur|Description|  
|-----------------|--------------------|------------|-----------------|  
|`LiteralName`|`DBTYPE_WSTR`||Nom du littéral décrit dans la ligne.<br /><br /> Par exemple : `DBLITERAL_LIKE_PERCENT`|  
|`LiteralValue`|`DBTYPE_WSTR`||Valeur littérale réelle.<br /><br /> Par exemple, si `LiteralName` est `DBLITERAL_LIKE_PERCENT` et si le caractère de pourcentage (`%`) équivaut à zéro, un ou plusieurs caractères dans une clause LIKE, la valeur de la colonne `LiteralValue` est "`%`".|  
|`LiteralInvalidChars`|`DBTYPE_WSTR`||Caractères qui ne sont pas valides dans le littéral.<br /><br /> Par exemple, si les noms de table acceptent n'importe quels caractères à l'exception des caractères numériques, cette chaîne est "`0123456789`".|  
|`LiteralInvalidStartingChars`|`DBTYPE_WSTR`||Caractères qui ne sont pas valides comme premier caractère dans le littéral. Si le littéral peut commencer par n'importe quel caractère valide, la chaîne est `null`.|  
|`LiteralMaxLength`|`DBTYPE_I4`||Nombre maximal de caractères du littéral. Si la colonne ne possède pas de longueur maximale ou si elle est inconnue, la valeur est -1.|  
|`LiteralNameEnumValue`|`DBTYPE_I4`|||  
  
 Cet ensemble de lignes de schéma n'est pas trié.  
  
## <a name="restriction-columns"></a>Colonnes de restriction  
 L'ensemble de lignes `DISCOVER_LITERALS` peut être restreint sur les colonnes répertoriées dans le tableau suivant.  
  
|Nom de colonne|Indicateur de type|État de la restriction|  
|-----------------|--------------------|-----------------------|  
|`LiteralName`|`DBTYPE_WSTR`|Facultatif.|  
  
## <a name="see-also"></a>Voir aussi  
 [XML for Analysis Schema Rowsets](xml-for-analysis-schema-rowsets.md)   
 [Ensemble de lignes DISCOVER_KEYWORDS &#40;XMLA&#41;](discover-keywords-rowset-xmla.md)  
  
  
