---
title: Afficher la liste des packages sur le serveur Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 67a992d1-7524-4f4b-b3d8-ebd9e5ea82a8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 895833726af07b7b650ab26c033eb1ee8018b499
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47682327"
---
# <a name="view-the-list-of-packages-on-the-integration-services-server"></a>Afficher la liste des packages sur le serveur Integration Services
  Vous pouvez afficher la liste des packages stockés sur le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] de deux façons :  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] Accès Transact-SQL  
 Pour afficher la liste des packages stockés sur le serveur, interrogez la vue [catalog.packages &#40;base de données SSISDB&#41;](../../integration-services/system-views/catalog-packages-ssisdb-database.md).  
  
 Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
 Pour afficher les packages stockés sur le serveur à l’aide de l’Explorateur d’objets dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], procédez comme indiqué ci-dessous.  
  
### <a name="to-view-packages-using-includessmanstudiofullincludesssmanstudiofull-mdmd"></a>Pour afficher les packages à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
1.  Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] . Autrement dit, connectez-vous à l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .  
  
2.  Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .  
  
3.  Développez le nœud **Catalogues Integration Services** pour afficher le nœud **SSISDB** .  
  
4.  Développez le nœud **SSISDB** pour afficher une liste d'un ou de plusieurs dossiers. Chaque dossier contient un ou plusieurs projets dans le dossier **Projets** et chaque projet contient un ou plusieurs packages dans le dossier **Packages** .  
  
  
