---
title: Fonctionnalités clientes ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- functionality [ADOMD.NET]
- ADOMD.NET, functionality
ms.assetid: 0f5e16a1-dc2d-4c87-8551-985921bf069b
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 9f0d1eadc7db44b1629f00d0972bbbaeb9dc0276
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48210859"
---
# <a name="adomdnet-client-functionality"></a>Fonctionnalités clientes ADOMD.NET
  À l'image des autres fournisseurs de données [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, ADOMD.NET joue le rôle de lien entre une application et une source de données. Cependant, ADOMD.NET se différencie des autres fournisseurs de données .NET Framework en ce sens qu'ADOMD.NET utilise des données analytiques. Pour ce faire, ADOMD.NET prend en charge des fonctionnalités très différentes de celles des autres fournisseurs de données .NET Framework. ADOMD.NET permet non seulement de récupérer des données, mais également d'extraire des métadonnées et modifier la structure de la banque de données analytiques :  
  
 **Récupération des métadonnées**  
 Les applications peuvent s'enquérir des données susceptibles d'être récupérées à partir de la source de données en recourant à la récupération de métadonnées via les ensembles de lignes de schéma ou le modèle objet. Certaines informations, telles que les types de chaque indicateur de performance clé (KPI) disponible, les dimensions d'un cube et les paramètres nécessaires aux modèles d'exploration de données, sont toutes détectables. Métadonnées sont particulièrement importantes pour *dynamique* applications nécessitant des entrées utilisateur pour déterminer le type de profondeur et étendue des données à récupérer. Tel est le cas notamment de l'Analyseur de requêtes, de Microsoft Excel et d'autres outils d'interrogation. Les métadonnées sont moins importantes pour *statique* les applications qui effectuent des actions prédéfinies.  
  
 Pour plus d’informations : [récupération de métadonnées à partir d’une Source de données analytiques](retrieving-metadata-from-an-analytical-data-source.md).  
  
 **Récupération de données**  
 La récupération de données consiste en la récupération effective des informations stockées dans la source de données. La récupération de données est la fonction principale des applications « statiques », qui connaissent la structure de la source de données. La récupération de données représente également le résultat final des applications « dynamiques ». La valeur de l'indicateur de performance clé à une heure donnée de la journée, le nombre de vélos vendus au cours de la dernière heure dans chaque magasin, et les éléments qui conditionnent les performances annuelles des employés sont autant d'exemples de données susceptibles d'être récupérées. La récupération de données est vitale pour les applications d'interrogation.  
  
 Pour plus d’informations : [extraction de données à partir d’une Source de données analytiques](retrieving-data-from-an-analytical-data-source.md).  
  
 **Modifier la Structure des données analytiques**  
 ADOMD.NET permet également de modifier à proprement parler la structure d'une banque de données analytiques. Bien que cette opération soit généralement accomplie par le biais du modèle objet AMO (Analysis Management Objects), vous pouvez utiliser ADOMD.NET pour envoyer des commandes ASSL (Analysis Services Scripting Language) afin de créer, modifier ou supprimer des objets sur le serveur.  
  
 Pour plus d’informations : [l’exécution de commandes par rapport à une analytique Source de données](executing-commands-against-an-analytical-data-source.md), [développement avec Analysis Management Objects &#40;AMO&#41;](../multidimensional-models/analysis-management-objects/developing-with-analysis-management-objects-amo.md), [Analysis Services Scripting Langage &#40;ASSL&#41; référence](../scripting/analysis-services-scripting-language-assl-for-xmla.md)  
  
 La récupération de métadonnées, la récupération de données et la modification d'une structure de données sont des opérations qui interviennent chacune à un moment précis dans le flux de travail d'une application ADOMD.NET classique.  
  
## <a name="typical-process-flow"></a>Flux de traitement standard  
 Les applications ADOMD.NET classiques suivent généralement le même flux de travail lorsqu'elles utilisent une base de données analytique :  
  
1.  En premier lieu, une connexion est établie à la base de données à l'aide de l'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>. Lorsque vous ouvrez la connexion, l'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> expose les métadonnées sur le serveur auquel vous vous êtes connecté. Dans une application dynamique, une partie de ces informations est en principe révélée à l'utilisateur pour lui permettre d'effectuer une sélection (p.ex., le cube à interroger). La connexion créée durant cette étape peut être réutilisée plusieurs fois par l'application, ce qui a pour effet de réduire la charge.  
  
     Pour plus d’informations : [l’établissement de connexions dans ADOMD.NET](connections-in-adomd-net.md)  
  
2.  Dès lors qu'une connexion a été établie, une application dynamique interroge ensuite le serveur pour obtenir des métadonnées plus spécifiques. Dans le cas d'une application statique, le programmeur sait par avance quels sont les objets que l'application demandera, ce qui rend inutile la récupération de ces métadonnées. Les métadonnées récupérées peuvent être utilisées par l'application et l'utilisateur pour l'étape suivante.  
  
     Pour plus d’informations : [récupération de métadonnées à partir d’une Source de données analytiques](retrieving-metadata-from-an-analytical-data-source.md)  
  
3.  L'application exécute ensuite une commande sur le serveur. Cette commande peut être utilisée dans le but de récupérer des métadonnées supplémentaires, des données ou de modifier la structure de la base de données. Pour chacune de ces tâches, l'application peut utiliser une requête déjà définie ou des métadonnées nouvellement récupérées pour créer d'autres requêtes.  
  
     Pour plus d’informations : [récupération de métadonnées à partir d’une Source de données analytiques](retrieving-metadata-from-an-analytical-data-source.md), [extraction de données à partir d’une Source de données analytiques](retrieving-data-from-an-analytical-data-source.md), [l’exécution de commandes par rapport à une analytique Source de données](executing-commands-against-an-analytical-data-source.md)  
  
4.  Une fois que la commande a été envoyée au serveur, le serveur commence à retourner les métadonnées ou les données au client. Ces informations peuvent être affichées en utilisant un objet <xref:Microsoft.AnalysisServices.AdomdClient.CellSet>, un objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdDataReader> ou un objet `System.XmlReader`.  
  
 Pour illustrer ce flux de travail standard, l'exemple suivant contient une méthode qui ouvre une connexion à la base de données, exécute une commande sur un cube connu et récupère les résultats dans un ensemble de cellules. L'ensemble de cellules retourne ensuite une chaîne délimitée par des tabulations qui contient des en-têtes de colonne, des en-têtes de ligne et des données de cellule.  
  
 [!code-csharp[Adomd.NetClient#ReturnCommandUsingCellSet](../../snippets/csharp/SQL14/adomd.net/adomd.netclient/cs/adomdexample.cs#returncommandusingcellset)]  
  
## <a name="see-also"></a>Voir aussi  
 [Programmation du client ADOMD.NET](adomd-net-client-programming.md)  
  
  
