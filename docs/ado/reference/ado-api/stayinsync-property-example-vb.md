---
title: StayInSync, propriété-Exemple (VB) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- StayInSync property [ADO], Visual Basic example
ms.assetid: b682bcc3-04b3-42b0-86f4-c17e0cd29baf
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4ff9e4c7f1903a187869f15573893d9f7d0c2fe7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47851687"
---
# <a name="stayinsync-property-example-vb"></a>StayInSync, exemple de propriété (VB)
Cet exemple montre comment la [StayInSync](../../../ado/reference/ado-api/stayinsync-property.md) propriété facilite l’accès aux lignes dans une liste hiérarchique [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
 La boucle externe affiche le nom et prénom de chaque auteur, l’état et identification. Ajouté **Recordset** pour chaque ligne est récupérée à partir de la [champs](../../../ado/reference/ado-api/fields-collection-ado.md) collection et attribué automatiquement aux **affectation** par le **StayInSync**  propriété chaque fois que le parent **Recordset** se déplace vers une nouvelle ligne. La boucle interne affiche quatre champs de chaque ligne dans l’objet recordset ajouté.  
  
```  
'BeginStayInSyncVB  
Public Sub Main()  
    On Error GoTo ErrorHandler  
  
    Dim Cnxn As ADODB.Connection  
    Dim rst As ADODB.Recordset  
    Dim rstTitleAuthor As New ADODB.Recordset  
    Dim strCnxn As String  
  
    ' Open the connection with Data Shape attributes  
    Set Cnxn = New ADODB.Connection  
    strCnxn = "Provider=MSDataShape;Data Provider='sqloledb';Data Source='MySqlServer';" & _  
        "Initial Catalog='Pubs';Integrated Security='SSPI';"  
    Cnxn.Open strCnxn  
  
    ' Create a recordset  
    Set rst = New ADODB.Recordset  
    rst.StayInSync = True  
    rst.Open "SHAPE {select * from Authors} " & _  
                   "APPEND ( { select * from titleauthor} AS chapTitleAuthor " & _  
                   "RELATE au_id TO au_id) ", Cnxn, , , adCmdText  
  
    Set rstTitleAuthor = rst("chapTitleAuthor").Value  
    Do Until rst.EOF  
        Debug.Print rst!au_fname & " " & rst!au_lname & " " & _  
                   rst!State & " " & rst!au_id  
  
        Do Until rstTitleAuthor.EOF  
            Debug.Print rstTitleAuthor(0) & " " & rstTitleAuthor(1) & " " & _  
                   rstTitleAuthor(2) & " " & rstTitleAuthor(3)  
            rstTitleAuthor.MoveNext  
        Loop  
  
        rst.MoveNext  
    Loop  
  
    ' Clean up  
    rst.Close  
    Cnxn.Close  
    Set rst = Nothing  
    Set Cnxn = Nothing  
    Exit Sub  
  
ErrorHandler:  
    ' Clean up  
    If Not rst Is Nothing Then  
        If rst.State = adStateOpen Then rst.Close  
    End If  
    Set rst = Nothing  
  
    If Not Cnxn Is Nothing Then  
        If Cnxn.State = adStateOpen Then Cnxn.Close  
    End If  
    Set Cnxn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
'EndStayInSyncVB  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Collection de champs (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)   
 [Objet Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)   
 [StayInSync, propriété](../../../ado/reference/ado-api/stayinsync-property.md)
