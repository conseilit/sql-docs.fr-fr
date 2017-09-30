---
title: "Exemple de propriété d’état (champ) (VB) | Documents Microsoft"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Status property [ADO Field], Visual Basic example
ms.assetid: fdd09b60-39c7-44be-8008-e891a031f80e
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 91c3418fea062661ffba94feb791d700301ff097
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="status-property-example-field-vb"></a>Exemple de propriété d’état (champ) (VB)
L’exemple suivant ouvre un document à partir d’un dossier en lecture/écriture à l’aide du [fournisseur de publication Internet](../../../ado/guide/appendixes/microsoft-ole-db-provider-for-internet-publishing.md). Le [état](../../../ado/reference/ado-api/status-property-ado-field.md) propriété d’un [champ](../../../ado/reference/ado-api/field-object.md) objet de la [enregistrement](../../../ado/reference/ado-api/record-object-ado.md) d’abord la valeur **adFieldPendingInsert**, puis être mis à jour vers **adFieldOk**.  
  
```  
'BeginStatusFieldVB  
  
 ' to integrate this code replace the values in the source string  
  
Sub Main()  
  
   Dim File As ADODB.Record  
   Dim strFile As String  
   Dim Cnxn As ADODB.Connection  
   Dim strCnxn As String  
  
   Set Cnxn = New ADODB.Connection  
   strCnxn = "url=http://MyServer/"  
   Cnxn.Open strCnxn  
  
   Set File = New ADODB.Record  
   strFile = "Folder/FileName"  
   ' Open a read/write document  
   File.Source = strFile  
   File.ActiveConnection = Cnxn  
   File.Mode = adModeReadWrite  
   File.Open  
  
   Debug.Print "Append a couple of fields"  
  
   File.Fields.Append "chektest:fld1", adWChar, 42, adFldUpdatable, "fld1"  
   File.Fields.Append "chektest:fld2", adWChar, 42, adFldUpdatable, "fld2"  
  
   Debug.Print "status for the fields"  
   Debug.Print File.Fields("chektest:fld1").Status 'adfldpendinginsert  
   Debug.Print File.Fields("chektest:fld2").Status 'adfldpendinginsert  
  
    'turn off error-handling to verify field status  
   On Error Resume Next  
  
   File.Fields.Update  
  
   Debug.Print "Update succeeds"  
   Debug.Print File.Fields("chektest:fld1").Status 'adfldpendinginsert + adFieldUnavailable  
   Debug.Print File.Fields("chektest:fld2").Status 'adfldpendinginsert + adFieldUnavailable  
  
    ' resume default error-handling  
   On Error GoTo 0  
  
     ' clean up  
    File.Close  
    Cnxn.Close  
    Set File = Nothing  
    Set Cnxn = Nothing  
  
End Sub  
'EndStatusFieldVB  
```  
  
 L’exemple suivant supprime un connu **champ** d’un **enregistrement** ouvert à partir d’un document. Le **état** propriété sera tout d’abord être définie sur **adFieldOK**, puis **adFieldPendingUnknown**.  
  
```  
Attribute VB_Name = "StatusField"  
```  
  
 Le code suivant supprime un **champ** d’un **enregistrement** ouvert sur un document en lecture seule. **État** a la valeur **adFieldPendingDelete**. À [mise à jour](../../../ado/reference/ado-api/update-method.md), la suppression échouera et **état** sera **adFieldPendingDelete** plus **adFieldPermissionDenied**. [CancelUpdate](../../../ado/reference/ado-api/cancelupdate-method-ado.md) efface l’attente **état** paramètre.  
  
```  
Attribute VB_Name = "StatusField"  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Objet Field](../../../ado/reference/ado-api/field-object.md)   
 [Objet d’enregistrement (ADO)](../../../ado/reference/ado-api/record-object-ado.md)   
 [Propriété d’état (champ ADO)](../../../ado/reference/ado-api/status-property-ado-field.md)