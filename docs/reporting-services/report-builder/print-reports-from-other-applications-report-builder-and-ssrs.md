---
title: Imprimer des rapports à partir d’autres applications (Générateur de rapports et SSRS) | Microsoft Docs
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: report-builder
ms.topic: conceptual
ms.assetid: a5560581-fd57-4a45-b7ea-43b21a8a7419
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 4c3db198ad707c298d48df5043627f327077a859
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47818757"
---
# <a name="print-reports-from-other-applications-report-builder-and-ssrs"></a>Imprimer des rapports à partir d'autres applications (Générateur de rapport et SSRS)
  Le Générateur de rapports fournit une option d'exportation qui vous permet d'afficher facilement un rapport dans d'autres applications. La commande **Exporter** est disponible dans la barre d’outils de rapport qui s’affiche en haut d’un rapport quand vous ouvrez ce dernier dans un navigateur ou une application web. L'exportation d'un rapport permet son affichage dans une autre application (par exemple, l'exportation d'un rapport vers Excel permet d'ouvrir le rapport dans [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)]). Pour l'impression, l'exportation d'un rapport est recommandée uniquement si l'application dispose de fonctionnalités d'impression spécifiques que vous souhaitez utiliser.  
  
 Pour exporter un rapport vers une autre application, cette dernière doit être installée. Par exemple, Adobe Acrobat Reader doit être préalablement installé sur votre ordinateur si vous choisissez une exportation au format Acrobat (PDF). Si vous choisissez d'exporter un rapport au format TIFF, le serveur de rapports place le rapport dans une application de visualisation associée au type de fichier TIFF. Bien que l'application utilisée dépende de la version de [!INCLUDE[msCoName](../../includes/msconame-md.md)] dont vous disposez, il s'agit généralement de l'outil Aperçu des images et des télécopies Windows. La résolution par défaut correspond à une résolution d'écran de 96 points par pouce (ppp). Vous pouvez augmenter la résolution dans l'outil Aperçu des images et des télécopies Windows à 300 ppp ou à 600 ppp de sorte qu'elle corresponde aux performances de votre imprimante. Pour plus d'informations sur le réglage de la résolution, consultez la documentation du produit Windows.  
  
 Si vous choisissez le format d'archive Web (également appelé MHTML), le rapport est exporté vers votre navigateur par défaut. L'impression à partir du navigateur peut entraîner l'ajout du chemin d'accès du rapport au bas de chaque page. Dans la plupart des cas, vous pouvez définir des options dans le navigateur afin que ces informations ne soient pas imprimées. Pour plus d'informations, consultez la documentation relative au navigateur utilisé.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a> Voir aussi  
 [Imprimer un rapport &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-builder/print-a-report-report-builder-and-ssrs.md)   
 [Imprimer des rapports à partir d’un navigateur à l’aide du contrôle d’impression &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-builder/print-reports-from-a-browser-with-the-print-control-report-builder-and-ssrs.md)   
 [Exporter des rapports &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-builder/export-reports-report-builder-and-ssrs.md)   
 [Exporter un rapport dans un autre type de fichier &#40;Générateur de rapports et SSRS&#41;](http://msdn.microsoft.com/library/b577568b-ecbd-44c3-be88-31dab6fc38a2)   
 [Recherche, affichage et gestion de rapports &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
