---
title: Afficher les propriétés d’une facette de la gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facet properties
ms.assetid: 022a244c-c2e7-4467-b9a2-c7a27859be22
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: e620f2a6fa6377b5a90770d94d53cd8983d3ec15
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47638027"
---
# <a name="view-the-properties-of-a-policy-based-management-facet"></a>Afficher les propriétés d'une facette de gestion basée sur des stratégies
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Cette rubrique explique comment afficher les propriétés d'une facette de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
 **Dans cette rubrique**  
  
-   **Avant de commencer :**  
  
     [Sécurité](#Security)  
  
-   **Pour afficher les propriétés d'une facette à l'aide de :**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Avant de commencer  
  
###  <a name="Security"></a> Sécurité  
  
####  <a name="Permissions"></a> Permissions  
 Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.  
  
##  <a name="SSMSProcedure"></a> Utilisation de SQL Server Management Studio  
  
#### <a name="to-view-the-properties-of-a-facet"></a>Pour afficher les propriétés d'une facette  
  
1.  Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient la facette dont vous souhaiter afficher les propriétés.  
  
2.  Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .  
  
3.  Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.  
  
4.  Cliquez sur le signe plus (+) pour développer le dossier **Facettes** .  
  
5.  Cliquez avec le bouton droit sur la facette dont vous souhaitez afficher les propriétés, puis sélectionnez **Propriétés**. Pour plus d’informations sur les options disponibles dans la boîte de dialogue **Propriétés de la facette –***nom_facette*, consultez [Boîte de dialogue Propriétés de la facette, page Général](../../relational-databases/policy-based-management/facet-properties-dialog-box-general-page.md), [Boîte de dialogue Propriétés de la facette, page Stratégies dépendantes](../../relational-databases/policy-based-management/facet-properties-dialog-box-dependent-policies-page.md) et [Boîte de dialogue Propriétés de la facette, page Conditions dépendantes](../../relational-databases/policy-based-management/facet-properties-dialog-box-dependent-conditions-page.md).  
  
6.  Lorsque vous avez terminé, cliquez sur **Fermer**.  
  
  
