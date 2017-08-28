---
title: Utilisation de Variables par programme | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- System namespace
- scope [Integration Services]
- variables [Integration Services], programmatically
- configuration files [Integration Services]
- Variables collection
- User namespace
- custom variables [Integration Services]
- variables [Integration Services], customizing
ms.assetid: c4b76a3d-94ca-4a8e-bb45-cb8bd0ea3ec1
caps.latest.revision: 53
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 4a8ade977c971766c8f716ae5f33cac606c8e22d
ms.openlocfilehash: 5c8968302f42e1b8fde55894810ecb77cf715ab6
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="working-with-variables-programmatically"></a>Utilisation de variables par programmation
  Les variables constituent un moyen de définir des valeurs et de contrôler des processus dans les packages, conteneurs, tâches et gestionnaires d'événements de manière dynamique. Les variables peuvent également être utilisées par les contraintes de précédence pour contrôler la direction du flux de données vers différentes tâches. Les variables ont diverses utilisations :  
  
-   Mise à jour des propriétés d'un package au moment de l'exécution.  
  
-   Remplir les valeurs de paramètre pour les instructions Transact-SQL en cours d’exécution.  
  
-   Contrôle du flux d'une boucle Foreach. Pour plus d’informations, consultez [ajouter une énumération à un flux de contrôle](http://msdn.microsoft.com/library/f212b5fb-3cc4-422e-9b7c-89eb769a812a).  
  
-   Contrôle d'une contrainte de précédence par son utilisation dans une expression. Une contrainte de précédence peut inclure des variables dans la définition de contrainte. Pour plus d’informations, consultez [Ajouter des expressions aux contraintes de précédence](http://msdn.microsoft.com/library/5574d89a-a68e-4b84-80ea-da93305e5ca1).  
  
-   Contrôle de la répétition conditionnelle d'un conteneur de boucles For. Pour plus d’informations, consultez [ajouter une itération à un flux de contrôle](http://msdn.microsoft.com/library/eb3a7494-88ae-4165-9d0f-58715eb1734a).  
  
-   Créer des expressions qui incluent les valeurs des variables.  
  
-   Vous pouvez créer des variables personnalisées pour tous les types de conteneurs : packages, **boucle Foreach** conteneurs, **de boucles for** conteneurs, **séquence** conteneurs, TaskHosts et gestionnaires d’événements. Pour plus d’informations, consultez [Variables Integration Services &#40;SSIS&#41;](../../integration-services/integration-services-ssis-variables.md) et [Utiliser des variables dans des packages](http://msdn.microsoft.com/library/7742e92d-46c5-4cc4-b9a3-45b688ddb787).  
  
## <a name="scope"></a>Portée  
 Chaque conteneur possède sa propre collection <xref:Microsoft.SqlServer.Dts.Runtime.Variables>. Lorsqu'une nouvelle variable est créée, elle se trouve dans la portée de son conteneur parent. Le conteneur de packages se trouvant au sommet de la hiérarchie de conteneurs, les variables avec une portée de package fonctionnent comme les variables globales et sont visibles pour tous les conteneurs contenus dans le package. La collection de variables du conteneur est également accessible par les enfants du conteneur via la collection <xref:Microsoft.SqlServer.Dts.Runtime.Variables>, en utilisant le nom de variable ou l'index de la variable dans la collection.  
  
 Parce que la visibilité d'une variable s'étend du haut vers le bas, les variables déclarées au niveau du package sont visibles pour tous les conteneurs situés dans le package. Par conséquent, la collection <xref:Microsoft.SqlServer.Dts.Runtime.Variables> sur un conteneur inclut toutes les variables qui appartiennent à son parent en plus de ses propres variables.  
  
 Inversement, les variables contenues dans une tâche sont limitées en termes de portée et de visibilité et sont uniquement visibles pour la tâche.  
  
 Si un package exécute d'autres packages, les variables définies dans la portée du package appelant sont disponibles pour le package appelé. La seule exception se produit lorsqu'une variable de même nom existe dans le package appelé. Lorsque cette collision se produit, la valeur de la variable dans le package appelé remplace celle du package appelant. Les variables définies dans la portée du package appelé ne sont jamais de nouveau disponibles pour le package appelant.  
  
 L'exemple de code suivant crée une variable, `myCustomVar`, par programme, à la portée du package, puis parcourt toutes les variables visibles pour le package, en imprimant leur nom, leur type de données et leur valeur.  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Application app = new Application();  
      // Load a sample package that contains a variable that sets the file name.  
      Package pkg = app.LoadPackage(  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx",  
        null);  
      Variables pkgVars = pkg.Variables;  
      Variable myVar = pkg.Variables.Add("myCustomVar", false, "User", "3");  
      foreach (Variable pkgVar in pkgVars)  
      {  
        Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name,  
          pkgVar.DataType, pkgVar.Value.ToString());  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim app As Application = New Application()  
    ' Load a sample package that contains a variable that sets the file name.  
    Dim pkg As Package = app.LoadPackage( _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx", _  
      Nothing)  
    Dim pkgVars As Variables = pkg.Variables  
    Dim myVar As Variable = pkg.Variables.Add("myCustomVar", False, "User", "3")  
    Dim pkgVar As Variable  
    For Each pkgVar In pkgVars  
      Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name, _  
        pkgVar.DataType, pkgVar.Value.ToString())  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 **Exemple de sortie :**  
  
 `Variable: CancelEvent, Int32, 0`  
  
 `Variable: CreationDate, DateTime, 4/18/2003 11:57:00 AM`  
  
 `Variable: CreatorComputerName, String,`  
  
 `Variable: CreatorName, String,`  
  
 `Variable: ExecutionInstanceGUID, String, {237AB5A4-7E59-4FC9-8D61-E8F20363DF25}`  
  
 `Variable: FileName, String, Junk`  
  
 `Variable: InteractiveMode, Boolean, False`  
  
 `Variable: LocaleID, Int32, 1033`  
  
 `Variable: MachineName, String, MYCOMPUTERNAME`  
  
 `Variable: myCustomVar, String, 3`  
  
 `Variable: OfflineMode, Boolean, False`  
  
 `Variable: PackageID, String, {F0D2E396-A6A5-42AE-9467-04CE946A810C}`  
  
 `Variable: PackageName, String, DTSPackage1`  
  
 `Variable: StartTime, DateTime, 1/28/2005 7:55:39 AM`  
  
 `Variable: UserName, String, <domain>\<userid>`  
  
 `Variable: VersionBuild, Int32, 198`  
  
 `Variable: VersionComments, String,`  
  
 `Variable: VersionGUID, String, {90E105B4-B4AF-4263-9CBD-C2050C2D6148}`  
  
 `Variable: VersionMajor, Int32, 1`  
  
 `Variable: VersionMinor, Int32, 0`  
  
 Notez que toutes les variables de portée dans le **système** espace de noms sont disponibles pour le package. Pour plus d’informations, consultez [Variables système](../../integration-services/system-variables.md).  
  
## <a name="namespaces"></a>Espaces de noms  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) fournit deux espaces de noms par défaut où les variables résident : **Utilisateur** et **système** espaces de noms. Par défaut, toute variable personnalisée créée par le développeur est ajouté à la **utilisateur** espace de noms. Variables système résident dans le **système** espace de noms. Vous pouvez créer des espaces de noms supplémentaires autres que les **utilisateur** espace de noms pour contenir des variables personnalisées et que vous pouvez modifier le nom de la **utilisateur** espace de noms, mais vous ne pouvez pas ajouter ou modifier les variables dans le **système** espace de noms, ou affecter des variables système à un autre espace de noms.  
  
 Les variables système qui sont disponibles diffèrent selon le type de conteneur. Pour obtenir la liste des variables système disponibles pour les packages, conteneurs, tâches et gestionnaires d’événements, consultez [Variables système](../../integration-services/system-variables.md).  
  
## <a name="value"></a>Valeur  
 La valeur d'une variable personnalisée peut être un littéral ou une expression :  
  
-   Si vous souhaitez que la variable contienne une valeur littérale, définissez la valeur de sa propriété <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A>.  
  
-   Si vous souhaitez que la variable contienne une expression, afin que vous pouvez utiliser les résultats de l’expression en tant que sa valeur, définissez la <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> propriété de la variable à **true**et fournissez une expression dans le <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A> propriété. Au moment de l'exécution, l'expression est évaluée et son résultat est utilisé en tant que valeur de la variable. Par exemple, si la propriété de l'expression d'une variable est `"100 * 2""100 * 2"` , la variable est évaluée à une valeur de 200.  
  
 Pour une variable, vous ne pouvez pas définir explicitement la valeur de sa propriété <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>. La valeur <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> est déduite de la valeur initiale assignée à la variable et ne peut pas être changée par la suite. Pour plus d’informations sur les types de données de variable, consultez [Integration Services Data Types](../../integration-services/data-flow/integration-services-data-types.md).  
  
 L’exemple de code suivant crée une variable, définit <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> à **true**, affecte l’expression `"100 * 2"` à la propriété expression de la variable, puis renvoie la valeur de la variable.  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package pkg = new Package();  
      Variable v100 = pkg.Variables.Add("myVar", false, "", 1);  
      v100.EvaluateAsExpression = true;  
      v100.Expression = "100 * 2";  
      Console.WriteLine("Expression for myVar: {0}",   
        v100.Properties["Expression"].GetValue(v100));  
      Console.WriteLine("Value of myVar: {0}", v100.Value.ToString());  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkg As Package = New Package  
    Dim v100 As Variable = pkg.Variables.Add("myVar", False, "", 1)  
    v100.EvaluateAsExpression = True  
    v100.Expression = "100 * 2"  
    Console.WriteLine("Expression for myVar: {0}", _  
      v100.Properties("Expression").GetValue(v100))  
    Console.WriteLine("Value of myVar: {0}", v100.Value.ToString)  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 **Exemple de sortie :**  
  
 `Expression for myVar: 100 * 2`  
  
 `Value of myVar: 200`  
  
 L'expression doit être une expression valide qui utilise la syntaxe d'expression [!INCLUDE[ssIS](../../includes/ssis-md.md)]. Les littéraux sont autorisés dans les expressions variables, en plus des opérateurs et fonctions que la syntaxe d'expression fournit, mais les expressions ne peuvent pas référencer d'autres variables ou colonnes. Pour plus d’informations, consultez [Expressions Integration Services &#40;SSIS&#41;](../../integration-services/expressions/integration-services-ssis-expressions.md).  
  
## <a name="configuration-files"></a>Fichiers de configuration  
 Si un fichier de configuration inclut une variable personnalisée, la variable peut être mise à jour au moment de l'exécution. Cela signifie que lorsque le package s'exécute, la valeur de la variable qui se trouvait à l'origine dans le package est remplacée par une nouvelle valeur provenant du fichier de configuration. Cette technique de remplacement s'avère utile lorsqu'un package est déployé sur plusieurs serveurs qui requièrent des valeurs de variables différentes. Par exemple, une variable peut spécifier le nombre de fois où un **boucle Foreach** conteneur répète son flux de travail, ou liste les destinataires choisis par un gestionnaire d’événements envoie des messages électroniques lorsqu’une erreur est générée ou modifier le nombre d’erreurs qui peuvent se produire avant que le package échoue. Ces variables sont fournies de manière dynamique dans des fichiers de configuration pour chaque environnement. Par conséquent, seules les variables accessibles en lecture/écriture sont autorisées dans les fichiers de configuration. Pour plus d’informations, consultez [Créer des configurations de package](../../integration-services/packages/create-package-configurations.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Integration Services &#40; SSIS &#41; Variables](../../integration-services/integration-services-ssis-variables.md)   
 [Utiliser des Variables dans des Packages](http://msdn.microsoft.com/library/7742e92d-46c5-4cc4-b9a3-45b688ddb787)  
  
  