---
title: 'Étape 5 : Test du package du didacticiel de la leçon 4 | Microsoft Docs'
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: tutorial
ms.assetid: 5f18df92-0248-4858-836b-c8b02f0e0439
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 415a49c49b21f1b4abb5d965926bfa68bb8fc3de
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47720667"
---
# <a name="lesson-4-5---testing-the-lesson-4-tutorial-package"></a>Leçon 4-5 : Test du package du didacticiel de la leçon 4
Au moment de l'exécution, le fichier corrompu, Currency_BAD.txt, ne parvient pas à générer une correspondance avec la transformation de recherche Currency Key. Du fait que la sortie d'erreur de la transformation de recherche Currency Key a été configurée en vue de réacheminer les lignes qui ont échoué vers une nouvelle destination de lignes échouées, le composant n'échoue pas et le package s'exécute correctement. Toutes les lignes qui ont échoué sont enregistrées dans le fichier ErrorOutput.txt.  
  
Au cours de cette tâche, vous allez tester la configuration de sortie d'erreur révisée en exécutant le package. Une fois le package exécuté, vous visualiserez le contenu du fichier ErrorOutput.txt.  
  
> [!NOTE]  
> Pour éviter l'accumulation de lignes d'erreur dans le fichier ErrorOutput.txt, vous devez manuellement supprimer le contenu du fichier entre chaque exécution du package.  
  
## <a name="checking-the-package-layout"></a>Vérification de la disposition du package  
Avant de tester le package, vous devez vérifier que le flux de contrôle et le flux de données dans le package de la leçon 4 contiennent les objets affichés dans les diagrammes suivants. Le flux de contrôle doit être identique au flux de contrôle des leçons 2 à 4.  
  
**Flux de contrôle**  
  
![Flux de contrôle dans le package](../integration-services/media/task4lesson2control.gif "Flux de contrôle dans le package")  
  
**Flux de données**  
  
![Flux de données dans le package](../integration-services/media/task5lesson5data.gif "Flux de données dans le package")  
  
### <a name="to-run-the-lesson-4-tutorial-package"></a>Pour exécuter le package du didacticiel Lesson 4  
  
1.  Dans le menu **Déboguer** , cliquez sur **Démarrer le débogage**.  
  
2.  Une fois l'exécution du package terminée, dans le menu **Déboguer** , cliquez sur **Arrêter le débogage**.  
  
### <a name="to-verify-the-contents-of-the-erroroutputtxt-file"></a>Pour vérifier le contenu du fichier ErrorOutput.txt  
  
-   Dans le Bloc-notes ou un autre éditeur de texte, ouvrez le fichier ErrorOutput.txt. L'ordre par défaut des colonnes est le suivant : AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.  
  
    Notez que toutes les lignes du fichier contiennent la valeur CurrencyID non appariée définie à BAD, la valeur ErrorCode définie à -1071607778, la valeur ErrorColumn définie à 0 et la valeur ErrorDescription dévoilant le message « Aucune correspondance de ligne trouvée au cours de la recherche ». La valeur de ErrorColumn est définie à 0 puisque l'erreur n'est pas liée à une colonne. C'est l'opération de recherche qui a échoué. .  
  
  
  
