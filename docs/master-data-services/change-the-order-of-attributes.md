---
title: "Modifier l’ordre des attributs | Documents Microsoft"
ms.custom:
- SQL2016_New_Updated
ms.date: 03/15/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 835a032c-e37c-4f35-8ab0-5e4ae25c2e9b
caps.latest.revision: 5
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 403b8824c09993b79f82422ba9136db73b2f7eb7
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="change-the-order-of-attributes"></a>Changer l'ordre des attributs
  Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous pouvez changer l'ordre des attributs.  
  
## <a name="prerequisites"></a>Conditions préalables  
 Pour effectuer cette procédure :  
  
-   Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .  
  
-   Vous devez être administrateur de modèle. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-change-the-order-of-an-attribute"></a>Pour changer la place d'un attribut  
  
1.  Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.  
  
2.  Dans la page **Gérer le modèle** , sélectionnez un modèle dans la grille et cliquez sur **Entités**.  
  
3.  Dans la page **Gérer l’entité** , sélectionnez la ligne de l’entité pour laquelle vous souhaitez créer un attribut.  
  
4.  Cliquez sur **Attributs**.  
  
5.  Sur la page **Gérer les attributs** , effectuez l’une des opérations suivantes.  
  
    -   Si l’attribut concerne les membres feuille, sélectionnez **Feuille** dans la zone de liste **Types de membres** .  
  
    -   Si l’attribut concerne les membres consolidés, sélectionnez **Consolidé** dans la zone de liste **Types de membre** .  
  
    -   Si l’attribut concerne les collections, sélectionnez **Collection** dans la zone de liste **Types de membres** .  
  
6.  Sélectionnez la ligne de l’attribut dont vous souhaitez modifier l’ordre.  
  
    > [!NOTE]  
    >  Vous ne pouvez pas modifier l’ordre des attributs Name ni Code.  
  
7.  Cliquez sur **Monter** ou sur **Descendre**.  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs &#40; Master Data Services &#41;](../master-data-services/attributes-master-data-services.md)  
  
  