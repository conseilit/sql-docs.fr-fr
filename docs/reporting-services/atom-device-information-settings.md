---
title: ATOM Device Information Settings | Documents Microsoft
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
caps.latest.revision: 7
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 847b387a04f302c731ed3cb1d2c31df57e202680
ms.contentlocale: fr-fr
ms.lasthandoff: 08/09/2017

---
# <a name="atom-device-information-settings"></a>Paramètres d'informations de périphérique ATOM
  Les paramètres d'informations de périphériques pour l'extension de rendu Atom prennent en charge la soumission du nom d'un flux Atom et de l'encodage de caractères à utiliser.  
  
 Le tableau suivant répertorie les paramètres des informations de périphériques pour le rendu dans un document de service de données.  
  
|Paramètre|Value|  
|-------------|-----------|  
|**DataFeed**|Si spécifié, restitue le flux Atom correspondant au nom de flux fourni dans ce paramètre. Dans le cas contraire, restitue le document de service Atom pour le rapport. Identificateur unique de la source de données générée automatiquement. Cette valeur est utilisée en interne et vous ne devez pas le modifier.|  
|**Encodage**|Nom IANA (Internet Assigned Numbers Authority) d'un encodage de caractères pris en charge par le .NET Framework. La valeur par défaut est **UTF-8**. Les exemples d'autres valeurs incluent ASCII, UTF-7 et UTF-16.|  
  
## <a name="see-also"></a>Voir aussi  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [Passage de paramètres d’informations de périphérique aux Extensions de rendu](../reporting-services/report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Personnaliser les paramètres d’Extension de rendu dans RSReportServer.Config](../reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Informations techniques de référence &#40; SSRS &#41;](../reporting-services/technical-reference-ssrs.md)  
  
  