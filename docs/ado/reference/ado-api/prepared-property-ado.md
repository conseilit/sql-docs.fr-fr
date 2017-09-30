---
title: "Préparé, propriété (ADO) | Documents Microsoft"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Command15::Prepared
helpviewer_keywords:
- Prepared property [ADO]
ms.assetid: 11ca8825-765e-4bb4-a6ce-3f6564ad8755
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: f47836c824401e5ca49edd5eac33c2f6f6393993
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="prepared-property-ado"></a>Prepared, propriété (ADO)
Indique s’il faut enregistrer la version compilée d’un [commande](../../../ado/reference/ado-api/command-object-ado.md) avant l’exécution.  
  
## <a name="settings-and-return-values"></a>Paramètres et valeurs de retour  
 Définit ou retourne un **booléenne** valeur, si la valeur **True**, indique que la commande doit être préparée.  
  
## <a name="remarks"></a>Notes  
 Utilisez le **Prepared** propriété pour que le fournisseur enregistre une version préparée (ou compilée) de la requête spécifiée dans le [CommandText](../../../ado/reference/ado-api/commandtext-property-ado.md) propriété avant une [commande](../../../ado/reference/ado-api/command-object-ado.md) l’objet première exécution. Cela peut ralentir l’exécution du premier d’une commande, mais une fois que le fournisseur compile une commande, le fournisseur utilise la version compilée de la commande pour des exécutions suivantes, ce qui entraîne une amélioration des performances.  
  
 Si la propriété est **False**, le fournisseur s’exécutera la **commande** objet directement sans création d’une version compilée.  
  
 Si le fournisseur ne prend pas en charge la préparation des commandes, elle peut retourner une erreur lorsque cette propriété est définie sur **True**. Si le fournisseur ne retourne pas d’erreur, il ignore simplement la requête de préparation de la commande et le définit le **Prepared** propriété **False**.  
  
## <a name="applies-to"></a>S'applique à  
 [Objet de commande (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de propriété préparé (VB)](../../../ado/reference/ado-api/prepared-property-example-vb.md)   
 [Exemple de propriété préparé (VC ++)](../../../ado/reference/ado-api/prepared-property-example-vc.md)   
