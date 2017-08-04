---
title: "Se connecter à Oracle (OracleToSQL) | Documents Microsoft"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23a48cb6-ff30-49bb-b4a7-603ebcab336f
caps.latest.revision: 5
author: sabotta
ms.author: carlasab
manager: v-thobro
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: d685be15fb8d0c6fea21d539e3370b3377316324
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="connect-to-oracle-oracletosql"></a>Se connecter à Oracle (OracleToSQL)
Utilisez le **se connecter à Oracle** boîte de dialogue se connecter à la base de données Oracle que vous souhaitez migrer.  
  
Pour accéder à cette boîte de dialogue, dans le **fichier** menu, sélectionnez **se connecter à Oracle**. Si vous êtes déjà connecté, la commande est **se reconnecter à Oracle**.  
  
## <a name="options"></a>Options  
**Fournisseur**  
Sélectionnez le fournisseur d’accès aux données pour la connexion à la base de données Oracle. Les fournisseurs disponibles sont le fournisseur du Client Oracle et le fournisseur OLE DB. La valeur par défaut est le fournisseur du Client Oracle.  
  
**Mode**  
Sélectionnez le mode Standard, TNSNAME ou chaîne de connexion.  
  
-   En mode Standard, vous entrez ou sélectionnez des valeurs pour le fournisseur, nom du serveur, port du serveur, Oracle SID, nom d’utilisateur et mot de passe.  
  
-   En mode TNSNAME, vous entrez l’identificateur de connexion (alias TNS) de la base de données Oracle, le nom d’utilisateur et le mot de passe.  
  
-   En mode de la chaîne de connexion, vous fournissez une chaîne de connexion.  
  
    > [!IMPORTANT]  
    > Nous vous déconseillons d’utiliser le mode de chaîne de connexion, car le texte peut inclure des mots de passe, et il est envoyé en texte clair.  
  
La valeur par défaut est en mode Standard.  
  
**Nom du serveur**  
Entrez le nom du serveur Oracle. Le nom du serveur par défaut est le même que le nom de l’ordinateur. Il s’agit d’une option de mode Standard.  
  
**Port du serveur**  
Si vous utilisez un numéro de port autre que 1521 (par défaut) pour les connexions à Oracle, entrez le numéro de port. Il s’agit d’une option de mode Standard.  
  
**Identificateur de connexion**  
Entrez le Oracle identificateur de connexion. Il s’agit de l’alias de la base de données tel que défini dans le fichier tnsnames.ora local.  
  
Il s’agit d’une option de mode TNSNAME.  
  
**Oracle SID**  
Entrez le SID de la base de données. Le SID est un identificateur qui le distingue de la base de données Oracle sur un ordinateur. La valeur par défaut de SID pour une base de données est les huit premiers caractères du nom de base de données.  
  
Il s’agit d’une option de mode Standard.  
  
**Nom d'utilisateur**  
Entrez le nom d’utilisateur SSMA utilisera pour se connecter à la base de données Oracle.  
  
**Mot de passe**  
Entrez le mot de passe correspondant au nom d'utilisateur indiqué.  
  
**Chaîne de connexion**  
> [!IMPORTANT]  
> Nous vous déconseillons d’utiliser le mode de chaîne de connexion, car le texte peut inclure des mots de passe, et il est envoyé en texte clair.  
  
Si vous utilisez le mode de la chaîne de connexion, entrez la chaîne de connexion complète pour la connexion à Oracle.  
  
Chaînes de connexion sont constitués de paires nom / valeur de paramètre.  
  
-   Pour plus d’informations de chaîne de connexion OLE DB, consultez [fournisseur Microsoft OLE DB pour Oracle](http://go.microsoft.com/fwlink/?LinkId=85640) l’article sur le site MSDN Library.  
  
Pour les chaînes de connexion de SSMA, toujours inclure le paramètre de fournisseur. En outre, assurez-vous que vous incluez le paramètre de Port lorsque vous vous connectez à Oracle.  
  
