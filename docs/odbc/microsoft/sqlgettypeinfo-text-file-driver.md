---
title: SQLGetTypeInfo (pilote de fichier texte) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLGetTypeInfo function [ODBC], Text File Driver
- text file driver [ODBC], SQLGetTypeInfo
ms.assetid: 05a58975-093c-4bd9-bd72-b5f0026a6e36
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3c1c38b66e9b8a3c1cbed4a3712f7af866935089
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47847727"
---
# <a name="sqlgettypeinfo-text-file-driver"></a>SQLGetTypeInfo (pilote de fichier texte)
> [!NOTE]  
>  Cette rubrique fournit des informations spécifiques au pilote fichier texte. Pour obtenir des informations générales sur cette fonction, consultez la rubrique appropriée sous [ODBC API Reference](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Le nom du type (TYPE_NAME) retourné dans la table produite par **SQLGetTypeInfo** sera le nom plus couramment utilisé par la source de données.  
  
 SQL_ALL_EXCEPT_LIKE s’affichera dans la colonne de recherche pour l’octet, compteur, Double, types de données unique, longue et courte. (La fonctionnalité LIKE est possible en convertissant la valeur en un caractère en utilisant les fonctions de conversion canonique ODBC, puis effectuer la comparaison.)  
  
 Lorsque le pilote de texte est utilisé, **SQLGetTypeInfo** retourne CASE_SENSITIVE la valeur FALSE pour le texte des types de données (CHAR et LONGCHAR), lorsque les types de données réellement respectent la casse.
