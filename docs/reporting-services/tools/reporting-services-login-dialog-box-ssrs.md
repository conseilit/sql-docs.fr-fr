---
title: Ouverture de session Reporting Services, boîte de dialogue (SSRS) | Microsoft Docs
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: tools
ms.topic: reference
f1_keywords:
- sql13.rtp.rptdesigner.reportservicelogin.f1
ms.assetid: 2037d797-0b61-44c7-931f-6c689c3fc733
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 2beb59a4cd0b1fefc8ff6ef9fafc376614cf0f3e
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47706197"
---
# <a name="reporting-services-login-dialog-box-ssrs"></a>Ouverture de session Reporting Services, boîte de dialogue (SSRS)
  Utilisez la boîte de dialogue **Ouverture de session Reporting Services** pour fournir les informations d'identification nécessaires à la publication de rapports sur le serveur de rapports.  
  
-   **Remarque** S’il s’agit de la première fois que vous publiez un rapport sur un serveur de rapports depuis que vous avez défini la propriété de déploiement **TargetServerURL** pour un projet, vérifiez que le nom du serveur comprend le mot **server** et non **reports**. Par exemple, `http://localhost/reportserver`, et non à `http://localhost/reports`. La spécification du répertoire `reports` sur le serveur local au lieu du répertoire `reportserver` provoque indirectement l'ouverture de cette boîte de dialogue. Pour plus d’informations sur la configuration de **TargetServerURL**, consultez [Définir des propriétés de déploiement &#40;Reporting Services&#41;](../../reporting-services/tools/set-deployment-properties-reporting-services.md).  
  
## <a name="options"></a>Options  
 **Server**  
 Affiche le nom du serveur de rapports. Par exemple, `http://localhost/reportserver`. Pour les serveurs de rapports qui utilisent un autre port que le port par défaut 80, incluez le numéro de port. Par exemple, `http://localhost:81/reportserver`.  
  
 **User name**  
 Tapez le nom d'utilisateur pour la connexion au service Web.  
  
 **Mot de passe**  
 Tapez le mot de passe pour la connexion au service Web.  
  
## <a name="see-also"></a> Voir aussi  
 [Connexions de données, sources de données et chaînes de connexion &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md)   
 [Spécifier des informations d'identification et de connexion pour les sources de données de rapport](../../reporting-services/report-data/specify-credential-and-connection-information-for-report-data-sources.md)   
 [Aide sur le concepteur de rapports via la touche F1](../../reporting-services/tools/report-designer-f1-help.md)  
  
  
