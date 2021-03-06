---
title: Création de l’URL de connexion | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 44996746-d373-4f59-9863-a8a20bb8024a
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d009a20b4e3a432cdea72a881024ca3aead1bc09
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47658797"
---
# <a name="building-the-connection-url"></a>Création de l'URL de connexion
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  La forme générale d'une URL de connexion est  
  
 `jdbc:sqlserver://[serverName[\instanceName][:portNumber]][;property=value[;property=value]]`  
  
 où :  
  
-   **jdbc:sqlserver://** (obligatoire) constitue le sous-protocole et sa constante.  
  
-   **serverName** (facultatif) correspond à l’adresse du serveur auquel se connecter. Il peut s'agir d'une adresse DNS ou IP, de localhost ou de 127.0.0.1 pour l'ordinateur local. S'il n'est pas spécifié dans l'URL de connexion, le nom du serveur doit être spécifié dans la collection de propriétés.  
  
-   **instanceName** (facultatif) est l’instance à laquelle se connecter sur serverName. Si cette valeur n'est pas spécifiée, une connexion à l'instance par défaut est établie.  
  
-   **portNumber** (facultatif) est le port auquel se connecter sur serverName. La valeur par défaut est 1433. Si vous utilisez la valeur par défaut, vous ne devez pas spécifier dans l’URL le port ni le signe « : » qui le précède.  
  
    > [!NOTE]  
    >  Pour des performances de connexion optimales, vous devez définir la valeur de portNumber lors de la connexion à une instance nommée. Cela permet d'éviter une boucle avec le serveur pour déterminer le numéro du port. Si un portNumber et un instanceName sont utilisés, le portNumber aura la priorité et l'instanceName sera ignoré.  
  
-   **property** (facultatif) correspond à une ou plusieurs propriétés de connexion. Pour plus d’informations, consultez [Définition des propriétés de connexion](../../connect/jdbc/setting-the-connection-properties.md). Vous pouvez spécifier n'importe quelle propriété de la liste. Les propriétés peuvent séparées seulement des points-virgules (« ; ») et ne peuvent pas figurer en doublon.  
  
> [!CAUTION]  
>  Pour des raisons de sécurité, il convient d'éviter de créer les URL de connexion en se basant sur des entrées utilisateur. Il est préférable de spécifier uniquement le nom du serveur et le pilote dans l'URL. Pour les valeurs de nom d'utilisateur et de mot de passe, utilisez des collections de propriétés de connexion. Pour plus d’informations sur la sécurité de vos applications JDBC, consultez [sécurisation des Applications de pilote JDBC](../../connect/jdbc/securing-jdbc-driver-applications.md).  
  
## <a name="connection-examples"></a>Exemples de connexion  
 Connectez-vous à la base de données par défaut sur l'ordinateur local à l'aide d'un nom d'utilisateur et d'un mot de passe :  
  
 `jdbc:sqlserver://localhost;user=MyUserName;password=*****;`  
  
> [!NOTE]  
>  Bien que l'exemple précédent utilise un nom d'utilisateur et un mot de passe dans la chaîne de connexion, vous devez utiliser une sécurité intégrée, pour mieux sécuriser. Pour plus d’informations, consultez la section [Connexion avec une authentification intégrée](#Connectingintegrated) plus loin dans cette rubrique.  
  
 La chaîne de connexion suivante montre un exemple de connexion à une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide de l’authentification intégrée et de Kerberos à partir d’une application qui s’exécute sur n’importe quel système d’exploitation pris en charge par [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] :  
  
```java
jdbc:sqlserver://;servername=server_name;integratedSecurity=true;authenticationScheme=JavaKerberos  
```  
  
 Connexion à la base de données par défaut sur l'ordinateur local à l'aide d'une authentification intégrée :  
  
 `jdbc:sqlserver://localhost;integratedSecurity=true;`  
  
 Connexion à une base de données nommée sur un serveur distant :  
  
 `jdbc:sqlserver://localhost;databaseName=AdventureWorks;integratedSecurity=true;`  
  
 Connexion au port par défaut du serveur distant :  
  
 `jdbc:sqlserver://localhost:1433;databaseName=AdventureWorks;integratedSecurity=true;`  
  
 Connexion en spécifiant un nom d'application personnalisé :  
  
 `jdbc:sqlserver://localhost;databaseName=AdventureWorks;integratedSecurity=true;applicationName=MyApp;`  
  
## <a name="named-and-multiple-sql-server-instances"></a>Instances SQL Server nommées et multiples  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permet d’installer plusieurs instances de bases de données par serveur. Chaque instance est identifiée par un nom spécifique. Pour établir une connexion avec une instance nommée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez soit spécifier le numéro de port de l’instance nommée (recommandé), soit spécifier le nom d’instance comme propriété d’URL JDBC ou comme propriété **datasource**. Si aucune propriété de nom d'instance ou de numéro de port n'est spécifiée, une connexion à l'instance par défaut est établie. Observez les exemples suivants :  
  
 Pour utiliser un numéro de port, procédez comme suit :  
  
 `jdbc:sqlserver://localhost:1433;integratedSecurity=true;<more properties as required>;`  
  
 Pour utiliser une propriété d'URL JDBC, procédez comme suit :  
  
 `jdbc:sqlserver://localhost;instanceName=instance1;integratedSecurity=true;<more properties as required>;`  
  
## <a name="escaping-values-in-the-connection-url"></a>Échappement de valeurs dans l'URL de connexion  
 Il se peut que vous deviez procéder à l'échappement de certaines parties des valeurs d'URL de connexion en raison de l'inclusion de caractères spéciaux tels que des espaces, des points-virgules ou des points d'interrogation. Le pilote JDBC prend en charge l'échappement de ces caractères s'ils sont placés entre accolades. Par exemple, {;} échappe un point-virgule.  
  
 Les valeurs d'échappement peuvent contenir des caractères spéciaux (« = », « ; », « [] » ou un espace) mais ne peuvent pas contenir d'accolades. Les valeurs qui doivent être échappées et qui contiennent des accolades doivent être ajoutées à une collection de propriétés.  
  
> [!NOTE]  
>  Un espace vide entre les accolades est un littéral qui n'est pas supprimé.  
  
##  <a name="Connectingintegrated"></a> Connexion avec une authentification intégrée sur Windows  
 Le pilote JDBC prend en charge l'utilisation d'une authentification intégrée de type 2 sur les systèmes d'exploitation Windows via la propriété de chaîne de connexion integratedSecurity. Pour utiliser l'authentification intégrée, copiez le fichier sqljdbc_auth.dll dans un répertoire sur le chemin du système Windows de l'ordinateur sur lequel le pilote JDBC est installé.  
  
 Les fichiers sqljdbc_auth.dll sont installés à l'emplacement suivant :  
  
 \<*répertoire d’installation*> \sqljdbc_\<*version*>\\<*langage*> \auth\  
  
 Pour n’importe quel système d’exploitation pris en charge par le [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)], consultez [à l’aide de l’authentification intégrée Kerberos pour se connecter à SQL Server](../../connect/jdbc/using-kerberos-integrated-authentication-to-connect-to-sql-server.md) pour obtenir une description de la fonctionnalité ajoutée dans [!INCLUDE[jdbc_40](../../includes/jdbc_40_md.md)] qui permet à une application pour se connecter à un base de données à l’aide de l’authentification intégrée avec le Kerberos Type 4.  
  
> [!NOTE]  
>  Si vous exécutez une machine virtuelle Java (JVM) 32 bits, utilisez le fichier sqljdbc_auth.dll dans le dossier x86, même si la version du système d'exploitation est x64. Si vous exécutez une machine virtuelle Java (JVM) 64 bits sur un processeur x64, utilisez le fichier sqljdbc_auth.dll dans le dossier x64.  
  
 Vous pouvez également définir la propriété système java.libary.path afin de spécifier le répertoire du fichier sqljdbc_auth.dll. Par exemple, si le pilote JDBC est installé dans le répertoire par défaut, vous pouvez spécifier l'emplacement de la DLL à l'aide de l'argument de machine virtuelle suivant lors du démarrage de l'application Java :  
  
 `-Djava.library.path=C:\Microsoft JDBC Driver 6.4 for SQL Server\sqljdbc_<version>\enu\auth\x86`  
  
## <a name="connecting-with-ipv6-addresses"></a>Connexion à l'aide d'adresses IPv6  
 Le pilote JDBC prend en charge l'utilisation d'adresses IPv6 avec la collection de propriétés de connexion et avec la propriété de chaîne de connexion serverName. La valeur initiale de serverName, comme jdbc:*sqlserver*://*nom_serveur*, n’est pas prise en charge pour les adresses IPv6 dans des chaînes de connexion. L’utilisation d’un nom au lieu d’une adresse IPv6 brute pour *serverName* fonctionne dans tous les cas pour la connexion. Les exemples suivants fournissent des informations complémentaires.  
  
 **Pour utiliser la propriété serverName**  
  
 `jdbc:sqlserver://;serverName=3ffe:8311:eeee:f70f:0:5eae:10.203.31.9\\instance1;integratedSecurity=true;`  
  
 **Pour utiliser la collection de propriétés**  
  
 `Properties pro = new Properties();`  
  
 `pro.setProperty("serverName", "serverName=3ffe:8311:eeee:f70f:0:5eae:10.203.31.9\\instance1");`  
  
 `Connection con = DriverManager.getConnection("jdbc:sqlserver://;integratedSecurity=true;", pro);`  
  
## <a name="see-also"></a> Voir aussi  
 [Connexion à SQL Server avec le pilote JDBC](../../connect/jdbc/connecting-to-sql-server-with-the-jdbc-driver.md)  
  
  
