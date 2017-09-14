---
title: "Types de données XML du scripts Language (ASSL) Analysis Services | Documents Microsoft"
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
- Analysis Services Scripting Language XML Data Types
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- ASSL, data types
- Analysis Services Scripting Language, data types
- data types [Analysis Services Scripting Language]
ms.assetid: 8e527916-932e-48ec-9010-f22cd4b721e2
caps.latest.revision: 21
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 63371810e2a7c41fab2935dfeb94a03b9250385a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="analysis-services-scripting-language-xml-data-types-assl"></a>Types de données XML Analysis Services Scripting Language (ASSL)
  Cette section de référence contient des informations de syntaxe et d'utilisation pour chaque élément agissant en tant que type dans le schéma ASSL (Analysis Services Scripting Language).  
  
 Bien que le schéma ASSL renferme uniquement des éléments XML à partir du point de vue d’un développeur, les éléments décrits dans cette section correspondent aux types, tels que **liaison** et **autorisation**, qui sont utilisés pour définir les éléments enfants et les propriétés d’autres objets.  
  
 Les éléments de type, tels que les éléments objets, ne sont jamais des éléments de niveau feuille au sein du schéma ASSL mais disposent d'éléments enfants et d'éléments qui correspondent aux propriétés des objets.  
  
 Toutefois un élément de type n’apparaît jamais comme un élément dans un script qui définit ou décrit [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objets. Au lieu de cela, il apparaît comme type d’autres éléments de l’objet, généralement désigné par le **type** attribut du schéma d’Instance du schéma XML à l’aide **xsi : type** ou **msdata**. Par exemple, `<Assembly xsi:type="ClrAssembly">...</Assembly>`.  
  
 Dans certains cas, un type provient d'un autre type. Par exemple, le **CubeBinding** dérive du type du parent **liaison** type.  
  
|Élément| Description|  
|-------------|-----------------|  
|[Type de données action &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/action-data-type-assl.md)|Définit un type de données primitif abstrait qui représente une action dans un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément ou un [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Type de données AggregationAttribute &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationattribute-data-type-assl.md)|Définit un type de données primitif qui représente l’association entre un [agrégation](../../../analysis-services/scripting/objects/aggregation-element-assl.md) élément et un attribut.|  
|[Type de données AggregationDesignAttribute &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationdesignattribute-data-type-assl.md)|Définit un type de données primitif qui représente l’association entre un attribut et un [AggregationDesignDimension](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md) élément.|  
|[Type de données AggregationDesignDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md)|Définit un type de données primitif qui représente la relation entre une dimension de cube et un [AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md) élément.|  
|[Type de données AggregationDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationdimension-data-type-assl.md)|Définit un type de données primitif qui représente la relation entre une dimension et un [agrégation](../../../analysis-services/scripting/objects/aggregation-element-assl.md) élément.|  
|[Type de données AggregationInstanceAttribute &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationinstanceattribute-data-type-assl.md)|Définit un type de données primitif qui fournit des informations sur un attribut utilisé par une instance d'agrégation.|  
|[Type de données AggregationInstanceCubeDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationinstancecubedimension-data-type-assl.md)|Définit un type de données primitif qui fournit des informations sur une dimension de cube utilisée par une instance d'agrégation.|  
|[Type de données AggregationInstanceMeasure &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationinstancemeasure-data-type-assl.md)|Définit un type de données primitif qui fournit des informations sur une mesure utilisée par une instance d'agrégation.|  
|[Type de données assembly &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/assembly-data-type-assl.md)|Définit un type de données primitif abstrait qui représente un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assembly ou une bibliothèque de liens dynamiques (DLL) COM associée une [Server](../../../analysis-services/scripting/objects/server-element-assl.md) ou [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Type de données AttributeBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/attributebinding-data-type-assl.md)|Définit un type de données dérivé qui représente une liaison pour un [attribut](../../../analysis-services/scripting/objects/attribute-element-assl.md) élément.|  
|[Type de données AttributeTranslation &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/attributetranslation-data-type-assl.md)|Définit un type de données dérivé représentant une traduction associée une [attribut](../../../analysis-services/scripting/objects/attribute-element-assl.md) élément|  
|[Type de liaison de données &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/binding-data-type-assl.md)|Définit un type de données primitif abstrait qui représente une relation de dépendance entre deux objets dans laquelle les données ou les métadonnées d'un objet dépendent des données ou des métadonnées d'un objet lié.|  
|[Type de données ClrAssembly &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md)|Définit un type de données dérivé qui représente un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assembly associé à un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) ou [Server](../../../analysis-services/scripting/objects/server-element-assl.md) élément|  
|[Type de données ClrAssemblyFile &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md)|Définit un type de données primitif qui représente un des fichiers qui composent un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assembly ([ClrAssembly](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md) élément).|  
|[Type de données ColumnBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/columnbinding-data-type-assl.md)|Définit un type de données dérivé qui représente la liaison d’une colonne dans une vue de source de données à un [DataItem](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md) élément.|  
|[Type de données ComAssembly &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/comassembly-data-type-assl.md)|Définit un type de données dérivé qui représente une bibliothèque COM associée à un [Server](../../../analysis-services/scripting/objects/server-element-assl.md) ou [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Type de données CubeAttribute &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubeattribute-data-type-assl.md)|Définit un type de données primitif qui représente un attribut associé avec un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Type de données CubeAttributeBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubeattributebinding-data-type-assl.md)|Définit un type de données dérivé représentant la liaison d'un attribut dans une dimension de cube à une colonne d'action ou à une colonne de la structure d'exploration de données.|  
|[Type de données CubeBinding &#40; hors ligne &#41; &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubebinding-data-type-out-of-line-assl.md)|Définit un type de données primitif qui représente la relation entre un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément et un [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) élément.|  
|[Type de données CubeDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md)|Définit un type de données primitif représentant la relation entre une dimension et un cube.|  
|[Type de données CubeDimensionBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubedimensionbinding-data-type-assl.md)|Définit un type de données dérivé qui représente la liaison d’un [Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md), [mesure](../../../analysis-services/scripting/objects/measure-element-assl.md), ou [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) élément à une dimension de cube.|  
|[Type de données CubeDimensionPermission &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubedimensionpermission-data-type-assl.md)|Définit un type de données primitif qui représente les autorisations d'un rôle unique dans une dimension spécifique au sein d'un cube.|  
|[Type de données CubeHierarchy &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubehierarchy-data-type-assl.md)|Définit un type de données primitif qui représente les informations concernant un [hiérarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) élément dans une [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Type de données DataBlock &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/datablock-data-type-assl.md)|Définit un type de données primitif qui représente une collection de blocs de données utilisé pour stocker le contenu binaire d’un [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) élément.|  
|[Type de données DataItem &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md)|Définit un type de données primitif qui représente les caractéristiques associées aux données d'un élément de données, tel qu'une colonne ou un attribut.|  
|[Type de données DataMiningMeasureGroupDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dataminingmeasuregroupdimension-data-type-assl.md)|Définit un type de données dérivé représentant la relation entre un groupe de mesures et une dimension d'exploration de données.|  
|[Type de données de la source de données &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/datasource-data-type-assl.md)|Définit un type de données primitif abstrait qui représente une source de données dans un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Type de données DataSourceViewBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/datasourceviewbinding-data-type-assl.md)|Définit un type de données dérivé représentant une liaison entre une vue de source de données et l'élément parent.|  
|[Type de données DegenerateMeasureGroupDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/degeneratemeasuregroupdimension-data-type-assl.md)|Définit un type de données dérivé représentant la relation entre une dimension dégénérée (soit, en définitif, une dimension) et un groupe de mesures.|  
|[Dimension de Type de données &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dimension-data-type-assl.md)|Définit un type de données primitif représentant une dimension de base de données.|  
|[Type de données DimensionAttribute &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md)|Définit un type de données primitif représentant un attribut dans une dimension.|  
|[Type de données DimensionBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dimensionbinding-data-type-assl.md)|Définit un type de données dérivé qui représente la liaison entre une source de données et un [Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md) élément.|  
|[Type de données DimensionPermission &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dimensionpermission-data-type-assl.md)|Définit un type de données dérivé représentant les autorisations attribuées à une dimension de base de données.|  
|[Type de données DrillThroughAction &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/drillthroughaction-data-type-assl.md)|Définit un type de données dérivé représentant une action d'extraction.|  
|[Type de données DSVTableBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dsvtablebinding-data-type-assl.md)|Définit un type de données dérivé qui représente la liaison entre une table et un [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) élément.|  
|[Type de données EventColumn &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/eventcolumn-data-type-assl.md)|Définit un type de données primitif qui représente une colonne d’informations à capturer pour un [événement](../../../analysis-services/scripting/objects/event-element-assl.md) élément dans le cadre d’un [Trace](../../../analysis-services/scripting/objects/trace-element-assl.md) élément.|  
|[Type de hiérarchie de données &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/hierarchy-data-type-assl.md)|Définit un type de données primitif représentant une hiérarchie dans une dimension.|  
|[Type de données ImpersonationInfo &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/impersonationinfo-data-type-assl.md)|Définit un type de données primitif fournissant des informations employées pour emprunter l'identité d'un utilisateur.|  
|[Type de données IncrementalProcessingNotification &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/incrementalprocessingnotification-data-type-assl.md)|Définit un type de données dérivé qui représente les informations pour le [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur une requête à exécuter pour déterminer la progression du traitement incrémentiel.|  
|[Type de données InheritedBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/inheritedbinding-data-type-assl.md)|Définit un type de données dérivé indiquant qu’un [MeasureGroupAttribute](../../../analysis-services/scripting/data-type/measuregroupattribute-data-type-assl.md) élément hérite ses liaisons de l’attribut.|  
|[Type de données ManyToManyMeasureGroupDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/manytomanymeasuregroupdimension-data-type-assl.md)|Définit un type de données dérivé représentant la relation entre une dimension plusieurs à plusieurs et un groupe de mesures.|  
|[Type de données MeasureBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measurebinding-data-type-assl.md)|Définit un type de données dérivé représentant la liaison d'une mesure à l'élément parent.|  
|[Type de données MeasureGroupAttribute &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupattribute-data-type-assl.md)|Définit un type de données primitif représentant la relation entre un attribut et un groupe de mesures.|  
|[Type de données MeasureGroupBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-assl.md)|Définit un type de données dérivé qui représente une liaison à un [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) élément.|  
|[Type de données MeasureGroupBinding &#40; hors ligne &#41; &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md)|Définit un type de données primitif représentant une liaison à un groupe de mesures.|  
|[Type de données MeasureGroupDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupdimension-data-type-assl.md)|Définit un type de données primitif abstrait représentant la relation entre une dimension et un groupe de mesures.|  
|[Type de données MeasureGroupDimensionBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupdimensionbinding-data-type-assl.md)|Définit un type de données dérivé représentant une liaison entre une dimension et un groupe de mesures.|  
|[Type de données MeasureGroupHierarchy &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregrouphierarchy-data-type-assl.md)|Définit un type de données primitif qui fournit des informations sur une hiérarchie dans un groupe de mesures.|  
|[Type de données MiningModelColumn &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/miningmodelcolumn-data-type-assl.md)|Définit un type de données primitif qui représente des informations sur une colonne dans un [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) élément.|  
|[Type de données MiningModelingFlag &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/miningmodelingflag-data-type-assl.md)|Définit un type de données primitif qui représente les indicateurs de modélisation pour une [ModelingFlag](../../../analysis-services/scripting/objects/modelingflag-element-assl.md) élément.|  
|[Type de données MiningStructureColumn &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md)|Définit un type de données primitif abstrait qui représente des informations sur une colonne dans un [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) élément.|  
|[Type de données OlapDataSource &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/olapdatasource-data-type-assl.md)|Définit un type de données dérivé qui représente un multidimensionnels [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) élément.|  
|[Type de données PartitionBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/partitionbinding-data-type-assl.md)|Définit un type de données dérivé qui représente une liaison à un [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) élément.|  
|[Type de données d’autorisation &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)|Définit un type de données primitif abstrait qui fournit des informations sur une autorisation individuelle.|  
|[Type de données PerspectiveAction &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectiveaction-data-type-assl.md)|Définit un type de données primitif qui fournit des informations sur une action dans un [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Type de données PerspectiveAttribute &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectiveattribute-data-type-assl.md)|Définit un type de données primitif qui représente des informations sur un attribut dans un [PerspectiveDimension](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md) élément.|  
|[Type de données PerspectiveCalculation &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivecalculation-data-type-assl.md)|Définit un type de données primitif qui représente la relation entre un calcul et une [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Type de données PerspectiveDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md)|Définit un type de données primitif qui fournit des informations sur une dimension dans une perspective.|  
|[Type de données PerspectiveHierarchy &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivehierarchy-data-type-assl.md)|Définit un type de données primitif qui représente des informations sur une hiérarchie dans un [PerspectiveDimension](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md) élément.|  
|[Type de données PerspectiveKpi &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivekpi-data-type-assl.md)|Définit un type de données primitif qui représente des informations sur l’indicateur de performance clé (KPI) dans un [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Type de données PerspectiveMeasure &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivemeasure-data-type-assl.md)|Définit un type de données primitif qui représente des informations sur une mesure dans un [PerspectiveMeasureGroup](../../../analysis-services/scripting/data-type/perspectivemeasuregroup-data-type-assl.md) élément.|  
|[Type de données PerspectiveMeasureGroup &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivemeasuregroup-data-type-assl.md)|Définit un type de données primitif qui représente des informations sur un groupe de mesures dans un [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Type de données ProactiveCachingBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingbinding-data-type-assl.md)|Définit un type de données dérivé abstrait qui représente les informations de la [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur les modifications de source de données qui exigent une reconstruction du cache, ou sur l’état du processus de reconstruction.|  
|[Type de données ProactiveCachingIncrementalProcessingBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingincrementalprocessingbinding-data-type-assl.md)|Définit un type de données dérivé qui représente une liaison à la [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur l’état du processus de reconstruction du cache.|  
|[Type de données ProactiveCachingInheritedBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachinginheritedbinding-data-type-assl.md)|Définit un type de données dérivé qui représente les informations de la [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur les modifications de source de données dans les tables et les vues identifiées par le biais des liaisons de données existantes qui exigent une reconstruction du cache.|  
|[Type de données ProactiveCachingObjectNotificationBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingobjectnotificationbinding-data-type-assl.md)|Définit un type de données dérivé abstrait qui représente les informations de la [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur les modifications de source de données, soit dans les tables et vues spécifiées dans les tables et les vues identifiées par le biais des données existantes liaisons qui exigent une reconstruction du cache.|  
|[Type de données ProactiveCachingQueryBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingquerybinding-data-type-assl.md)|Définit un type de données dérivé qui représente les informations de la [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur les modifications de source de données dans les tables et les vues identifiées lors de l’exécution des requêtes spécifiées qui exigent une reconstruction du cache.|  
|[Type de données ProactiveCachingTablesBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingtablesbinding-data-type-assl.md)|Définit un type de données dérivé qui représente les informations de la [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur les modifications de source de données dans les tables et vues qui exigent une reconstruction du cache spécifiées.|  
|[Type de données PushedDataSource &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/pusheddatasource-data-type-assl.md)|Définit un type de données primitif qui représente une source de données (comme un [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package) utilisé pour « pousser » des données dans un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Type de données QueryBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/querybinding-data-type-assl.md)|Définit un type de données dérivé qui représente l’association d’un [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) élément avec un [QueryDefinition](../../../analysis-services/scripting/properties/querydefinition-element-assl.md) élément.|  
|[Type de données ReferenceMeasureGroupDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/referencemeasuregroupdimension-data-type-assl.md)|Définit un type de données dérivé représentant une dimension indirectement liée à la table de faits par le biais d'une dimension intermédiaire. (Par exemple, un groupe de mesures Ventes peut référencer une dimension Géographie liée par le biais de la dimension Client.)|  
|[Type de données RegularMeasureGroupDimension &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/regularmeasuregroupdimension-data-type-assl.md)|Définit un type de données dérivé représentant une relation régulière entre une dimension et un groupe de mesures.|  
|[Type de données RelationalDataSource &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/relationaldatasource-data-type-assl.md)|Définit un type de données dérivé qui représente un [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) élément basé sur une source de données relationnelle.|  
|[Type de données ReportAction &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md)|Définit un type de données dérivé représentant une action qui génère un rapport [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].|  
|[Type de données RowBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/rowbinding-data-type-assl.md)|Définit un type de données dérivé qui représente une liaison aux lignes d’une table dans un [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) élément.|  
|[Type de données ScalarMiningStructureColumn &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md)|Définit un type de données dérivé qui représente un [MiningStructureColumn](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md) élément qui contient des valeurs scalaires, par opposition aux tables imbriquées associés à la [TableMiningStructureColumn](../../../analysis-services/scripting/data-type/tableminingstructurecolumn-data-type-assl.md) élément qui contient des tables imbriquées.|  
|[Type de données StandardAction &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/standardaction-data-type-assl.md)|Définit un type de données dérivé représentant tous les éléments [Action](../../../analysis-services/scripting/objects/action-element-assl.md) éléments autres qu’un [DrillThroughAction](../../../analysis-services/scripting/data-type/drillthroughaction-data-type-assl.md) élément ou un [ReportAction](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md) élément.|  
|[Type de données TableBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/tablebinding-data-type-assl.md)|Définit un type de données dérivé représentant une liaison à une table.|  
|[Type de données TableMiningStructureColumn &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/tableminingstructurecolumn-data-type-assl.md)|Définit un type de données dérivé qui représente un [MiningStructureColumn](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md) élément qui contient des tables imbriquées, par opposition aux valeurs scalaires associées à la [ScalarMiningStructureColumn](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md) élément qui contient des valeurs scalaires.|  
|[Type de données TabularBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/tabularbinding-data-type-assl.md)|Définit un type de données dérivé abstrait représentant une liaison à un élément tabulaire, tel qu'une table ou une dimension de cube.|  
|[Type de données TimeAttributeBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/timeattributebinding-data-type-assl.md)|Définit un type de données dérivé représentant une liaison d'espace réservé pour les éléments de données créés dans une dimension de temps du serveur, tels que les colonnes clés d'un attribut.|  
|[Type de données TimeBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/timebinding-data-type-assl.md)|Définit un type de données dérivé représentant une liaison à des périodes.|  
|[Type de données Translation &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/translation-data-type-assl.md)|Définit un type de données primitif représentant une traduction localisée.|  
|[Type de données UserDefinedGroupBinding &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/userdefinedgroupbinding-data-type-assl.md)|Définit un type de données dérivé représentant un groupement défini par l'utilisateur pour un attribut.|  
  
## <a name="see-also"></a>Voir aussi  
 [Analysis Services Scripting Language hiérarchie des éléments XML &#40; ASSL &#41;](../../../analysis-services/scripting/analysis-services-scripting-language-xml-element-hierarchy-assl.md)  
  
  