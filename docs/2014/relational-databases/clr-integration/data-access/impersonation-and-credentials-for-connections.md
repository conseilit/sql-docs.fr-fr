---
title: L’emprunt d’identité et les informations d’identification pour les connexions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- impersonation [CLR integration]
- security [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- authentication [CLR integration]
- user impersonation [CLR integration]
- credentials [CLR integration]
- database objects [CLR integration], security
ms.assetid: 293dce7d-1db2-4657-992f-8c583d6e9ebb
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 05f3255dac93940439174c20b11769a022bcb7bd
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48072699"
---
# <a name="impersonation-and-credentials-for-connections"></a>Emprunt d'identité et informations d'identification pour les connexions
  Dans l'intégration du CLR (Common Language Runtime) [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'authentification Windows est complexe à utiliser, mais elle offre une protection supérieure à l'authentification SQL Server. Lorsque vous utilisez l'authentification Windows, gardez à l'esprit les points suivants.  
  
 Par défaut, un processus SQL Server qui se connecte à Windows acquiert le contexte de sécurité du compte de service Windows SQL Server. Mais il est possible de mapper une fonction CLR à une identité de proxy afin que ses connexions sortantes aient un contexte de sécurité différent de celui du compte de service Windows.  
  
 Dans certains cas, vous pouvez emprunter l'identité de l'appelant à l'aide de la propriété `SqlContext.WindowsIdentity` plutôt que de fonctionner en tant que compte de service. L'instance de `WindowsIdentity`, qui représente l'identité du client qui a appelé le code appelant, est uniquement disponible lorsque le client utilise l'authentification Windows. Après avoir obtenu l'instance de `WindowsIdentity`, vous pouvez appeler `Impersonate` pour modifier le jeton de sécurité du thread, puis ouvrir des connexions ADO.NET pour le compte du client.  
  
 Après avoir appelé SQLContext.WindowsIdentity.Impersonate, vous ne pouvez pas accéder aux données locales et vous ne pouvez pas accéder aux données système. Pour accéder aux données à nouveau, vous devez appeler WindowsImpersonationContext.Undo.  
  
 L'exemple suivant montre comment emprunter l'identité de l'appelant à l'aide de la propriété `SqlContext.WindowsIdentity`.  
  
 Visual C#   
  
```  
WindowsIdentity clientId = null;  
WindowsImpersonationContext impersonatedUser = null;  
  
clientId = SqlContext.WindowsIdentity;  
  
// This outer try block is used to protect from   
// exception filter attacks which would prevent  
// the inner finally block from executing and   
// resetting the impersonation.  
try  
{  
   try  
   {  
      impersonatedUser = clientId.Impersonate();  
      if (impersonatedUser != null)  
         return GetFileDetails(directoryPath);  
         else return null;  
   }  
   finally  
   {  
      if (impersonatedUser != null)  
         impersonatedUser.Undo();  
   }  
}  
catch  
{  
   throw;  
}  
```  
  
> [!NOTE]  
>  Pour plus d’informations sur les changements de comportement dans l’emprunt d’identité, consultez [modifications avec rupture des fonctionnalités du moteur de base de données dans SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).  
  
 Par ailleurs, si vous avez obtenu l'instance de l'identité [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows, vous ne pouvez pas, par défaut, propager cette instance à un autre ordinateur, cette opération étant restreinte par défaut par l'infrastructure de sécurité Windows. Il existe cependant un mécanisme, appelé « délégation », qui permet la propagation d'identités Windows sur plusieurs ordinateurs approuvés. Plus d’informations sur la délégation dans l’article TechNet, «[Kerberos Protocol Transition and Constrained Delegation](http://go.microsoft.com/fwlink/?LinkId=50419)».  
  
## <a name="see-also"></a>Voir aussi  
 [Objet SqlContext](../../clr-integration-data-access-in-process-ado-net/sqlcontext-object.md)  
  
  
