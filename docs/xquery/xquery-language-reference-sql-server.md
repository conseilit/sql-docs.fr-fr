---
title: Référence du langage XQuery (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: language-reference
helpviewer_keywords:
- XQuery
- XQuery, about XQuery
- xml data type [SQL Server], XQuery
- XML [SQL Server], XQuery
- queries [XML in SQL Server], XQuery
ms.assetid: 8a69344f-2990-4357-8160-cb26aac95b91
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 0b0b66722189a42b4bd5f157900815a96a716f49
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47840684"
---
# <a name="xquery-language-reference-sql-server"></a>Références relatives au langage Xquery (SQL Server)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[tsql](../includes/tsql-md.md)] prend en charge un sous-ensemble du langage XQuery qui est utilisé pour interroger le **xml** type de données. Cette implémentation de XQuery est alignée sur la spécification préliminaire de XQuery de juillet 2004. Le langage est en cours de développement par le W3C (World Wide Web Consortium), avec la participation des principaux éditeurs de base de données ainsi que de Microsoft. Étant donné que les spécifications du W3C pourront faire l'objet de révisions avant de devenir une recommandation du W3C, cette implémentation peut être différente de la recommandation finale. Cette rubrique met en valeur la sémantique et la syntaxe du sous-ensemble de XQuery pris en charge dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
 Pour plus d’informations, consultez le [W3C XQuery 1.0 Language Specification](http://go.microsoft.com/fwlink/?LinkId=48846).  
  
 XQuery est un langage qui permet d'interroger des données XML structurées ou semi-structurées. Avec le **xml** type de données prise en charge fournie dans le [!INCLUDE[ssDE](../includes/ssde-md.md)], documents peuvent être stockés dans une base de données et ensuite interrogées à l’aide de XQuery.  
  
 Basé sur le langage de requête XPath existant, XQuery se caractérise par une prise en charge améliorée de l'itération et du tri des résultats ainsi que par la possibilité de construire le document XML nécessaire. XQuery fonctionne sur le modèle de données XQuery. Il s'agit d'une abstraction de documents XML et des résultats XQuery pouvant être typés ou non typés. Les informations de type reposent sur les types fournis par le langage de schéma XML W3C. Si aucune information de type n'est disponible, XQuery gère les données comme étant non typées. Ce procédé est similaire à celui qu'utilise XPath version 1.0 pour gérer les données XML.  
  
 Pour interroger une instance XML stockée dans une variable ou une colonne de **xml** type, que vous utilisez le [les méthodes de Type de données xml](../t-sql/xml/xml-data-type-methods.md). Par exemple, vous pouvez déclarer une variable de **xml** type et l’interroger à l’aide de la **query()** méthode de la **xml** type de données.  
  
```  
DECLARE @x xml  
SET @x = '<ROOT><a>111</a></ROOT>'  
SELECT @x.query('/ROOT/a')  
```  
  
 Dans l’exemple suivant, la requête est spécifiée sur la colonne Instructions de **xml** type dans la table ProductModel dans la base de données AdventureWorks.  
  
```  
SELECT Instructions.query('declare namespace AWMI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";           
    /AWMI:root/AWMI:Location[@LocationID=10]  
') as Result   
FROM  Production.ProductModel  
WHERE ProductModelID=7  
```  
  
 La requête XQuery comprend la déclaration d’espace de noms, `declare namespace``AWMI=...`et l’expression de requête, `/AWMI:root/AWMI:Location[@LocationID=10]`.  
  
 Notez que la requête XQuery est spécifiée sur la colonne Instructions de **xml** type. Le [méthode query()](../t-sql/xml/query-method-xml-data-type.md) des données xml type est utilisé pour spécifier la requête XQuery.  
  
 Le tableau suivant répertorie les rubriques connexes qui permettent d'assimiler l'implémentation de XQuery dans le [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
|Rubrique|Description|  
|-----------|-----------------|  
|[Données XML &#40;SQL Server&#41;](../relational-databases/xml/xml-data-sql-server.md)|Explique la prise en charge pour le **xml**type de données dans le [!INCLUDE[ssDE](../includes/ssde-md.md)] et les méthodes que vous pouvez utiliser sur ce type de données. Le **xml** formulaires de données XQuery d’entrée de modèle sur lequel les expressions XQuery sont exécutées de type de données.|  
|[Collections de schémas XML &#40;SQL Server&#41;](../relational-databases/xml/xml-schema-collections-sql-server.md)|Explique comment les instances XML stockées dans une base de données peuvent être typées. Cela signifie que vous pouvez associer une collection de schémas XML avec le **xml** colonne de type. Toutes les instances stockées dans la colonne sont validées et typées par rapport au schéma contenu dans la collection et fournissent les informations de type pour XQuery.|  
|||  
  
> [!NOTE]  
>  L'organisation de cette section est basée sur la spécification préliminaire de XQuery du W3C (World Wide Web Consortium). Certains des diagrammes fournis dans cette section proviennent de cette spécification. Cette section compare l'implémentation de Microsoft XQuery à la spécification du W3C, explique en quoi Microsoft XQuery diffère de cette spécification et indique les fonctionnalités W3C non prises en charge. La spécification W3C est disponible à l’adresse [ http://www.w3.org/TR/2004/WD-xquery-20040723 ](http://go.microsoft.com/fwlink/?LinkId=48846).  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Rubrique|Description|  
|-----------|-----------------|  
|[Concepts de base de XQuery](../xquery/xquery-basics.md)|Fournit une vue d'ensemble des concepts XQuery ainsi que de l'évaluation des expressions (contextes statique et dynamique), de l'atomisation, de la valeur booléenne effective, du système de type XQuery, de la correspondance des types de séquence et de la gestion des erreurs.|  
|[Expressions XQuery](../xquery/xquery-expressions.md)|Décrit les principales expressions XQuery, les expressions de chemin d'accès, les expressions de séquence, les expressions logiques et de comparaison arithmétiques, la construction XQuery, l'expression FLWOR, les expressions conditionnelles et quantifiées et les différentes expressions applicables aux types de séquence.|  
|[Modules et prologues &#40;XQuery&#41;](../xquery/modules-and-prologs-xquery.md)|Décrit le prologue XQuery.|  
|[Fonctions XQuery impliquant le type de données xml](../xquery/xquery-functions-against-the-xml-data-type.md)|Décrit la liste des fonctions XQuery prises en charge.|  
|[Opérateurs XQuery sur le type de données xml](../xquery/xquery-operators-against-the-xml-data-type.md)|Décrit les opérateurs XQuery pris en charge.|  
|[Exemples supplémentaires de requêtes XQuery sur le type de données xml](../xquery/additional-sample-xqueries-against-the-xml-data-type.md)|Fournit des exemples XQuery supplémentaires.|  
  
## <a name="see-also"></a>Voir aussi  
 [Données XML &#40;SQL Server&#41;](../relational-databases/xml/xml-data-sql-server.md)   
 [Collections de schémas XML &#40;SQL Server&#41;](../relational-databases/xml/xml-schema-collections-sql-server.md)   
 [Exemples d’importation et d’exportation en bloc de documents XML &#40;SQL Server&#41;](../relational-databases/import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
  
  
