---
title: "Ajouter des tables à des requêtes (Visual Database Tools) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inserting tables
- adding tables
- queries [SQL Server], tables
ms.assetid: 6551aa7e-31a1-4636-852a-819bc53d658b
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: ffa0dc48650d116f76df704ceae1d10f96b2b5be
ms.lasthandoff: 04/11/2017

---
# <a name="add-tables-to-queries-visual-database-tools"></a>Ajouter des tables à des requêtes (Visual Database Tools)
Lorsque vous créez une requête, vous extrayez des données d'une table ou d'autres objets structurés comme des tables (vues et certaines fonctions définies par l'utilisateur). Pour utiliser l'un de ces objets dans votre requête, vous pouvez les ajouter au **volet Schéma**.  
  
### <a name="to-add-a-table-or-table-valued-object-to-a-query"></a>Pour ajouter une table ou objet table à une requête  
  
1.  Dans le **volet Schéma** du Concepteur de requêtes et de vues, cliquez avec le bouton droit sur l'arrière-plan et choisissez **Ajouter une table** dans le menu contextuel qui s'affiche.  
  
2.  Dans la boîte de dialogue **Ajouter une table** , sélectionnez l'onglet qui correspond au type d'objet que vous souhaitez ajouter à la requête.  
  
3.  Dans la liste affichée, double-cliquez sur chacun des éléments que vous souhaitez ajouter.  
  
4.  Une fois que vous avez ajouté tous les éléments choisi, cliquez sur **Fermer**.  
  
    Le Concepteur de requêtes et de vue met à jour le **volet Schéma**, le **volet Critères**et le **volet SQL** d'après vos sélections.  
  
Les tables et les vues sont automatiquement ajoutées à la requête lorsque vous les référencez dans l'instruction du volet SQL.  
  
Le Concepteur de requêtes et de vues n'affiche pas les colonnes de données d'une table ou d'un objet table si vous ne disposez pas des droits d'accès correspondants ou si le fournisseur ne parvient pas à retourner des informations le concernant. Dans ce cas, seules une barre de titre et la case à cocher * (Toutes les colonnes) sont disponibles pour la table ou l'objet table.  
  
### <a name="to-add-an-existing-query-to-a-new-query"></a>Pour ajouter une requête existante à une nouvelle requête  
  
1.  Vérifiez que le **volet SQL** figure dans la nouvelle requête que vous êtes en train de créer.  
  
2.  Dans le **volet SQL**, tapez des parenthèses ouvrante et fermante () à la suite du mot FROM.  
  
3.  Ouvrez le Concepteur de requêtes et de vues pour la requête existante. Deux Concepteurs de requêtes et de vues sont désormais ouverts.  
  
4.  Affichez le **volet SQL** pour la requête interne (la requête existante que vous ajoutez à la nouvelle requête externe).  
  
5.  Sélectionnez l'ensemble du texte figurant dans le **volet SQL**et copiez-le dans le Presse-papiers.  
  
6.  Cliquez sur le **volet SQL** de la nouvelle requête, placez le curseur entre les parenthèses que vous avez ajoutées et collez-y le contenu du Presse-papiers.  
  
7.  Toujours dans le **volet SQL**, ajoutez un alias à la suite de la parenthèse fermante.  
  
## <a name="see-also"></a>Voir aussi  
[Créer des alias de tables &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/create-table-aliases-visual-database-tools.md)  
[Supprimer des tables des requêtes &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/remove-tables-from-queries-visual-database-tools.md)  
[Spécifier des critères de recherche &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/specify-search-criteria-visual-database-tools.md)  
[Résumer les résultats de la requête &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/summarize-query-results-visual-database-tools.md)  
[Effectuer des opérations de base concernant les requêtes &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/perform-basic-operations-with-queries-visual-database-tools.md)  
  
