---
title: InternetTimeout, propriété (RDS) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- InternetTimeout property [ADO]
ms.assetid: 4d1c8892-4bbc-4e71-bf4b-ba52c0ea9549
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 7ccb9aa7fe10fd9024e283a6134c581ea98c70c1
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47828287"
---
# <a name="internettimeout-property-rds"></a>InternetTimeout, propriété (RDS)
Indique le nombre de millisecondes à attendre avant l’expiration d’une requête.  
  
> [!IMPORTANT]
>  Depuis Windows 8 et Windows Server 2012, composants de serveur Services Bureau à distance ne sont plus inclus dans le système d’exploitation Windows (voir Windows 8 et [Guide de compatibilité de Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) pour plus de détails). Composants du client RDS seront supprimées dans une future version de Windows. Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. Les applications qui utilisent des services Bureau à distance doivent migrer vers [Service de données WCF](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="settings-and-return-values"></a>Paramètres et valeurs de retour  
 Définit ou retourne un **Long** valeur qui représente le nombre de millisecondes avant qu’une requête arrive à expiration.  
  
## <a name="remarks"></a>Notes  
 Cette propriété s’applique uniquement aux demandes envoyées avec les protocoles HTTP ou HTTPS.  
  
 Demandes dans un environnement à trois niveaux peuvent prendre quelques minutes. Cette propriété permet de spécifier plus de temps pour les requêtes longues.  
  
## <a name="applies-to"></a>S'applique à  
  
|||  
|-|-|  
|[DataControl, objet (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)|[DataSpace, objet (RDS)](../../../ado/reference/rds-api/dataspace-object-rds.md)|  
  
## <a name="see-also"></a>Voir aussi  
 [InternetTimeout, propriété-Exemple (VB)](../../../ado/reference/rds-api/internettimeout-property-example-vb.md)   
 [InternetTimeout, exemple de propriété (VC++)](../../../ado/reference/rds-api/internettimeout-property-example-vc.md)   
 

