---
title: À l’aide de Transactions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, transactions
- transactions [SMO]
- SMO [SQL Server], transactions
ms.assetid: 399aded8-bee3-4cfb-a671-1877c7d0de9f
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d9f7984be9f48a3651d5dc804faabbc0cd9625f3
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48086159"
---
# <a name="using-transactions"></a>Utilisation de transactions
  Dans SMO ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects), le traitement transactionnel est effectué par le biais de la connexion à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection>. Le <xref:Microsoft.SqlServer.Management.Common.ServerConnection> objet est référencé par le <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> propriété de la <xref:Microsoft.SqlServer.Management.Smo.Server> de l’objet lorsque la connexion est établie. Des méthodes telles que <xref:Microsoft.SqlServer.Management.Common.DataTransferProgressEventType.StartTransaction>, <xref:Microsoft.SqlServer.Management.Common.ServerConnection.RollBackTransaction%2A> et <xref:Microsoft.SqlServer.Management.Common.ServerConnection.CommitTransaction%2A> appartiennent à la propriété de l'objet <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Création de programmes SMO](creating-smo-programs.md)  
  
  
