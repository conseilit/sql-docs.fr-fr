---
title: MSSQLSERVER_3417 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 3417 (Database Engine error)
ms.assetid: 005829c8-cf57-4828-818a-bbe8ee2e00f0
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: da66b69ab130bc45e7d52c7ef87f59d00194ee6d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47795146"
---
# <a name="mssqlserver3417"></a>MSSQLSERVER_3417
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|3417|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|REC_BADMASTER|  
|Texte du message|Impossible de récupérer la base de données master. Impossible d'exécuter SQL Server. Restaurez la base master à partir d'une sauvegarde complète, réparez-la ou reconstruisez-la. Pour plus d'informations sur la façon de reconstruire la base de données master, consultez la documentation en ligne de SQL Server.|  
  
## <a name="explanation"></a>Explication  
SQL Server ne peut pas démarrer la base de données **MASTER**. Si les bases de données **MASTER** ou **tempdb** ne peuvent pas être mises en ligne, SQL Server ne peut pas s’exécuter. Cette erreur est généralement précédée d'autres erreurs. Étudiez les journaux d'erreurs pour trouver la racine du problème.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Restaurez la sauvegarde de la base de données ou réparez la base de données.  
  
