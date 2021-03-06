---
title: Méthode getEncrypt (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- getEncrypt Method (SQLServerDataSource)
apilocation:
- getEncrypt Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: 1cdb12dd-6e6f-4bbd-8f5f-9e630f3ee2c9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 328bf9921bc4d70ef77862edd1476e2f8f629720
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47637097"
---
# <a name="getencrypt-method-sqlserverdatasource"></a>Méthode getEncrypt (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retourne une valeur **booléenne** qui indique si la propriété encrypt est activée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public boolean getEncypt()  
```  
  
## <a name="return-value"></a>Valeur retournée  
 **true** si chiffrer est activé. Dans le cas contraire, la valeur est **false**.  
  
## <a name="remarks"></a>Notes   
 Si la propriété encrypt est définie sur **true**, le [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] vérifie que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilise le chiffrement SSL pour toutes les données envoyées entre le client et le serveur, si un certificat est installé sur le serveur.  
  
 Si la propriété encrypt n’est pas spécifiée ou si elle est définie sur **false**, le pilote n’impose pas à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] la prise en charge du chiffrement SSL. Si l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] n’est pas configurée pour imposer le chiffrement SSL, une connexion est établie sans aucun chiffrement. Si l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est configurée pour forcer le chiffrement SSL, le [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] active automatiquement le chiffrement SSL lors de l’exécution sur une machine virtuelle Java (JVM) correctement configurée ; sinon, la connexion est interrompue et le pilote génère une erreur. Si la propriété de chiffrement n’est pas définie, la méthode [getEncrypt](../../../connect/jdbc/reference/getencrypt-method-sqlserverdatasource.md) retourne la valeur par défaut **false**.  
  
## <a name="see-also"></a> Voir aussi  
 [SQLServerDataSource, membres](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource, classe](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
