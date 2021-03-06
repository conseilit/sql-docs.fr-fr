---
title: Boîte de dialogue Propriétés du package | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageprop.general.f1
- sql12.ssis.ssms.packageproperties.f1
ms.assetid: a70acbf4-5f5c-4606-8ce4-8eb3684233de
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 9d3bb5f71617371d4ff360242cf3076e73fdbbea
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48070671"
---
# <a name="package-properties-dialog-box"></a>Propriétés du package, boîte de dialogue
  Utilisez la boîte de dialogue **Propriétés du package** pour afficher et gérer les propriétés des packages stockés sur le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .  
  
 Pour plus d’informations, consultez [Serveur Integration Services &#40;SSIS&#41;](integration-services-ssis-server-and-catalog.md).  
  
 **Que voulez-vous faire ?**  
  
-   [Ouvrir la boîte de dialogue Propriétés du package](#open_dialog)  
  
-   [Configurer les options](#options)  
  
##  <a name="open_dialog"></a> Ouvrir la boîte de dialogue Propriétés du package  
  
1.  Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .  
  
     Vous vous connectez à l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données SSISDB.  
  
2.  Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .  
  
3.  Développez le nœud **SSISDB** .  
  
4.  Développez le dossier qui contient le package dont vous souhaitez afficher les propriétés.  
  
5.  Cliquez avec le bouton droit sur le package, puis sélectionnez **Propriétés**.  
  
##  <a name="options"></a> Configurer les options  
 Utilisez la page **Général** pour afficher les propriétés du package sélectionné.  
  
 Toutes les propriétés affichées dans la page **Général** sont en lecture seule.  
  
 **Nom**  
 Affiche le nom du package.  
  
 **Identificateur**  
 Indique l'ID du package.  
  
 **Point d'entrée**  
 La valeur de `True` indique que le package est démarré directement. La valeur de `False` indique que le package est démarré par un autre package à l’aide de la tâche d’exécution de Package. La valeur par défaut est `True`.  
  
 Vous définissez cette propriété dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pour les packages parent et enfant en cliquant avec le bouton droit sur le package dans l’Explorateur de solutions et en sélectionnant **Package de point d’entrée**.  
  
 **Description**  
 Affiche la description facultative du package.  
  
  
