---
title: Élément ImpersonationMode (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- ImpersonationMode Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- ImpersonateMode
helpviewer_keywords:
- ImpersonateMode element
ms.assetid: 160fdcb2-ac9f-4c5a-a0eb-a5f7669166b9
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 87a68d6ef1035d7caf1d787d9ab44578d17c5489
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48105144"
---
# <a name="impersonationmode-element-assl"></a>Élément ImpersonationMode (ASSL)
  Contient une valeur qui indique la méthode d’emprunt d’identité pour les éléments qui sont dérivés de la [ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md) type de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<ImpersonationInfo>  
   ...  
   <ImpersonationMode>...</ImpersonationMode>  
  
</ImpersonationInfo>...  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|*Par défaut*|  
|Cardinalité|0-1 : élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Élément parent|[ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md)|  
|Éléments enfants|None|  
  
## <a name="remarks"></a>Notes  
 La valeur de cet élément est limitée à l'une des chaînes du tableau suivant.  
  
|Valeur|Description|  
|-----------|-----------------|  
|*Par défaut*|Le parent utilise la méthode d'emprunt d'identité la mieux adaptée au contexte dans lequel l'emprunt d'identité s'effectue.|  
|*ImpersonateAccount*|Le parent utilise les informations d'identification du compte d'utilisateur spécifié dans l'élément parent.|  
|*ImpersonateAnonymous*|Le parent utilise les informations d'identification d'un utilisateur anonyme.|  
|*ImpersonateCurrentUser*|Le parent utilise les informations d'identification de l'utilisateur actuel.|  
|*ImpersonateServiceAccount*|Le parent utilise les informations d’identification du compte de service qui est associé à l’instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
  
 L’énumération qui correspond aux valeurs autorisées pour `ImpersonationMode` dans l’objet d’objets AMO (Analysis Management) modèle est <xref:Microsoft.AnalysisServices.ImpersonationLevel>.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40;ASSL&#41;](properties-assl.md)  
  
  
