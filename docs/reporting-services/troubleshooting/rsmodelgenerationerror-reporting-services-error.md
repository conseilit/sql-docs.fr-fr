---
title: rsModelGenerationError - Erreur Reporting Services | Microsoft Docs
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: troubleshooting
ms.topic: conceptual
helpviewer_keywords:
- rsModelGenerationError
ms.assetid: 3a0ad63f-87f9-4ca1-b0c2-c85fa991634a
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 9a8c2dc17bbb6599acbb363d7d8f8b9c51bc061a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47707677"
---
# <a name="rsmodelgenerationerror---reporting-services-error"></a>rsModelGenerationError - Erreur Reporting Services
    
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|ID d'événement|rsRenderingError|  
|Source de l'événement|Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings|  
|Composant|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|Texte du message|Une erreur s'est produite lors de la génération du modèle. (rsModelGenerationError) (ReportingServicesLibrary) %1|  
  
## <a name="explanation"></a>Explication  
 Le modèle de rapport n'a pas pu être généré. Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 et les versions antérieures, cette erreur s'affiche, en règle générale, si l'objet System.Data.DataSet ne peut pas gérer une table ou une relation au sein du schéma de la base de données, par exemple lorsque deux clés étrangères sont définies sur la même colonne d'une table.  
  
## <a name="user-action"></a>Action de l'utilisateur  
 Pour déterminer précisément la raison pour laquelle vous avez reçu ce message, consultez les fichiers journaux du serveur de rapports qui se trouvent dans le dossier \Microsoft SQL Server\\<Instance SQL Server\>\Reporting Services\LogFiles.  
  
## <a name="internal-only"></a>Interne uniquement  
  
