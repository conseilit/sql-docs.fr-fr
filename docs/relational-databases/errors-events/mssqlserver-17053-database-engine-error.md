---
title: MSSQLSERVER_17053 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 17053 (Database Engine error)
ms.assetid: e0a01f3d-d0aa-4c38-8bcc-82e59de50512
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 07c215c0ae360a5b386909cd64e9f3dfb2893bcf
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47809567"
---
# <a name="mssqlserver17053"></a>MSSQLSERVER_17053
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|17053|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|OS_ERROR|  
|Texte du message|%ls : erreur du système d'exploitation %ls.|  
  
## <a name="explanation"></a>Explication  
Une erreur générique du système d'exploitation s'est produite.  L'état résultant est indéfini.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Habituellement cette erreur apparaît conjointement avec une autre erreur et doit servir à diagnostiquer cet échec. Les exemples peuvent inclure des échecs de lecture ou d'écriture des données ou des fichiers journaux, des opérations en lecture/écriture du Registre, ou d'autres échecs Win32API inattendus.  
  
