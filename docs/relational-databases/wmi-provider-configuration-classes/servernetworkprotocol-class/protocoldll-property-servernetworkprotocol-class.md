---
title: Protocoldll, propriété (classe ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: reference
apiname:
- ProtocolDLL Property (ServerNetworkProtocol Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- ProtocolDLL property
ms.assetid: ac386558-392e-46f3-97f8-382f267b7fca
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 2fc4a18e1f5a03104fbdbad680640bc2d51fbf64
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47747657"
---
# <a name="protocoldll-property-servernetworkprotocol-class"></a>Propriété ProtocolDLL (classe ServerNetworkProtocol)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  Obtient le nom du fichier .dll requis par un protocole réseau serveur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object.ProtocolDLL [= value]  
```  
  
## <a name="parts"></a>Éléments  
 *object*  
 A [classe ServerNetworkProtocol](../../../relational-databases/wmi-provider-configuration-classes/servernetworkprotocol-class/servernetworkprotocol-class.md) qui représente le protocole réseau utilisé par l'instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour  
 Valeur de chaîne qui spécifie le fichier .dll de protocole requis par le protocole réseau serveur.  
  
## <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Configuration des bibliothèques réseau et des protocoles réseau du serveur](http://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  
