---
title: MSSQL_ENG020596 | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020596 error
ms.assetid: fa33627c-2e99-4be3-9424-52ab83446e07
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: de689f8a0239ce81b9fcf99b846f8d4767a4dbde
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47606517"
---
# <a name="mssqleng020596"></a>MSSQL_ENG020596
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="message-details"></a>Détails du message  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|20596|  
|Source de l'événement|MSSQLSERVER|  
|Composant|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nom symbolique||  
|Texte du message|Seul '%1!' ou les membres de db_owner peuvent supprimer l'Agent anonyme.|  
  
## <a name="explanation"></a>Explication  
 Vous ne disposez pas des autorisations suffisantes pour supprimer l'agent pour l'abonnement anonyme. Le nom de connexion utilisé lors de l’appel de [sp_dropanonymousagent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql.md) doit être un membre du rôle de serveur fixe **sysadmin** sur le serveur de distribution ou du rôle de base de données fixe **db_owner** dans la base de données de distribution, ou bien l’utilisateur doit être celui qui a initié la première exécution de l’agent.  
  
## <a name="user-action"></a>Action de l'utilisateur  
 Connectez-vous avec les informations d'identification appropriées et exécutez **sp_dropanonymousagent**.  
  
## <a name="see-also"></a> Voir aussi  
 [Guide de référence des erreurs et des événements &#40;réplication&#41;](../../relational-databases/replication/errors-and-events-reference-replication.md)  
  
  
