---
title: Sécuriser le serveur de distribution | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], Distributors
- Distributors [SQL Server replication], security
ms.assetid: 76d78229-0ff2-4aa4-9b4e-ad97534c5296
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 2ff08dda7870c9f8596370c38c207350f51e6f0a
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48188749"
---
# <a name="secure-the-distributor"></a>Sécuriser le serveur de distribution
  Les Agents de réplication suivants se connectent au serveur de distribution : l'Agent de lecture du journal, l'Agent d'instantané, l'Agent de lecture de la file d'attente, l'Agent de distribution et l'Agent de fusion. Il est important de donner un nom d'accès approprié à chacun de ces agents tout en suivant le principe d'accorder le minimum de droits nécessaires et de protéger également le stockage de tous les mots de passe.  
  
-   Pour plus d’informations sur la gestion des connexions et des mots de passe, consultez [Gérer les connexions et les mots de passe dans la réplication](manage-logins-and-passwords-in-replication.md).  
  
-   Pour des informations détaillées sur les autorisations requises pour chaque Agent, consultez [Replication Agent Security Model](replication-agent-security-model.md).  
  
 En plus de gérer les noms d'accès et les mots de passe de manière appropriée, il est important de comprendre le rôle de la liaison du serveur distant **repl_distributor** et du compte **distributor_admin** .  
  
## <a name="securing-the-connection-from-the-publisher-to-the-distributor"></a>Protection de la connexion du serveur de publication au serveur de distribution  
 Afin de prendre en charge les communications nécessaires lorsque des procédures stockées administratives s'exécutent sur le serveur de publication et mettent à jour des informations sur le serveur de distribution, la réplication configure automatiquement le serveur distant **repl_distributor**. L'entrée du serveur distant **repl_distributor** sert à communiquer avec la base de données de distribution, que la base de données de distribution soit contenue dans l'instance du serveur de publication (un serveur de distribution local), ou réside dans une instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distante (un serveur de distribution distant).  
  
 Lorsqu'une base de données de distribution est contenue dans une instance locale, un mot de passe aléatoire est généré et configuré automatiquement. Lorsque la base de données de distribution sur trouve sur une instance distante, l'administrateur configure un mot de passe pendant l'installation du serveur de publication et du serveur de distribution ; ce mot de passe est ensuite utilisé pour fournir l'authentification du trafic passant par le lien **repl_distributor** .  
  
 Le serveur de distribution utilise l'entrée du serveur distant **repl_distributor** pour vérifier que le serveur appelant est configuré comme serveur de publication sur le serveur de distribution, valide le mot de passe fourni par le serveur de publication, et valide la procédure stockée comme étant une procédure stockée de réplication pendant l'exécution.  
  
 Le mot de passe configuré pour l'entrée du serveur distant **repl_distributor** pendant l'installation est associé à un nom d'accès [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , **distributor_admin**, qui est ajouté au rôle serveur fixe **sysadmin** sur le serveur de distribution. La connexion **distributor_admin** est utilisée par les procédures stockées de réplication lors de la connexion au serveur de distribution.  
  
> [!NOTE]  
>  Ne modifiez pas manuellement le mot de passe pour **distributor_admin** . Utilisez toujours la procédure stockée **sp_changedistributor_password** , ou les boîtes de dialogue **Propriétés du serveur de distribution** ou **Mettre à jour les mots de passe de réplication** dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], car les changements de mots de passe sont ensuite appliqués automatiquement aux publications locales.  
  
## <a name="snapshot-folder-security"></a>Sécurité du répertoire d'instantanés  
 Assurez-vous que le partage de fichiers d'instantanés dispose d'une autorisation de lecture sur le compte sous lequel s'exécute l'Agent de fusion (pour la réplication de fusion) ou l'Agent de distribution (pour la réplication d'instantané ou transactionnelle), et d'une autorisation d'écriture sur le compte sous lequel s'exécute l'Agent d'instantané. Pour plus d’informations sur le dossier d’instantanés, consultez [Sécuriser le dossier d’instantanés](secure-the-snapshot-folder.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Afficher et modifier les paramètres de sécurité de la réplication](view-and-modify-replication-security-settings.md)   
 [Activer les connexions chiffrées dans le moteur de base de données &#40;Gestionnaire de configuration SQL Server&#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md)   
 [Replication Security Best Practices](replication-security-best-practices.md)   
 [Sécurité et protection &#40;réplication&#41;](security-and-protection-replication.md)  
  
  
