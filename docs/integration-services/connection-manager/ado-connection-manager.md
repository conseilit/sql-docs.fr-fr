---
title: Gestionnaire de connexions ADO | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connections [Integration Services], ADO
- connection managers [Integration Services], ADO
- ADO connection manager [Integration Services]
ms.assetid: 490418bc-5ef1-41b8-a9c8-de38aa96e0f6
caps.latest.revision: 54
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b42410ae3654bed35103ea9b0dcafedff32e3af7
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="ado-connection-manager"></a>Gestionnaire de connexions ADO
  Un gestionnaire de connexions ADO permet à un package de se connecter à des objets ADO (ActiveX Data Objects), comme un recordset. Ce gestionnaire de connexions est généralement utilisé dans les tâches personnalisées écrites dans une version antérieure d’un langage comme Microsoft Visual Basic 6.0 ou dans les tâches personnalisées qui font partie d’une application existante utilisant ADO pour se connecter à une source de données.  
  
 Quand vous ajoutez un gestionnaire de connexions ADO à un package, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera converti en connexion ADO au moment de l’exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la collection **Connections** du package. La propriété **ConnectionManagerType** du gestionnaire de connexions a pour valeur **ADO**.  
  
## <a name="troubleshooting-the-ado-connection-manager"></a>Résolution des problèmes liés au gestionnaire de connexions ADO  
 Lors de la lecture par un gestionnaire de connexions ADO, certains types de données de date [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] génèrent les résultats présentés dans le tableau suivant.  
  
|Type de données SQL Server|Résultat|  
|--------------------------|------------|  
|**time**, **datetimeoffset**|Le package échoue s'il n'utilise pas de commandes SQL paramétrables. Pour utiliser des commandes SQL paramétrables, utilisez la tâche d'exécution SQL dans votre package. Pour plus d’informations, consultez [Tâche d’exécution de requêtes SQL](../../integration-services/control-flow/execute-sql-task.md) et [Paramètres et codes de retour dans la tâche d’exécution SQL](http://msdn.microsoft.com/library/a3ca65e8-65cf-4272-9a81-765a706b8663).|  
|**datetime2**|Le gestionnaire de connexions ADO tronque les millisecondes.|  
  
> [!NOTE]  
>  Pour plus d’informations sur les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et leur mappage aux types de données [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], consultez [Types de données &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md) et [Types de données d’Integration Services](../../integration-services/data-flow/integration-services-data-types.md).  
  
## <a name="configuring-the-ado-connection-manager"></a>Configuration du gestionnaire de connexions ADO  
 Vous pouvez configurer un gestionnaire de connexions ADO de plusieurs manières :  
  
-   Indiquez une chaîne de connexion spécifique configurée pour répondre aux besoins du fournisseur sélectionné.  
  
-   Selon le fournisseur, incluez le nom de la source de données à laquelle se connecter.  
  
-   Fournissez les informations d'identification de sécurité nécessaires selon le fournisseur sélectionné.  
  
-   Indiquez si la connexion créée à partir du gestionnaire de connexions est conservée au moment de l'exécution.  
  
 Vous pouvez définir des propriétés au moyen du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.  
  
 Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :  
  
-   [Configurer le gestionnaire de connexions OLE DB](../../integration-services/connection-manager/configure-ole-db-connection-manager.md)  
  
 Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programmation](../../integration-services/building-packages-programmatically/adding-connections-programmatically.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Connexions Integration Services &#40;SSIS&#41;](../../integration-services/connection-manager/integration-services-ssis-connections.md)  
  
  