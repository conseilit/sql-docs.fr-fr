---
title: Instructions et Limitations de DiffGrams dans SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: cf8689c4-2a63-4d05-b202-21b5ff187d7f
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2adbd116b818086e13adacd5e88d3923b53f81ee
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48074971"
---
# <a name="guidelines-and-limitations-of-diffgrams-in-sqlxml"></a>Instructions et limitations de DiffGrams dans SQLXML
  Souvenez-vous des éléments suivants lors de l'utilisation de DiffGrams avec SQLXML 4.0 :  
  
-   Les types de données BLOB tels que `text/ntext` et les images ne doivent pas être utilisés dans le bloc `<diffgr:before>` lors de l'utilisation de DiffGrams, car cela les inclura dans le contrôle d'accès concurrentiel. Cela peut entraîner des problèmes avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en raison des limitations sur la comparaison pour les types BLOB. Par exemple, le mot clé LIKE est utilisé dans la clause WHERE pour effectuer une comparaison entre les colonnes du type de données `text` ; toutefois, les comparaisons échouent dans le cas de types BLOB lorsque la taille des données dépasse 8 Ko.  
  
-   Les caractères spéciaux dans les données `ntext` peuvent entraîner des problèmes avec SQLXML 4.0 en raison des limitations sur la comparaison pour les types BLOB. Par exemple, l'utilisation de "[Serializable]" dans le bloc `<diffgr:before>` d'un DiffGram, s'il est utilisé dans le contrôle d'accès concurrentiel d'une colonne de type `ntext`, échouera avec la description d'erreur SQLOLEDB suivante :  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
  
