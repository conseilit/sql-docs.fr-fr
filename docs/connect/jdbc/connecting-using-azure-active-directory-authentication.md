---
title: Connexion avec l’authentification Azure Active Directory | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.reviewer: ''
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 9c9d97be-de1d-412f-901d-5d9860c3df8c
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 6c87e7b85282c7ca237689296e08d2b7645240ed
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47767137"
---
# <a name="connecting-using-azure-active-directory-authentication"></a>Connexion avec l’authentification Azure Active Directory

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

Cet article fournit des informations sur la façon de développer des applications Java à utiliser la fonctionnalité d’authentification Azure Active Directory avec le pilote Microsoft JDBC 6.0 (ou version ultérieure) pour SQL Server.

Vous pouvez utiliser l’authentification Azure Active Directory (AAD), ce qui est un mécanisme de connexion à Azure SQL Database v12 à l’aide d’identités dans Azure Active Directory. Utilisez l’authentification Azure Active Directory pour gérer de manière centralisée les identités des utilisateurs de base de données et comme alternative à l’authentification SQL Server. Le pilote JDBC vous permet de spécifier vos informations d’identification Azure Active Directory dans la chaîne de connexion JDBC pour se connecter à la base de données SQL Azure. Pour plus d’informations sur la façon de configurer l’authentification Azure Active Directory, visitez [connexion à SQL de base de données avec l’Azure Active Directory authentification](https://azure.microsoft.com/documentation/articles/sql-database-aad-authentication/). 

Deux nouvelles propriétés de connexion ont été ajoutées pour prendre en charge l’authentification Azure Active Directory :
*   **authentification**: utilisez cette propriété pour indiquer la méthode d’authentification SQL à utiliser pour la connexion. Les valeurs possibles sont : **ActiveDirectoryIntegrated**, **ActiveDirectoryPassword**, **SqlPassword**et la valeur par défaut **NotSpecified**.
    * Utilisez « authentication = ActiveDirectoryIntegrated » pour vous connecter à une base de données SQL à l’aide de l’authentification Windows intégrée. Pour utiliser ce mode d’authentification, vous devez fédérer le sur site Active Directory Federation Services (ADFS) avec AAD dans le cloud. Une fois cette opération a lieu, ainsi que d’un ticket Kerberos, vous pouvez accéder à Azure SQL DB sans avoir à saisir des informations d’identification lorsque vous êtes connecté dans un ordinateur joint au domaine. 
    * Utilisez « authentication = ActiveDirectoryPassword » pour vous connecter à une base de données SQL à l’aide d’un nom principal d’Azure AD et un mot de passe.
    * Utilisez « authentication = SqlPassword » pour vous connecter à un serveur SQL Server à l’aide des propriétés de l’utilisateur ou le nom d’utilisateur et mot de passe.
    * Utilisez ' authentification = NotSpecified » ou la laisser comme valeur par défaut quand aucune de ces méthodes d’authentification sont nécessaires.

*   **accessToken**: utilisez cette propriété pour se connecter à une base de données SQL à l’aide d’un jeton d’accès. accessToken peut uniquement être défini avec le paramètre de propriétés de la méthode getConnection() dans la classe DriverManager. Il ne peut pas être utilisé dans l’URL de connexion.  

Pour plus d’informations, consultez la propriété de l’authentification sur le [définissant les propriétés de connexion](../../connect/jdbc/setting-the-connection-properties.md) page.  


## <a name="client-setup-requirements"></a>Configuration requise du programme d’installation client
Assurez-vous que les composants suivants sont installés sur l’ordinateur client :
* Java 7 ou version ultérieure
*   Microsoft JDBC Driver 6.0 (ou version ultérieure) pour SQL Server
*   Si vous utilisez le mode d’authentification basée sur le jeton d’accès, vous devez [azure-activedirectory-library-for-java](https://github.com/AzureAD/azure-activedirectory-library-for-java) et ses dépendances pour exécuter les exemples de cet article. Pour plus d’informations, consultez **connexion à l’aide du jeton d’accès** section.
*   Si vous utilisez le mode d’authentification ActiveDirectoryPassword, vous devez [azure-activedirectory-library-for-java](https://github.com/AzureAD/azure-activedirectory-library-for-java) et ses dépendances. Pour plus d’informations, consultez **connexion à l’aide du Mode d’authentification ActiveDirectoryPassword** section.
*   Si vous utilisez le mode ActiveDirectoryIntegrated, vous avez besoin d’azure-activedirectory-library-for-java et ses dépendances. Pour plus d’informations, consultez **connexion à l’aide du Mode d’authentification ActiveDirectoryIntegrated** section.
    
## <a name="connecting-using-activedirectoryintegrated-authentication-mode"></a>Connexion à l’aide du Mode d’authentification ActiveDirectoryIntegrated
 Avec la version 6.4, Microsoft JDBC Driver prend en charge pour l’authentification ActiveDirectoryIntegrated à l’aide d’un ticket Kerberos sur plusieurs plateformes (Windows/Linux et Mac).
Pour plus d’informations, consultez [ticket Kerberos défini sur Windows, Linux et Mac](https://docs.microsoft.com/sql/connect/jdbc/connecting-using-azure-active-directory-authentication#set-kerberos-ticket-on-windows-linux-and-mac) pour plus d’informations. Vous pouvez également sur Windows, sqljdbc_auth.dll peut également servir pour l’authentification ActiveDirectoryIntegrated avec le pilote JDBC.

> [!NOTE]
>  Si vous utilisez une version antérieure du pilote, vérifiez cela [lien](../../connect/jdbc/feature-dependencies-of-microsoft-jdbc-driver-for-sql-server.md) pour les dépendances respectifs qui sont requises pour utiliser ce mode d’authentification. 

L’exemple suivant montre comment utiliser « authentication = ActiveDirectoryIntegrated' mode. Exécutez cet exemple sur un ordinateur joint au domaine qui est fédéré avec Azure Active Directory. Un utilisateur de base de données de relation contenant-contenu représentant votre principal Azure AD, ou l’un des groupes, vous appartenez à devez exister dans la base de données et devez avoir l’autorisation CONNECT. 

Avant de générer et exécuter l’exemple, sur l’ordinateur client (sur lequel, vous souhaitez exécuter l’exemple), téléchargez le [azure-activedirectory-library-for-java bibliothèque](https://github.com/AzureAD/azure-activedirectory-library-for-java) et ses dépendances et les inclure dans le chemin d’accès de build Java

Avant d’exécuter l’exemple, remplacez le nom de serveur/base de données avec votre nom de serveur/base de données dans les lignes suivantes :

```java
ds.setServerName("aad-managed-demo.database.windows.net"); // replace 'aad-managed-demo' with your server name
ds.setDatabaseName("demo"); // replace with your database name
```

L’exemple à utiliser le mode d’authentification ActiveDirectoryIntegrated :
```java
import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.Statement;

import com.microsoft.sqlserver.jdbc.SQLServerDataSource;

public class AADIntegrated {
    public static void main(String[] args) throws Exception {

        SQLServerDataSource ds = new SQLServerDataSource();
        ds.setServerName("aad-managed-demo.database.windows.net"); // Replace with your server name
        ds.setDatabaseName("demo"); // Replace with your database name
        ds.setAuthentication("ActiveDirectoryIntegrated");
        ds.setHostNameInCertificate("*.database.windows.net");

        try (Connection connection = ds.getConnection(); 
                Statement stmt = connection.createStatement();) {
            
            ResultSet rs = stmt.executeQuery("SELECT SUSER_SNAME()");
            if (rs.next()) {
                System.out.println("You have successfully logged on as: " + rs.getString(1));
            }
        }
    }
}
```
Exécution de cet exemple automatiquement sur un ordinateur client utilise votre ticket Kerberos et aucun mot de passe n’est nécessaire. Si une connexion est établie, vous devez voir le message suivant :
```
You have successfully logged on as: <your domain user name>
```

### <a name="set-kerberos-ticket-on-windows-linux-and-mac"></a>Définir le ticket Kerberos sur Windows, Linux et Mac

Vous devez configurer un ticket Kerberos liant votre utilisateur actuel à un compte de domaine Windows. Un résumé des étapes clés figurent ci-dessous.

#### <a name="windows"></a>Windows
JDK est fourni avec `kinit`, que vous pouvez utiliser pour obtenir un ticket TGT dans le centre de Distribution de clés (KDC) sur un domaine joint à un ordinateur qui est fédéré avec Azure Active Directory.

##### <a name="step-1-ticket-granting-ticket-retrieval"></a>Étape 1 : Récupération de Ticket Granting Ticket
- **Exécuter sur**: Windows
- **Action** :
  - Utilisez la commande `kinit username@DOMAIN.COMPANY.COM` pour obtenir un ticket TGT de KDC, puis il vous demandera votre mot de passe de domaine.
  - Utilisez `klist` pour afficher les tickets disponibles. Si le kinit a réussi, vous devez voir un ticket à partir de krbtgt/DOMAIN.COMPANY.COM@ DOMAIN.COMPANY.COM.

> [!NOTE]
>  Vous devrez peut-être spécifier un `.ini` de fichiers avec `-Djava.security.krb5.conf` pour votre application localiser le contrôleur de domaine Kerberos.

#### <a name="linux-and-mac"></a>Linux et Mac

##### <a name="requirements"></a>Spécifications
Accès à un ordinateur joint au domaine Windows pour interroger votre contrôleur de domaine Kerberos.

##### <a name="step-1-find-kerberos-kdc"></a>Étape 1 : Rechercher le KDC Kerberos
- **Exécuter sur**: ligne de commande Windows
- **Action**: `nltest /dsgetdc:DOMAIN.COMPANY.COM` (où « DOMAIN.COMPANY.COM » est mappé à un nom de votre domaine)
- **Résultat de l'exemple**
  ```
  DC: \\co1-red-dc-33.domain.company.com
  Address: \\2111:4444:2111:33:1111:ecff:ffff:3333
  ...
  The command completed successfully
  ```
- **Pour extraire des informations** nommez le contrôleur de domaine, dans ce cas `co1-red-dc-33.domain.company.com`

##### <a name="step-2-configuring-kdc-in-krb5conf"></a>Étape 2 : Configuration KDC dans krb5.conf
- **Exécuter sur**: Linux/Mac
- **Action**: modifier le /etc/krb5.conf dans un éditeur de votre choix. Configurez les clés suivantes
  ```
  [libdefaults]
    default_realm = DOMAIN.COMPANY.COM
   
  [realms]
  DOMAIN.COMPANY.COM = {
     kdc = co1-red-dc-28.domain.company.com
  }
  ```
  Puis enregistrez le fichier krb5.conf et sortie

> [!NOTE]
>  Domaine doit être en majuscules.

##### <a name="step-3-testing-the-ticket-granting-ticket-retrieval"></a>Étape 3 : Tester la récupération de Ticket Granting Ticket
- **Exécuter sur**: Linux/Mac
- **Action** :
  - Utilisez la commande `kinit username@DOMAIN.COMPANY.COM` pour obtenir un ticket TGT de KDC, puis il vous demandera votre mot de passe de domaine.
  - Utilisez `klist` pour afficher les tickets disponibles. Si le kinit a réussi, vous devez voir un ticket à partir de krbtgt/DOMAIN.COMPANY.COM@ DOMAIN.COMPANY.COM.

## <a name="connecting-using-activedirectorypassword-authentication-mode"></a>Connexion à l’aide du Mode d’authentification ActiveDirectoryPassword
L’exemple suivant montre comment utiliser « authentication = ActiveDirectoryPassword' mode.

Avant de générer et exécuter l’exemple :
1.  Sur l’ordinateur client (sur lequel, vous souhaitez exécuter l’exemple), téléchargez le [azure-activedirectory-library-for-java bibliothèque](https://github.com/AzureAD/azure-activedirectory-library-for-java) et ses dépendances et les inclure dans le chemin d’accès de build Java
2.  Recherchez les lignes de code suivantes et remplacez le nom de serveur/base de données par votre nom de serveur/base de données.
    ```java
    ds.setServerName("aad-managed-demo.database.windows.net"); // replace 'aad-managed-demo' with your server name
    ds.setDatabaseName("demo"); // replace with your database name
    ```
3.  Recherchez les lignes suivantes de code et remplacez le nom d’utilisateur, avec le nom de l’utilisateur d’AAD que vous souhaitez vous connecter en tant que.
    ```java
    ds.setUser("bob@cqclinic.onmicrosoft.com"); // replace with your user name
    ds.setPassword("password");     // replace with your password
    ```

L’exemple à utiliser le mode d’authentification ActiveDirectoryPassword :
```java
import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.Statement;

import com.microsoft.sqlserver.jdbc.SQLServerDataSource;

public class AADUserPassword {
    
    public static void main(String[] args) throws Exception{
        
        SQLServerDataSource ds = new SQLServerDataSource();
        ds.setServerName("aad-managed-demo.database.windows.net"); // Replace with your server name
        ds.setDatabaseName("demo"); // Replace with your database
        ds.setUser("bob@cqclinic.onmicrosoft.com"); // Replace with your user name
        ds.setPassword("password"); // Replace with your password
        ds.setAuthentication("ActiveDirectoryPassword");
        ds.setHostNameInCertificate("*.database.windows.net");
        
        try (Connection connection = ds.getConnection(); 
                Statement stmt = connection.createStatement();) {
            
            ResultSet rs = stmt.executeQuery("SELECT SUSER_SNAME()");
            if (rs.next()) {
                System.out.println("You have successfully logged on as: " + rs.getString(1));
            }
        }
    }
}
```
Si la connexion est établie, vous devez voir le message suivant en tant que sortie :
```
You have successfully logged on as: <your user name>
```

> [!NOTE]  
> Une base de données de relation contenant-contenu utilisateur doit exister et un utilisateur de base de données de relation contenant-contenu représentant spécifié utilisateur Azure AD ou l’un des groupes, Azure spécifié utilisateur AD appartient, doit exister dans la base de données et doit avoir l’autorisation de se connecter (à l’exception d’Azure Active Directory administrateur du serveur ou groupe)

## <a name="connecting-using-access-token"></a>Connexion à l’aide du jeton d’accès
Applications/services peut récupérer un jeton d’accès à partir d’Azure Active Directory et l’utiliser pour se connecter à la base de données SQL Azure.

> [!NOTE] 
> **accessToken** peut uniquement être définie à l’aide du paramètre des propriétés de la méthode getConnection() dans la classe DriverManager. Il ne peut pas être utilisé dans la chaîne de connexion.

L’exemple ci-dessous contient une simple application Java qui se connecte à la base de données SQL Azure à l’aide de l’authentification basée sur les jetons d’accès. Avant de générer et exécuter l’exemple, procédez comme suit :
1.  Créer un compte d’application dans Azure Active Directory pour votre service.
    1. Connectez-vous au portail Azure.
    2. Dans le volet de navigation gauche, cliquez sur Azure Active Directory.
    3. Cliquez sur l’onglet « Inscriptions d’application ».
    4. Dans le menu déroulant, cliquez sur « Nouvelle inscription d’application ».
    5. Entrez mytokentest sous la forme d’un nom convivial pour l’application, sélectionnez « application/API Web ».
    6. URL de connexion est inutile. Quoi que ce soit fournir uniquement : « http://mytokentest».
    7. En bas, cliquez sur « Créer ».
    9. Dans le portail Azure, cliquez sur l’onglet « Paramètres » de votre application et ouvrez l’onglet « Propriétés ».
    10. Recherchez la valeur « ID d’Application » (également appelé ID de Client) et copiez-la, car vous besoin plus tard lors de la configuration de votre application (par exemple, 1846943b-ad04-4808-aa13-4702d908b5c1). Consultez l’instantané suivant.
    11. Dans la section « Clés », créez une clé en renseignant le champ nom, en sélectionnant la durée de la clé et enregistrer la configuration (laissez le champ de valeur vide). Après l’enregistrement, la valeur doit être rempli automatiquement, copiez la valeur générée. Il s’agit du secret du client.
    12. Dans le volet gauche, cliquez sur Azure Active Directory. Sous « « inscriptions d’application, recherchez l’onglet « Points de terminaison ». Copiez l’URL sous « Serment 2.0 TOKEN ENDPOINT », il s’agit de l’URL de votre STS.
    
    ![JDBC_AAD_Token](../../connect/jdbc/media/jdbc_aad_token.png)  
2. Connectez-vous à la base de données utilisateur de votre serveur SQL Azure en tant qu’administrateur Azure Active Directory et l’utilisation d’un utilisateur de relation contenant-contenu de la base de données une disposition de la commande T-SQL pour votre application principale. Pour plus d’informations, consultez le [connexion à la base de données SQL ou SQL Data Warehouse en utilisant Azure Active Directory authentification](https://azure.microsoft.com/documentation/articles/sql-database-aad-authentication/) pour plus d’informations sur la création d’un administrateur Azure Active Directory et un utilisateur de base de données de relation contenant-contenu.

    ```
    CREATE USER [mytokentest] FROM EXTERNAL PROVIDER
    ```

3.  Sur l’ordinateur client (sur lequel, vous souhaitez exécuter l’exemple), téléchargez le [azure-activedirectory-library-for-java](https://github.com/AzureAD/azure-activedirectory-library-for-java) bibliothèque et ses dépendances et les inclure dans le chemin d’accès de build Java. Notez que l’azure-activedirectory-library-for-java est uniquement nécessaire pour exécuter cet exemple spécifique. L’exemple utilise les API à partir de cette bibliothèque pour récupérer le jeton d’accès d’Azure AAD. Si vous avez déjà un jeton d’accès, vous pouvez ignorer cette étape. Notez que vous devez également supprimer la section dans l’exemple qui Récupère le jeton d’accès.

Dans l’exemple suivant, remplacez le nom de l’URL du STS, ID de Client, clé secrète Client, serveur et base de données par vos valeurs.

```java
import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.Statement;
import java.util.concurrent.Executors;
import java.util.concurrent.Future;
import com.microsoft.sqlserver.jdbc.SQLServerDataSource;

// The azure-activedirectory-library-for-java is needed to retrieve the access token from the AD.
import com.microsoft.aad.adal4j.AuthenticationContext;
import com.microsoft.aad.adal4j.AuthenticationResult;
import com.microsoft.aad.adal4j.ClientCredential;

public class AADTokenBased {

    public static void main(String[] args) throws Exception {

        // Retrieve the access token from the AD.
        String spn = "https://database.windows.net/";
        String stsurl = "https://login.microsoftonline.com/..."; // Replace with your STS URL.
        String clientId = "1846943b-ad04-4808-aa13-4702d908b5c1"; // Replace with your client ID.
        String clientSecret = "..."; // Replace with your client secret.

        AuthenticationContext context = new AuthenticationContext(stsurl, false, Executors.newFixedThreadPool(1));
        ClientCredential cred = new ClientCredential(clientId, clientSecret);

        Future<AuthenticationResult> future = context.acquireToken(spn, cred, null);
        String accessToken = future.get().getAccessToken();

        System.out.println("Access Token: " + accessToken);

        // Connect with the access token.
        SQLServerDataSource ds = new SQLServerDataSource();

        ds.setServerName("aad-managed-demo.database.windows.net"); // Replace with your server name.
        ds.setDatabaseName("demo"); // Replace with your database name.
        ds.setAccessToken(accessToken);
        ds.setHostNameInCertificate("*.database.windows.net");

        try (Connection connection = ds.getConnection(); 
                Statement stmt = connection.createStatement();) {

            ResultSet rs = stmt.executeQuery("SELECT SUSER_SNAME()");
            if (rs.next()) {
                System.out.println("You have successfully logged on as: " + rs.getString(1));
            }
        }
    }
}
``` 

Si la connexion est établie, vous devez voir le message suivant en tant que sortie :
```java
Access Token: <your access token>
You have successfully logged on as: <your client ID>    
``` 
