---
title: Options de validation d’abonnement (Abonnements de fusion) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.validate.mergeoptions.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: 4958c4ab-2025-42ce-b836-6fb4e9e6f24d
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: c966b258a333b53a8e14686ccb32228655ce7b3a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47650107"
---
# <a name="subscription-validation-options-merge-subscriptions"></a>Options de validation d'abonnement (Abonnements de fusion)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  Utilisez la boîte de dialogue **Options de validation d'abonnement** pour indiquer si la validation doit utiliser un nombre de lignes uniquement ou un nombre de lignes et une somme de contrôle binaire.  
  
## <a name="options"></a>Options  
 **Vérifier uniquement le nombre de lignes**  
 Sélectionnez cette option pour indiquer si la table au niveau de l'Abonné a le même nombre de lignes que la table sur le serveur de publication. Cette méthode ne valide pas le contenu des correspondances de lignes. La validation du nombre de lignes fournit une approche allégée de la validation qui vous permet de savoir qu'il existe des problèmes au niveau des données.  
  
 **Vérifier le nombre de lignes et comparer les totaux de contrôle pour vérifier les données de ligne**  
 Outre le comptage des lignes sur le serveur de publication et sur l'Abonné, une somme de contrôle de toutes les données est calculée à l'aide de l'algorithme de somme de contrôle binaire. Si le nombre de lignes est erroné, la somme de contrôle n'est pas effectuée. Cette option n'est pas valide pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)].  
  
## <a name="see-also"></a> Voir aussi  
 [Valider des données sur l’abonné](../../relational-databases/replication/validate-data-at-the-subscriber.md)   
 [Valider des données répliquées](../../relational-databases/replication/validate-replicated-data.md)  
  
  
