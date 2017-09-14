---
title: "Élément Restore (XMLA) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Restore Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Restore
- urn:schemas-microsoft-com:xml-analysis#Restore
- microsoft.xml.analysis.restore
helpviewer_keywords:
- Restore command
ms.assetid: bb5a0c92-3927-4fa4-975b-6e4d79e0a912
caps.latest.revision: 26
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 08586ce2b7d5126250b82bc65655c7b69872a346
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="restore-element-xmla"></a>Élément Restore (XMLA)
  Restaure un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] base de données à partir d’un fichier de sauvegarde.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Command>  
   <Restore>  
      <DatabaseName>...</DatabaseName>  
      <DatabaseID>...</DatabaseID>  
      <File>...</File>  
      <Security>...</Security>  
      <AllowOverwrite>...</AllowOverwrite>  
      <Password>...</Password>  
      <Locations>...</Locations>  
      <DbStorageLocation>...</DbStorageLocation>  
   </Restore>  
</Command>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Aucune|  
|Valeur par défaut|Aucune|  
|Cardinalité|0-n : élément facultatif pouvant apparaître plusieurs fois.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Command](../../../analysis-services/xmla/xml-elements-properties/command-element-xmla.md)|  
|Éléments enfants|[AllowOverwrite](../../../analysis-services/xmla/xml-elements-properties/allowoverwrite-element-xmla.md), [DatabaseName](../../../analysis-services/xmla/xml-elements-properties/databasename-element-xmla.md), [DatabaseID](../../../analysis-services/xmla/xml-elements-properties/databaseid-element-xmla.md), [fichier](../../../analysis-services/xmla/xml-elements-properties/file-element-xmla.md), [emplacements](../../../analysis-services/xmla/xml-elements-properties/locations-element-xmla.md), [mot de passe](../../../analysis-services/xmla/xml-elements-properties/password-element-xmla.md), [sécurité](../../../analysis-services/xmla/xml-elements-properties/security-element-xmla.md), [DbStorageLocation](../../../analysis-services/xmla/xml-elements-properties/dbstoragelocation-element.md)|  
  
## <a name="remarks"></a>Notes  
 Le **restaurer** commande restaure un [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] base de données spécifiée dans le **DatabaseName** élément à partir d’un fichier de sauvegarde et, éventuellement, restaurer des partitions distantes à partir des fichiers de sauvegarde distants.  
  
 Les informations restaurées par la commande **Restore** varient en fonction du mode de stockage utilisé par les objets stockés dans le fichier de sauvegarde, comme indiqué dans le tableau suivant.  
  
|Mode de stockage|Informations|  
|------------------|-----------------|  
|OLAP multidimensionnel (MOLAP)|Données sources, agrégations et métadonnées|  
|Hybrid OLAP (HOLAP)|Agrégations et métadonnées|  
|OLAP relationnel (ROLAP)|Métadonnées|  
  
 Pendant un **restaurer** de commande, un verrou exclusif est placé sur le [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] base de données spécifiée dans le **DatabaseName** élément. Le verrou est libéré lorsque la commande **Restore** est terminée.  
  
 Pour plus d’informations sur la sauvegarde et restauration des bases de données, consultez [sauvegarde, restauration et synchroniser les bases de données &#40; XMLA &#41; ](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md).  
  
> [!IMPORTANT]  
>  Pour chaque fichier de sauvegarde, l'utilisateur qui exécute la commande de restauration doit avoir l'autorisation de lire à partir de l'emplacement de sauvegarde spécifié pour chaque fichier. Pour restaurer une base de données [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] qui n'est pas installée sur le serveur, l'utilisateur doit également être un membre du rôle serveur pour cette instance d' [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] . Pour remplacer une base de données [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , l’utilisateur doit avoir l’un des rôles suivants : membre du rôle serveur pour l’instance d’ [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ou membre d’un rôle de base de données avec les autorisations de contrôle total (Administrateur) sur la base de données à restaurer.  
  
> [!NOTE]  
>  Après la restauration d'une base de données existante, l'utilisateur qui a restauré la base de données peut perdre l'accès à la base de données restaurée. Cette perte d'accès peut se produire si, au moment de la sauvegarde, l'utilisateur n'était pas un membre du rôle de serveur ou un membre du rôle de base de données avec les autorisations de contrôle total (Administrateur).  
  
## <a name="see-also"></a>Voir aussi  
 [Élément Backup &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/backup-element-xmla.md)   
 [Élément de lot &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md)   
 [Élément Parallel &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/parallel-element-xmla.md)   
 [Synchroniser, élément &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)   
 [Commandes &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/xml-elements-commands.md)  
  
  