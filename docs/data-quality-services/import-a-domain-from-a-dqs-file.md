---
title: "Importer un domaine &#224; partir d&#39;un fichier&#160;.dqs | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fabd88b0-22b3-4543-a993-6d5b202ded80
caps.latest.revision: 18
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 18
---
# Importer un domaine &#224; partir d&#39;un fichier&#160;.dqs
  Cette rubrique explique comment importer un domaine à partir d'un fichier .dqs vers une base de connaissances existante dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS). Un fichier de données .dqs est créé en exportant un domaine ou une base de connaissances à partir de l'application [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] . Un fichier de données .dqs est chiffré, et ne peut pas être affiché.  
  
 L'utilisation d'un fichier de données .dqs pour exporter un domaine d'une base de connaissances puis l'importer vers une autre base de connaissances simplifie le processus de génération de connaissances, et permet d'économiser aussi bien du temps que des efforts. Il vous permet de partager un domaine et ses connaissances avec d'autres, ce qui leur fait gagner du temps. Vous pouvez importer un domaine unique ou un domaine composite (contenant plusieurs domaines uniques). Un fichier .dqs contenant un domaine unique inclut toutes les données du domaine avec les propriétés de domaine, les valeurs et les données des règles, à l'exception des informations de données de référence mappées. Un fichier .dqs contenant un domaine composite inclut toutes les données du domaine composite, notamment toutes les données des domaines uniques contenus dans le domaine composite, ainsi que les propriétés, les relations de valeur et les règles du domaine composite, à l'exception des données de référence mappées. Les données publiées et non publiées seront importées.  
  
 Lorsque vous importez un domaine, le nom du domaine reste le même que le nom du domaine exporté à l'origine, à moins que ce nom de domaine existe déjà, auquel cas DQS ajoute « _1 » au nom. C'est également le cas si vous importez un domaine composite qui contient un domaine individuel portant le même nom qu'un domaine existant.  
  
##  <a name="BeforeYouBegin"></a> Avant de commencer  
  
###  <a name="Prerequisites"></a> Conditions préalables  
 Pour importer un domaine à partir d'un fichier .dqs, vous devez avoir déjà exporté un domaine unique ou un domaine composite (contenant plusieurs domaines uniques) vers le fichier .dqs. Le fichier .dqs doit contenir un seul domaine. Vous devez également avoir créé et ouvert une base de connaissances dans laquelle importer le domaine.  
  
###  <a name="Security"></a> Sécurité  
  
####  <a name="Permissions"></a> Autorisations  
 Vous devez disposer du rôle dqs_kb_editor ou dqs_administrator sur la base de données DQS_MAIN pour importer un domaine à partir d'un fichier de données .dqs.  
  
##  <a name="Import"></a> Importer un domaine à partir d'un fichier .dqs  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Exécutez l’Application Data Quality Client](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  Sur l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , ouvrez une base de connaissances dans l'activité Gestion de l'arborescence du domaine.  
  
3.  Cliquez sur l'icône **Importer un domaine à partir d'un fichier de données** .  
  
4.  Dans la **Importer à partir du fichier de données** boîte de dialogue, accédez au dossier que vous souhaitez importer le fichier, sélectionnez le fichier (de type fichier DQS), puis cliquez sur **Ouvrir**.  
  
5.  Dans la boîte de dialogue **Importer un domaine** , cliquez sur **OK**.  
  
    > [!NOTE]  
    >  L'opération d'importation réussit uniquement si le fichier .dqs à partir duquel vous effectuez l'importation ne contient qu'un domaine unique ou un domaine composite (contenant plusieurs domaines uniques).  
  
6.  Vérifiez que le domaine que vous avez importé s'affiche dans la liste **Domaine** . Si vous avez importé un domaine composite, vérifiez que le domaine composite et les domaines uniques qu'il contient figurent tous dans la liste **Domaine** .  
  
##  <a name="FollowUp"></a> Suivi : Après l'importation d'un domaine à partir d'un fichier .dqs  
 Après avoir importé un domaine à partir d'un fichier .dqs, vous pouvez ajouter des connaissances au domaine ou utiliser le domaine dans un projet de nettoyage ou de correspondance, en fonction du contenu du domaine. Pour plus d’informations, consultez [effectuer une découverte des connaissances](../data-quality-services/perform-knowledge-discovery.md), [Gestion d’un domaine](../data-quality-services/managing-a-domain.md), [Gestion d’un domaine Composite](../data-quality-services/managing-a-composite-domain.md), [créer une stratégie de correspondance](../data-quality-services/create-a-matching-policy.md), [le nettoyage des données](../data-quality-services/data-cleansing.md), ou [correspondance des données](../data-quality-services/data-matching.md).  
  
  