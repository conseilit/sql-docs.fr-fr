---
title: Recordset Destination | Documents Microsoft
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.recordsetdest.f1
helpviewer_keywords:
- Recordset destination
- ADO recordsets [Integration Services]
- destinations [Integration Services], Recordset
- in-memory ADO recordsets [Integration Services]
ms.assetid: be973cf1-c4ff-49f8-987e-314c08ef98e4
caps.latest.revision: 47
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: ba67dbc528d781325f35a7b6c1556b1debee1171
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="recordset-destination"></a>Destination de l'ensemble d'enregistrements
  La destination de l'ensemble d'enregistrements crée et remplit un ensemble d'enregistrements ADO en mémoire. La forme de l'ensemble d'enregistrements est définie par l'entrée de la destination d'ensemble d'enregistrements au moment de la conception.  
  
## <a name="configuration-of-the-recordset-destination"></a>Configuration de la destination de l'ensemble d'enregistrements  
 Pour configurer la destination de l'ensemble d'enregistrements,vous devez spécifier la variable qui contient l'ensemble d'enregistrements ADO.  
  
 Au moment de l’exécution, un ensemble d’enregistrements ADO est écrit dans la variable du type, Object, qui est spécifié dans la propriété VariableName de la destination de l’ensemble d’enregistrements. La variable rend ensuite l'ensemble d'enregistrements disponible en dehors du flux de données, où il peut être utilisé par des scripts et d'autres éléments de package.  
  
 Cette source possède une entrée. Elle ne prend pas en charge de sortie d'erreur.  
  
 Vous pouvez définir des propriétés au moyen du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.  
  
 La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation. Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programme, cliquez sur l'une des rubriques suivantes :  
  
-   [Propriétés communes](http://msdn.microsoft.com/library/51973502-5cc6-4125-9fce-e60fa1b7b796)  
  
-   [Propriétés personnalisées de la destination du jeu d'enregistrements](../../integration-services/data-flow/recordset-destination-custom-properties.md)  
  
 Pour plus d’informations sur la façon de définir des propriétés, consultez [Définir les propriétés d’un composant de flux de données](../../integration-services/data-flow/set-the-properties-of-a-data-flow-component.md).  
  
## <a name="related-tasks"></a>Tâches associées  
 [Utiliser une destination de jeu d'enregistrements](../../integration-services/data-flow/use-a-recordset-destination.md)  
  
  