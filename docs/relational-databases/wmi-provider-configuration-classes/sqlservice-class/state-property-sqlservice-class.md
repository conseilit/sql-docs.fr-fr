---
title: State, propriété (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: reference
apiname:
- State Property (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- State property
ms.assetid: 9e09f419-947c-4d4b-9a49-2d3396c847cd
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: bed08f87e3d93eb3d18a86fd0931a4359a67ffea
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47644167"
---
# <a name="state-property-sqlservice-class"></a>Propriété State (classe SqlService)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  Obtient ou définit l'état actuel du service.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object.State [= value]  
```  
  
## <a name="parts"></a>Éléments  
 *object*  
 Objet de [classe SqlService](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) qui représente le service.  
  
## <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour  
 Valeur uint32 qui spécifie l'état du service.  
  
 Il peut s'agir de l'une des valeurs suivantes.  
  
 1  
 Arrêté. Le service est arrêté.  
  
 2  
 Démarrage en attente. Le service est en attente de démarrage.  
  
 3  
 Arrêt en attente. Le service est en attente d'arrêt.  
  
 4  
 En cours d'exécution. Le service est en cours d'exécution.  
  
 5  
 Continuation en attente. Le service est en attente de continuation.  
  
 6  
 Pause en attente. Le service est en attente de pause.  
  
 7  
 Suspendu. Le service est suspendu.  
  
## <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Démarrage et arrêt des Services](http://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
