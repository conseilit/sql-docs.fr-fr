---
title: Personnaliser le comportement des analyseurs lexicaux avec un dictionnaire personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: search, sql-database
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: a8e278d1-aeaa-48f1-a0c6-5de232c983e4
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 7cedd510018ce487d5f6eb61468b1b66ce45ddf9
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47646287"
---
# <a name="customize-the-behavior-of-word-breakers-with-a-custom-dictionary"></a>Personnaliser le comportement des analyseurs lexicaux avec un dictionnaire personnalisé
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  Vous pouvez personnaliser le comportement de l'analyseur lexical pour une langue particulière en créant un fichier de dictionnaire personnalisé propre à une langue. Par exemple, vous pouvez empêcher l'analyseur lexical de séparer certains termes ou modèles.  
  
 Pour plus d'informations, consultez l'article SharePoint suivant :  
  
 [Créer un dictionnaire personnalisé (SharePoint Server 2010)](http://go.microsoft.com/fwlink/?LinkId=215011)  
  
 Pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], placez les fichiers de dictionnaire personnalisés dans le dossier suivant :  
  
 `C:\Program Files\Microsoft SQL Server\<instance name>\MSSQL\Binn`  
  
 Après avoir créé ou modifié les fichiers de dictionnaire personnalisés, redémarrez le lanceur de démon de texte intégral SQL à l'aide de la commande suivante :  
  
 `exec sp_fulltext_service 'restart_all_fdhosts'`  
  
  
