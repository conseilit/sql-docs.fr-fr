---
title: Propriétés de la base de données (page Groupes de fichiers) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.filegroups.f1
ms.assetid: 8d06e859-73dd-4019-b6e8-99c5c5297697
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 67e1de3aaa877b666d43f39faa92f3cfe89bd4c7
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48143829"
---
# <a name="database-properties-filegroups-page"></a>Propriétés de la base de données (page Groupes de fichiers)
  Cette page vous permet d'afficher les groupes de fichiers existants ou d'ajouter un nouveau groupe de fichiers à la base de données sélectionnée. Il existe trois types de groupes de fichiers : les groupes de fichiers de *ligne* , les groupes de fichiers de données FILESTREAM et les groupes de fichiers optimisés en mémoire.  
  
 Les groupes de fichiers de ligne contiennent des données régulières et des fichiers journaux. Les groupes de fichiers de données FILESTREAM contiennent des fichiers de données FILESTREAM. Ces fichiers de données comportent des informations sur la manière dont les données des objets BLOB (Binary Large Objects) sont stockées sur le système de fichiers lorsque vous utilisez le stockage FILESTREAM. Les deux types de groupes de fichiers disposent des mêmes options.  
  
 Si FILESTREAM n'est pas activé, la section **Filestream** ne sera pas disponible. Vous pouvez activer le stockage FILESTREAM dans la boîte de dialogue [Propriétés du serveur (page Avancé)](../../database-engine/configure-windows/server-properties-advanced-page.md).  
  
 Pour plus d’informations sur la manière dont [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise les groupes de fichiers de ligne, consultez [Groupes de fichiers et fichiers de base de données](database-files-and-filegroups.md). Pour plus d’informations sur les données et groupes de fichiers FILESTREAM, consultez [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).  
  
 Les groupes de fichiers optimisés en mémoire sont nécessaires pour toute base de données devant contenir une ou plusieurs tables optimisées en mémoire.  
  
## <a name="row-and-filestream-data-filegroup-options"></a>Options des groupes de fichiers de ligne et de données FILESTREAM  
 **Nom**  
 Entrez le nom du groupe de fichiers.  
  
 **Fichiers**  
 Indique le nombre de fichiers contenus dans le groupe de fichiers.  
  
 **Lecture seule**  
 Sélectionnez cette option pour attribuer au groupe de fichiers l'état lecture seule.  
  
 **Default**  
 Sélectionnez cette option pour définir ce groupe de fichiers comme groupe de fichiers par défaut. Vous pouvez définir un groupe de fichiers de ligne par défaut et un groupe de fichiers par défaut pour les données FILESTREAM.  
  
 **Ajouter**  
 Ajoute une nouvelle ligne vide dans la grille qui répertorie les groupes de fichiers associés à la base de données.  
  
 **Supprimer**  
 Supprime la ligne sélectionnée des groupes de fichiers de la grille.  
  
## <a name="memory-optimized-data-filegroup-options"></a>Options des groupes de fichiers optimisés en mémoire  
 **Nom**  
 Entrez le nom du groupe de fichiers optimisé en mémoire.  
  
 **Fichiers FILESTREAM**  
 Affiche le nombre de fichiers (conteneurs) figurant dans le groupe de fichiers de données optimisé en mémoire. Vous pouvez ajouter des conteneurs sur la page **Fichiers** .  
  
 **Ajouter**  
 Ajoute une nouvelle ligne vide dans la grille qui répertorie les groupes de fichiers associés à la base de données.  
  
 **Supprimer**  
 Supprime la ligne sélectionnée des groupes de fichiers de la grille.  
  
## <a name="see-also"></a>Voir aussi  
 [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql)   
 [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
