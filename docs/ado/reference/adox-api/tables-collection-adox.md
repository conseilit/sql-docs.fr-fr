---
title: Tables, Collection (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Catalog::Tables
- Tables
helpviewer_keywords:
- Tables collection [ADOX]
ms.assetid: 38d750e7-f3fb-426e-b4b4-55eea4f1a654
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1b9ae2422e9d0d3a776bf786f77be5c8c5025d21
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47623157"
---
# <a name="tables-collection-adox"></a>Tables, collection (ADOX)
Contient tous les [Table](../../../ado/reference/adox-api/table-object-adox.md) objets d’un catalogue.  
  
## <a name="remarks"></a>Notes  
 Le [Append](../../../ado/reference/adox-api/append-method-adox-tables.md) méthode pour un **Tables** collection est unique pour ADOX. Vous pouvez :  
  
-   Ajouter une nouvelle table à la collection avec le **Append** (méthode).  
  
 Les propriétés et les méthodes restantes sont des collections ADO standard. Vous pouvez :  
  
-   Accéder à une table dans la collection avec le [élément](../../../ado/reference/ado-api/item-property-ado.md) propriété.  
  
-   Retourner le nombre de tables contenues dans la collection avec le [nombre](../../../ado/reference/ado-api/count-property-ado.md) propriété.  
  
-   Supprimer une table de la collection avec le [supprimer](../../../ado/reference/adox-api/delete-method-adox-collections.md) (méthode).  
  
-   Mettre à jour les objets dans la collection afin de refléter le schéma actuel de la base de données avec le [Actualiser](../../../ado/reference/ado-api/refresh-method-ado.md) (méthode).  
  
 Certains fournisseurs peuvent retourner des autres objets de schéma, tel qu’une vue, dans le **Tables** collection. Par conséquent, certaines collections ADOX peuvent contenir plusieurs références au même objet. Devez vous supprimez l’objet d’une collection, la modification sera pas visible dans une autre collection qui fait référence à l’objet supprimé jusqu'à ce que le **Actualiser** méthode est appelée sur la collection. Par exemple, avec le fournisseur OLE DB pour Microsoft Jet, les vues sont retournées avec la **Tables** collection. Si vous supprimez une vue, vous devez actualiser le **Tables** collection avant de la collection reflète la modification.  
  
 Cette section contient les rubriques suivantes.  
  
-   [Propriétés, méthodes et événements de la collection Tables](../../../ado/reference/adox-api/tables-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de propriété ActiveConnection de catalogue (VB)](../../../ado/reference/adox-api/catalog-activeconnection-property-example-vb.md)   
 [Tables et colonnes ajouter des méthodes, exemple de nom de propriété (VB)](../../../ado/reference/adox-api/columns-and-tables-append-methods-name-property-example-vb.md)   
 [Méthode Close de connexion, exemple de propriété de Type de Table (VB)](../../../ado/reference/adox-api/connection-close-method-table-type-property-example-vb.md)   
 [Keys Append, méthode, Type de clé, RelatedColumn, RelatedTable et UpdateRule, exemple de propriétés (VB)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Catalog, objet (ADOX)](../../../ado/reference/adox-api/catalog-object-adox.md)   
 [Table, objet (ADOX)](../../../ado/reference/adox-api/table-object-adox.md)
