---
title: Prise en main de SSMA pour DB2 Console (DB2ToSQL) | Documents Microsoft
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: f245c017-023e-4880-8721-8908d339525e
caps.latest.revision: 5
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 24c96c6e76d89d271d80e3be51c8c27d62dbd6b3
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="getting-started-with-ssma--for-db2-console-db2tosql"></a>Prise en main de SSMA pour DB2 Console (DB2ToSQL)
Cette section décrit la procédure pour lancer et commencer à l’application de console DB2. Dans la liste, qu’elle contient, sont les conventions utilisées dans une fenêtre de sortie de Console de SSMA classique.  
  
## <a name="launching-ssma-console"></a>Lancer la Console SSMA  
Utilisez les étapes suivantes pour démarrer l’application de console SSMA :  
  
1.  Accédez à **Démarrer** et pointez sur **tous les programmes**.  
  
2.  Cliquez sur le  **[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] l’Assistant Migration de l’invite de commandes DB2** contextuel.  
  
    Il affiche le menu de l’utilisation de SSMA Console et `(/? Help)`, pour vous aider à démarrer avec l’application console.  
  
## <a name="procedure-for-using-the-ssma-console"></a>Procédure d’utilisation de la Console SSMA  
Une fois que la console est lancée correctement sur votre système Windows, vous pouvez utiliser les étapes suivantes pour travailler dessus :  
  
1.  Configurer la Console de SSMA via les fichiers de script. Pour plus d’informations sur cette section, consultez [création de fichiers de Script &#40; DB2ToSQL &#41;](../../ssma/db2/creating-script-files-db2tosql.md) .  
  
2.  [Création de fichiers de la valeur de la Variable &#40; DB2ToSQL &#41;](../../ssma/db2/creating-variable-value-files-db2tosql.md)  
  
3.  [Créer les fichiers de connexion de serveur &#40; DB2ToSQL &#41;](../../ssma/db2/creating-the-server-connection-files-db2tosql.md)  
  
4.  [L’exécution de la Console SSMA &#40; DB2ToSQL &#41; ](../../ssma/db2/executing-the-ssma-console-db2tosql.md) selon les besoins de votre projet  
  
Fonctionnalités supplémentaires :  
  
1.  [La gestion des mots de passe](http://msdn.microsoft.com/en-us/56d546e3-8747-4169-aace-693302667e94) et exporter / importer sur d’autres ordinateurs de la fenêtre  
  
2.  [Génération de rapports](http://msdn.microsoft.com/en-us/69ef5fd9-190d-4c58-8199-b3f77d5e1883) pour afficher le code xml détaillé rapports pour évaluation /conversion et migration des données de sortie. Rapports d’erreur détaillé peuvent également être générées pour les commandes d’actualisation et la synchronisation.  
  
## <a name="ssma-console-output-conventions"></a>Conventions de sortie de Console SSMA  
Lors de l’exécution des commandes de script SSMA et des options, le programme de console affiche les résultats et les messages (information, erreur, etc.) à l’utilisateur sur la console ou si nécessaire, redirige vers un fichier de sortie xml. Chaque type de message dans la sortie est signalé par une couleur unique. Par exemple, le message de couleur blanche indique les commandes du fichier de script. celui de couleur verte représente une invite de commandes pour l’entrée d’utilisateur et ainsi de suite.  
  
![Output_Oracle de Console SSMA](../../ssma/db2/media/ssmaconsoleoutput_oracle.jpg "Output_Oracle de Console SSMA")  
  
Interprétation de couleur de la sortie de console dans le tableau suivant :  
  
|Color| Description|  
|---------|---------------|  
|Rouge|Erreur irrécupérable lors de l’exécution|  
|Gris|Cachet de date et heure, le message à l’utilisateur|  
|White|Commandes du fichier de script, le type de message|  
|Jaune|Avertissement|  
|Vert|Invite d’entrée d’utilisateur|  
|Cyan|Début, fin et le résultat d’une opération|  
  
## <a name="see-also"></a>Voir aussi  
[L’installation de SSMA pour DB2](http://msdn.microsoft.com/en-us/79fbe8ea-471b-407a-be2a-4100d9b57c61)  
  
