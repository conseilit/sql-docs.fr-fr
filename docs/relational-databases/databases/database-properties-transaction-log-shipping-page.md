---
title: Propriétés de la base de données (page Envoi des journaux de transactions) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- sql13.swb.databaseproperties.logshipping.f1
ms.assetid: 72c4e539-fe11-4d57-b977-65b418d5916f
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 8f38c5d29192b5f61decb0a4b229a5faefbb637b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47801969"
---
# <a name="database-properties-transaction-log-shipping-page"></a>Propriétés de la base de données (page Envoi des journaux de transactions)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Cette page vous permet de configurer et de modifier les propriétés de copie des journaux de transactions d'une base de données.  
  
 Pour obtenir des explications sur les concepts de copie des journaux de transaction, consultez [À propos de la copie des journaux de transaction &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).  
  
## <a name="options"></a>Options  
 **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**  
 Active la base de données comme base de données primaire de copie des journaux de transactions. Activez cette option, puis configurez les options restantes dans cette page. Si vous désactivez cette case à cocher, la configuration de copie des journaux de transactions est supprimée pour la base de données.  
  
 **Paramètres de sauvegarde**  
 Cliquez sur **Paramètres de sauvegarde** pour configurer la planification, l’emplacement, l’alerte et les paramètres d’archivage de sauvegarde.  
  
 **Planification de la sauvegarde**  
 Indique la planification de sauvegarde actuellement sélectionnée pour la base de données primaire. Cliquez sur **Paramètres de sauvegarde** pour modifier ces paramètres.  
  
 **Date de la dernière sauvegarde créée**  
 Indique la date et l'heure de la dernière sauvegarde des journaux de transactions de la base de données primaire.  
  
 **Instances de serveurs et bases de données secondaires**  
 Répertorie les serveurs et les bases de données secondaires actuellement configurés pour la base de données primaire. Mettez en surbrillance une base de données, puis cliquez sur **...** pour modifier les paramètres associés à cette base de données secondaire.  
  
 **Ajouter**  
 Cliquez sur **Ajouter** pour ajouter une base de données secondaire à la configuration de copie des journaux de transactions pour cette base de données primaire.  
  
 **Supprimer**  
 Supprime une base de données sélectionnée de cette configuration de copie des journaux de transactions. Sélectionnez la base de données, puis cliquez sur **Supprimer**.  
  
 **Utiliser une instance du serveur moniteur**  
 Permet de définir une instance de serveur moniteur pour cette configuration de copie des journaux de transactions. Activez la case à cocher **Utiliser une instance du serveur moniteur** , puis cliquez sur **Paramètres** pour spécifier l'instance de serveur moniteur.  
  
 **Instance du serveur moniteur**  
 Spécifie l'instance de serveur moniteur actuellement configurée pour cette configuration de copie des journaux de transactions.  
  
 **Paramètres**  
 Permet de configurer l'instance de serveur moniteur pour une configuration de copie des journaux de transactions. Cliquez sur **Paramètres** pour configurer cette instance de serveur moniteur.  
  
 **Créer un script de configuration**  
 Génère un script pour la configuration de la copie des journaux de transactions avec les paramètres que vous avez sélectionnés. Cliquez sur **Créer un script de configuration**, puis sélectionnez une destination de sortie pour le script.  
  
> [!IMPORTANT]  
>  Avant de créer un script des paramètres pour une base de données secondaire, vous devez appeler la boîte de dialogue **Paramètres de base de données secondaire** . L'appel de cette boîte de dialogue vous connecte au serveur secondaire et récupère les paramètres actuels de la base de données secondaire, nécessaires pour générer le script.  
  
## <a name="see-also"></a> Voir aussi  
 [Procédures stockées de copie des journaux de transaction &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql.md)   
 [Tables de copie des journaux de transaction &#40;Transact-SQL&#41;](../../relational-databases/system-tables/log-shipping-tables-transact-sql.md)  
  
  
