---
title: "Options (Concepteurs - Page Concepteurs de bases de données et de tables) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Designers.Table_Designer
ms.assetid: b43f4b97-17b9-4004-a824-f77b9e145741
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 79e728f7cf2c300338e202b3e9cae27226f70a50
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="options-designers---table-and-database-designers-page"></a>Options (Concepteurs - Page Concepteurs de bases de données et de tables)
Utilisez cette page pour déterminer le comportement par défaut du concepteur. Pour accéder aux paramètres, dans le menu **Outils** , cliquez sur **Options**, développez le dossier **Concepteurs** , puis cliquez sur **Concepteur de bases de données et de tables**.  
  
## <a name="uielement-list"></a>Liste des éléments de l'interface utilisateur  
**Remplacer la valeur du délai d'attente de la chaîne de connexion pour les mises à jour du Concepteur de tables**  
Permet de définir une nouvelle valeur de délai d'attente pour les actions du Concepteur de tables. Cette option peut s'avérer utile lorsque le Concepteur de tables affecte une table volumineuse et nécessite un délai supplémentaire pour terminer la modification de la table.  
  
**Délai d'expiration de la transaction après**  
Définit une valeur de délai d'expiration pour le Concepteur de bases de données et de tables.  
  
**Générer automatiquement des scripts de modification**  
Crée automatiquement un script pour implémenter les modifications définies dans le Concepteur de bases de données et de tables.  
  
**Avertir en cas de clés primaires Null**  
Affiche une boîte de dialogue d'avertissement lorsqu'un champ sélectionné pour une clé primaire peut contenir des valeurs Null.  
  
**Signaler les différences de détection**  
Si vous activez cette case à cocher, lorsque vous enregistrerez vos modifications, un message dressera la liste des conflits entre vos modifications et les modifications apportées par un autre utilisateur.  
  
**Signaler les tables affectées**  
Affiche une boîte de dialogue d'avertissement répertoriant les tables affectées par l'action et demande une confirmation de votre part.  
  
**Empêcher l'enregistrement de modifications qui nécessitent une recréation de la table**  
Empêche un utilisateur d'apporter des modifications qui requièrent la récréation de la table. Les actions suivantes peuvent nécessiter la recréation d'une table :  
  
-   Ajout d'une nouvelle colonne au milieu de la table  
  
-   Suppression d'une colonne  
  
-   Modification de la possibilité de valeur nulle d'une colonne  
  
-   Modification de l'ordre des colonnes  
  
-   Modification du type de données d'une colonne  
  
**Vue de table par défaut**  
Sélectionnez le mode d'affichage des tables dans les concepteurs :  
  
-   **Standard**  
  
    Affiche l'en-tête de la table, tous les noms des colonnes, les types de données et le paramètre Autoriser les valeurs NULL.  
  
-   **Noms de colonnes**  
  
    Affiche les noms des colonnes.  
  
-   **Clé**  
  
    Affiche l'en-tête de la table et les colonnes clés primaires.  
  
-   **Nom uniquement**  
  
    Affiche uniquement l'en-tête de la table avec son nom.  
  
-   **Custom**  
  
    Permet de choisir les colonnes à afficher.  
  
**Lancer la boîte de dialogue Ajouter une table sur Nouveau schéma**  
Ouvre automatiquement la boîte de dialogue **Ajouter une table** à l’ouverture des concepteurs.  
  
