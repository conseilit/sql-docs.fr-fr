---
title: 'Étape 6 : Les modifications sont envoyées au serveur (didacticiel RDS) | Microsoft Docs'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS tutorial [ADO], changes sent to server
ms.assetid: b1e927d6-7d50-4978-9eef-045043cdce7a
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2d79fb88ba9371d1767561c7190818c135fd0a03
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47680267"
---
# <a name="step-6-changes-are-sent-to-the-server-rds-tutorial"></a>Étape 6 : Les changements sont envoyés au serveur (tutoriel RDS)
Si le **Recordset** objet est modifié, toutes les modifications (autrement dit, les lignes qui sont ajoutées, modifiées ou supprimées) peuvent être envoyées sur le serveur.  
  
> [!NOTE]
>  Le comportement par défaut des services Bureau à distance peut être appelé implicitement avec des objets ADO et le fournisseur Microsoft OLE DB d’accès distant. Les requêtes peuvent renvoyer **Recordset**s et modifié **Recordset**s peut mettre à jour la source de données. Ce didacticiel n’appelle pas les services Bureau à distance avec des objets ADO, mais il s’agit d’aspect si c’était le cas :  
  
```  
Dim rs as New ADODB.Recordset  
rs. "SELECT * FROM Authors","=MS Remote;=Pubs;" & _  
=http://yourServer;=SQLOLEDB;"  
...              ' Edit the Recordset.  
rs.   ' The equivalent of   
...  
```  
  
 **Partie A** Assume pour ce cas vous n’avez utilisé le [RDS. DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) et qu’un **Recordset** objet est maintenant associé le **RDS. DataControl**. Le [SubmitChanges](../../../ado/reference/rds-api/submitchanges-method-rds.md) méthode met à jour la source de données avec les modifications apportées à la **Recordset** si l’objet le [Server](../../../ado/reference/rds-api/server-property-rds.md) et [Connect](../../../ado/reference/rds-api/connect-property-rds.md) propriétés sont toujours définies.  
  
```  
Sub RDSTutorial6A()  
Dim DC as New RDS.DataControl  
Dim RS as ADODB.Recordset  
DC. = "http://yourServer"  
DC. = "DSN=Pubs"  
DC. = "SELECT * FROM Authors"  
DC.  
...  
Set RS = DC.  
   ' Edit the Recordset.  
...  
DC.  
...  
```  
  
 **Partie B** vous pouvez également vous pouvez mettre à jour le serveur avec le [RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) objet et en spécifiant une connexion et un **Recordset** objet.  
  
```  
Sub RDSTutorial6B()  
Dim DS As New RDS.DataSpace  
Dim RS As ADODB.Recordset  
Dim DC As New RDS.DataControl  
Dim DF As Object  
Dim blnStatus As Boolean  
Set DF = DS.("RDSServer.DataFactory", "http://yourServer")  
Set RS = DF. ("DSN=Pubs", "SELECT * FROM Authors")  
DC. = RS    ' Visual controls can now bind to DC.  
    ' Edit the Recordset.  
blnStatus = DF."DSN=Pubs", RS  
End Sub  
```  
  
 **Il s’agit de la fin du didacticiel.**  
  
> [!IMPORTANT]
>  Depuis Windows 8 et Windows Server 2012, composants de serveur Services Bureau à distance ne sont plus inclus dans le système d’exploitation Windows (voir Windows 8 et [Guide de compatibilité de Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) pour plus de détails). Composants du client RDS seront supprimées dans une future version de Windows. Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. Les applications qui utilisent des services Bureau à distance doivent migrer vers [Service de données WCF](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="see-also"></a>Voir aussi  
 [Fournisseur de communication à distance Microsoft OLE DB (fournisseur de services ADO)](../../../ado/guide/appendixes/microsoft-ole-db-remoting-provider-ado-service-provider.md)   
 [Didacticiel RDS](../../../ado/guide/remote-data-service/rds-tutorial.md)   
 [Didacticiel RDS (VBScript)](../../../ado/guide/remote-data-service/rds-tutorial-vbscript.md)   
