---
title: Destination DataReader | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.datareaderdest.f1
helpviewer_keywords:
- DataReader destination
- destinations [Integration Services], DataReader
ms.assetid: 56fcc4bf-c901-42c3-a71d-110039293431
caps.latest.revision: 30
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: dd7a53971e8042a391d4ebbd5a05cefa77b33345
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37207489"
---
# <a name="datareader-destination"></a>destination DataReader
  La destination DataReader expose les données d'un flux à l'aide de l'interface ADO.NET `DataReader`. Les données peuvent ensuite être utilisées par d'autres applications. Vous pouvez par exemple configurer la source de données d’un rapport [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] de sorte qu’elle utilise le résultat d’exécution d’un package [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] . Pour ce faire, vous devez créer un flux qui implémente la destination DataReader.  
  
 Pour plus d’informations sur l’accès aux valeurs de la destination DataReader et sur leur lecture par programmation, consultez [Chargement de la sortie d’un package local](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).  
  
## <a name="configuration-of-the-datareader-destination"></a>Configuration de la destination DataReader  
 Vous pouvez spécifier une valeur de délai d'attente de la destination DataReader et indiquer si la destination doit échouer en cas de dépassement de délai. Un délai d'attente est dépassé si l'application ne demande aucune donnée dans le délai spécifié.  
  
 La destination DataReader possède une entrée. Elle ne prend pas en charge de sortie d'erreur.  
  
 Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.  
  
 Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :  
  
-   [Propriétés communes](../common-properties.md)  
  
-   [Propriétés personnalisées de la destination DataReader](datareader-destination-custom-properties.md)  
  
 Pour plus d’informations sur la façon de définir des propriétés, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).  
  
  