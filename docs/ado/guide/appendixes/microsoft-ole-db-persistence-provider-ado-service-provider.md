---
title: Fournisseur de persistance Microsoft OLE DB (fournisseur de services ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- providers [ADO], OLE DB persistence provider
- persistence provider [ADO]
- OLE DB persistence provider [ADO]
ms.assetid: e75ef0dc-2016-4fcc-8918-23311c0d4e02
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3b7ffeec1ca14aa57876ea14cbfdb536d9207c1f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47630777"
---
# <a name="microsoft-ole-db-persistence-provider-overview"></a>Présentation du fournisseur de persistance Microsoft OLE DB
Le fournisseur de persistance Microsoft OLE DB vous permet d’enregistrer un [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) l’objet dans un fichier et de restaurer ultérieurement qui **Recordset** objet à partir du fichier. Informations de schéma, les données et les modifications en attente sont conservés.

 Vous pouvez enregistrer le **Recordset** dans le format de données Table Gram ADTG (Advanced) propriétaire ou le format de langage XML (Extensible Markup) ouvert.

## <a name="provider-keyword"></a>Mot clé de fournisseur
 Pour appeler ce fournisseur, spécifiez le mot clé et la valeur suivante dans la chaîne de connexion.

```
"Provider=MSPersist"
```

## <a name="errors"></a>Erreurs
 Les erreurs suivantes émises par ce fournisseur peuvent être détectés dans votre application.

|Constante|Description|
|--------------|-----------------|
|E_BADSTREAM|Le fichier ouvert n’a pas un format valide (autrement dit, le format n’est pas ADTG ou XML).|
|E_CANTPERSISTROWSET|Le **Recordset** objet enregistré présente des caractéristiques qui l’empêchent d’être stocké.|

## <a name="remarks"></a>Notes
 Le fournisseur de persistance Microsoft OLE DB n’expose aucuns propriétés dynamiques.

 Uniquement paramétrables actuellement, hiérarchique **Recordset** objets ne peut pas être enregistrés.

 Pour plus d’informations sur le stockage persistant des **Recordset** , consultez [persistance des recordsets](../../../ado/guide/data/more-about-recordset-persistence.md).

 Lorsqu’un flux est utilisé pour ouvrir un **Recordset,** qu’il ne doit y avoir aucun paramètre spécifié autre que le *Source* paramètre de la **ouvrir** (méthode).

## <a name="see-also"></a>Voir aussi
[Fournisseur de persistance Microsoft OLE DB (fournisseur de services ADO)](../../../ado/guide/appendixes/microsoft-ole-db-persistence-provider-ado-service-provider.md)
