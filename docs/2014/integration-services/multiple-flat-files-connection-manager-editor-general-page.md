---
title: Éditeur du Gestionnaire de connexions (Page Général) de fichiers plats multiples | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.general.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: 00129d43-2772-413b-bdf8-ac5de81cf4a5
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 3c7af9641ffc033c2c7173eaf74884700de7a3ed
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48176439"
---
# <a name="multiple-flat-files-connection-manager-editor-general-page"></a>Éditeur du gestionnaire de connexions de fichiers plats multiples (page Général)
  Utilisez la page **Général** de la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats multiples** pour sélectionner un groupe de fichiers ayant le même format de données et pour spécifier leur format de données. Une connexion de fichiers plats multiples permet à un package de se connecter à un groupe de fichiers texte ayant le même format.  
  
 Pour en savoir plus sur le gestionnaire de connexions de fichiers plats multiples, consultez [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).  
  
## <a name="options"></a>Options  
 **Nom du gestionnaire de connexions**  
 Spécifiez un nom unique pour la connexion de fichiers plats multiples dans le flux de travail. Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .  
  
 **Description**  
 Décrit la connexion. Il est recommandé d'indiquer ici l'usage auquel la connexion est destinée, de sorte que les packages soient correctement documentés et plus faciles à gérer.  
  
 **Noms de fichiers**  
 Tapez le chemin d'accès et les noms de fichiers à utiliser dans la connexion de fichiers plats multiples. Vous pouvez spécifier plusieurs fichiers à la fois en utilisant des caractères génériques (par exemple, C:\\*.txt) ou en utilisant la barre verticale (|) pour séparer plusieurs noms de fichiers. Tous les fichiers doivent avoir le même format de données.  
  
 **Parcourir**  
 Naviguez jusqu'aux noms de fichiers à utiliser dans la connexion de fichiers plats multiples. Vous pouvez sélectionner plusieurs fichiers. Tous les fichiers doivent avoir le même format de données.  
  
 **Paramètres régionaux**  
 Indiquez l'emplacement qui fournira les informations de classement et de conversion de la date et de l'heure.  
  
 **Unicode**  
 Indique s'il convient d'utiliser Unicode. L'utilisation d'Unicode vous empêche de spécifier une page de codes.  
  
 **Page de codes**  
 Spécifiez la page de codes pour du texte non-Unicode.  
  
 **Format**  
 Permet de préciser la mise en forme à utiliser : délimitée, à largeur fixe ou en drapeau à droite. Tous les fichiers doivent avoir le même format de données.  
  
|Valeur|Description|  
|-----------|-----------------|  
|Délimité|Les colonnes sont séparées par les séparateurs spécifiés à la page **Colonnes** .|  
|Largeur fixe|Les colonnes ont une largeur fixe que vous spécifiez en faisant glisser les lignes des marqueurs dans la page **Colonnes** .|  
|En drapeau à droite|Dans les fichiers en drapeau à droite, toutes les colonnes ont une largeur fixe, sauf la dernière, qui est délimitée par le séparateur de lignes défini dans la page **Colonnes** .|  
  
 **Qualificateur de texte**  
 Spécifiez le qualificateur de texte à utiliser. Par exemple, vous pouvez spécifier de mettre le texte entre guillemets.  
  
 **Séparateur de lignes d'en-tête**  
 Choisissez dans la liste des séparateurs de lignes d'en-tête ou entrez le texte de séparation.  
  
|Valeur|Description|  
|-----------|-----------------|  
|**{CR}{LF}**|La ligne d'en-tête est séparée par une combinaison retour chariot-saut de ligne.|  
|**{CR}**|La ligne d'en-tête est séparée par des retours chariot.|  
|**{LF}**|La ligne d'en-tête est séparée par des sauts de lignes.|  
|**Point-virgule {;}**|La ligne d'en-tête est séparée par des points-virgules.|  
|**Deux-points {:}**|La ligne d'en-tête est séparée par des deux-points.|  
|**Virgule {,}**|La ligne d'en-tête est séparée par des virgules.|  
|**Tabulation {t}**|La ligne d'en-tête est séparée par des tabulations.|  
|**Barre verticale {&#124;}**|La ligne d'en-tête est séparée par des barres verticales.|  
  
 **Lignes d'en-tête à ignorer**  
 Spécifiez le nombre de lignes d'en-tête à ignorer, le cas échéant.  
  
 **Noms de colonnes dans la première ligne de données**  
 Indique si des noms de colonne doivent être attendus ou fournis dans la première ligne de données.  
  
## <a name="see-also"></a>Voir aussi  
 [Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Éditeur du Gestionnaire de connexions de fichiers plats multiples &#40;Page colonnes&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md)   
 [Éditeur du Gestionnaire de connexions de fichiers plats multiples &#40;Page avancé&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md)   
 [Éditeur du Gestionnaire de connexions de fichiers plats multiples &#40;afficher un aperçu de la Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
