---
title: Inverser une Transaction (Master Data Services) | Documents Microsoft
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions [Master Data Services], reversing
ms.assetid: 6f7c3f07-0f64-4283-8c9c-93facd00a046
caps.latest.revision: 8
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 2c0adfc3f27bf8767f759a67001020cbbdff9f31
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="reverse-a-transaction-master-data-services"></a>Inverser une transaction (Master Data Services)
  Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], les administrateurs peuvent inverser une transaction lorsqu'une action doit être annulée. Les exemples de transactions sont les suivants : modifications apportées aux valeurs d'attribut, déplacements de hiérarchie ou suppressions de membres. Cette rubrique s’applique seulement aux transactions des entités ayant le type de journal des transactions « Attribut ». Accédez à la page de l’explorateur d’entités pour afficher l’historique de transaction des entités avec le type de journal des transactions « Membre ».  
  
## <a name="prerequisites"></a>Conditions préalables  
  
-   Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Gestion des versions** .  
  
-   Vous devez être administrateur de modèle. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-reverse-a-transaction"></a>Pour inverser une transaction  
  
1.  Dans la page d’accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , cliquez sur **Gestion des versions**.  
  
2.  Dans la barre de menus, cliquez sur **Transactions**.  
  
3.  Dans la page **Transactions** , dans la liste **Modèle** , sélectionnez un modèle.  
  
4.  Dans la liste **Version** , sélectionnez une version.  
  
5.  Cliquez dans la grille sur la ligne correspondant à la transaction que vous souhaitez inverser.  
  
6.  Cliquez sur **Inverser la transaction**.  
  
7.  Dans la boîte de dialogue de confirmation, cliquez sur **OK**. Une autre transaction est ajoutée à la grille pour enregistrer la transaction inversée.  
  
## <a name="see-also"></a>Voir aussi  
 [Transactions &#40; Master Data Services &#41;](../master-data-services/transactions-master-data-services.md)   
 [Réactiver un membre ou Collection &#40; Master Data Services &#41;](../master-data-services/reactivate-a-member-or-collection-master-data-services.md)  
 [Restauration de l’historique de révision de membre](../master-data-services/rollback-member-revision-history-master-data-services.md)
  
  