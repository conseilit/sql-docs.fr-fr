---
title: Format de persistance XML | Documents Microsoft
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML persistence [ADO], persistence format
ms.assetid: 6e146738-ac4d-47bb-b6cd-d87b2260aead
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 8694aac4f8699d102d94664862f5ad357579eab9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="xml-persistence-format"></a>Format de persistance XML
ADO utilise l’encodage UTF-8 pour le flux de données XML.  
  
 Le format XML ADO est divisé en deux sections : une section de schéma suivie de la section de données. Voici un exemple de fichier XML pour la table des expéditeurs (Shippers) à partir de la base de données Northwind. Différentes parties du document XML sont présentées à l’exemple suivant.  
  
## <a name="remarks"></a>Notes  
  
```  
<xml xmlns:s="uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C14882"   
xmlns:dt="uuid:C2F41010-65B3-11d1-A29F-00AA00C14882"   
xmlns:rs="urn:schemas-microsoft-com:rowset"   
xmlns:z="#RowsetSchema">   
  <s:Schema id="RowsetSchema">   
    <s:ElementType name="row" content="eltOnly" rs:updatable="true">   
      <s:AttributeType name="ShipperID" rs:number="1"   
        rs:basetable="shippers" rs:basecolumn="ShipperID"  
        rs:keycolumn="true">   
        <s:datatype dt:type="int" dt:maxLength="4" rs:precision="10"   
          rs:fixedlength="true" rs:maybenull="false"/>   
      </s:AttributeType>   
      <s:AttributeType name="CompanyName" rs:number="2"   
        rs:nullable="true" rs:write="true" rs:basetable="shippers"   
        rs:basecolumn="CompanyName">   
        <s:datatype dt:type="string" dt:maxLength="40" />   
      </s:AttributeType>   
      <s:AttributeType name="Phone" rs:number="3" rs:nullable="true"   
        rs:write="true" rs:basetable="shippers"   
        rs:basecolumn="Phone">   
        <s:datatype dt:type="string" dt:maxLength="24"/>   
      </s:AttributeType>   
      <s:extends type="rs:rowbase"/>   
    </s:ElementType>   
  </s:Schema>   
  
  <rs:data>   
    <z:row ShipperID="1" CompanyName="Speedy Express"   
      Phone="(503) 555-9831"/>   
    <z:row ShipperID="2" CompanyName="United Package"   
      Phone="(503) 555-3199"/>   
    <z:row ShipperID="3" CompanyName="Federal Shipping"   
      Phone="(503) 555-9931"/>   
  </rs:data>   
</xml>  
```  
  
 Le schéma montre les déclarations d’espaces de noms, de la section de schéma et de la section de données. La section de schéma contient des définitions pour la ligne, ShipperID, CompanyName et téléphone.  
  
 Définitions de schéma est conforme à la [spécification W3C XML-Data](http://www.w3.org/TR/1998/NOTE-XML-data/) et peut être entièrement validée (mais pas la validation aura lieu dans Internet Explorer 5). XML-Data est actuellement le seul format de schéma pour la persistance Recordset.  
  
 La section de données possède trois lignes contenant des informations à leur sujet. Pour un ensemble de lignes vide, la section de données peut être vide, mais la \<rs : data > balises doivent être présents. Sans données, vous pouvez écrire la balise simplement \<rs : data / >. Les balises précédées de « rs » indique qu’il est dans l’espace de noms défini par urn : schemas-microsoft-rowset.  
  
## <a name="see-also"></a>Voir aussi  
 [Maintien d’enregistrements au Format XML](../../../ado/guide/data/persisting-records-in-xml-format.md)