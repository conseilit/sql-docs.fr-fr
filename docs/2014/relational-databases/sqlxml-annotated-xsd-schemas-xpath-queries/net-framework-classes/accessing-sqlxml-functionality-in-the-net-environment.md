---
title: Accès aux fonctionnalités SQLXML dans l’environnement .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], accessing SQLXML functionality
- SQLXML Managed Classes, accessing SQLXML functionality
- DiffGrams [SQLXML], accessing SQLXML functionality
- .NET Framework [SQLXML], accessing SQLXML functionality
ms.assetid: 74744535-2945-414d-9a5b-7e8cc363953a
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: cab28e4252c1d2a07b3e19c7017f8cb3a4f0396e
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48190829"
---
# <a name="accessing-sqlxml-functionality-in-the-net-environment"></a>Accès aux fonctionnalités SQLXML dans l'environnement .NET
  Cet exemple montre :  
  
-   Comment utiliser [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Classes managées SQLXML (Microsoft.Data.SqlXml) pour accéder à Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] environnement .NET Framework.  
  
-   Comment les DiffGrams générés dans l'environnement .NET Framework peuvent appliquer les mises à jour des données aux tables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 Dans cette application, une requête XPath est exécutée sur un schéma XSD. L’exécution de la requête XPath retourne un document XML qui se compose de données de contact (**FirstName**, **LastName**). L'application charge le document XML dans le dataset de l'environnement .NET Framework. Les données du dataset sont modifiées : le prénom du contact est changé en « Susan » pour le premier contact du dataset. Le DiffGram est généré à partir du dataset, puis la mise à jour spécifiée dans le DiffGram (modification du prénom de l'employé) est appliquée à la table Person.Contact.  
  
> [!NOTE]  
>  Dans le code, vous devez fournir le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      DataRow row;  
      SqlXmlAdapter ad;  
      //need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandText = "Con";  
      cmd.CommandType = SqlXmlCommandType.XPath;  
      cmd.SchemaPath = "MySchema.xml";  
      //load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      row = ds.Tables["Con"].Rows[0];  
      row["FName"] = "Susan";  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
 **Pour tester l’exemple :**  
  
 Pour tester cet exemple, le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework doit être installé sur votre ordinateur.  
  
1.  Enregistrez ce schéma XSD (MySchema.xml) dans un dossier :  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Con" sql:relation="Person.Contact" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="FName"    
                         sql:field="FirstName"   
                         type="xsd:string" />   
            <xsd:element name="LName"    
                         sql:field="LastName"    
                         type="xsd:string" />  
         </xsd:sequence>  
         <xsd:attribute name="ContactID" type="xsd:integer" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
2.  Enregistrez le code C# (DocSample.cs) fourni dans cet exemple dans le même dossier que celui du schéma. (Si vous stockez les fichiers dans un dossier différent, vous devrez modifier le code et spécifier le chemin d'accès approprié au répertoire pour le schéma de mappage.)  
  
3.  Compilez le code. Pour compiler le code à l'invite de commandes, utilisez :  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     Un fichier exécutable (DocSample.exe) est alors créé.  
  
 À l'invite de commandes, exécutez DocSample.exe.  
  
  
