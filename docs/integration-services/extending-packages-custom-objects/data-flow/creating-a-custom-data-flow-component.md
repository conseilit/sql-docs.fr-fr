---
title: "Création d’un composant de flux de données personnalisé | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- design-time component interface [Integration Services]
- custom data flow components [Integration Services], about data flow components
- custom data flow components [Integration Services]
- data flow components [Integration Services]
- data flow components [Integration Services], developing
ms.assetid: 9d96bcf5-eba8-44bd-b113-ed51ad0d0521
caps.latest.revision: 28
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 565a2b8e48537cea20a8e509cf5b6d7b59cc12f0
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="creating-a-custom-data-flow-component"></a>Création d'un composant de flux de données personnalisé
  Dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], la tâche de flux de données expose un modèle objet qui permet aux développeurs de créer des composants de flux de données personnalisé, sources, transformations et destinations, à l’aide de la [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] et du code managé.  
  
 Une tâche de flux de données comprend des composants qui contiennent une interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> et une collection d'objets <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> qui définissent le déplacement de données entre les composants.  
  
> [!NOTE]  
>  Lorsque vous créez un fournisseur personnalisé, vous devez mettre à jour le dossier ProviderDescriptors.xml avec les valeurs de la colonne de métadonnées.  
  
## <a name="design-time-and-run-time"></a>Moment de la conception et moment de l'exécution  
 Avant l'exécution, la tâche de flux de données est dite au moment de la conception, puisqu'elle subit des modifications incrémentielles. Les modifications peuvent inclure l'ajout ou la suppression de composants, l'ajout ou la suppression d'objets de chemin d'accès qui connectent des composants, ainsi que des modifications apportées aux métadonnées des composants. Lorsque des modifications de métadonnées se produisent, le composant peut les surveiller et y réagir. Par exemple, un composant peut rejeter certaines modifications ou apporter des modifications supplémentaires en réponse à une modification. Au moment de la conception, le concepteur interagit avec un composant via l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> du moment de la conception.  
  
 Au moment de l'exécution, la tâche de flux de données examine la séquence de composants, prépare un plan d'exécution et gère un pool de threads de travail qui exécute le plan de travail. Bien que chaque thread de travail effectue un travail qui est interne à la tâche de flux de données, la tâche principale du thread de travail consiste à appeler les méthodes du composant via l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> du moment de l'exécution.  
  
## <a name="creating-a-component"></a>Création d'un composant  
 Pour créer un composant de flux de données, vous dérivez une classe de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>, vous appliquez la classe <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>, puis vous remplacez les méthodes appropriées de la classe de base. L'objet <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implémente les interfaces <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> et <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100>, puis expose leurs méthodes pour que vous les remplaciez dans votre composant.  
  
 Selon les objets utilisés par votre composant, votre projet requerra des références à une partie ou la totalité des assemblys suivants :  
  
|Fonctionnalité|Assembly à référencer|Espace de noms à importer|  
|-------------|---------------------------|-------------------------|  
|Flux de données|Microsoft.SqlServer.PipelineHost|<xref:Microsoft.SqlServer.Dts.Pipeline>|  
|Wrapper de flux de données|Microsoft.SqlServer.DTSPipelineWrap|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>|  
|Runtime|Microsoft.SQLServer.ManagedDTS|<xref:Microsoft.SqlServer.Dts.Runtime>|  
|Wrapper d'exécution|Microsoft.SqlServer.DTSRuntimeWrap|<xref:Microsoft.SqlServer.Dts.Runtime.Wrapper>|  
  
 L'exemple de code suivant montre un composant simple dérivé de la classe de base, puis applique l'objet <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>. Vous devez ajouter une référence à l’assembly Microsoft.SqlServer.DTSPipelineWrap.  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SampleComponent", ComponentType = ComponentType.Transform )]  
    public class BasicComponent: PipelineComponent  
    {  
        // TODO: Override the base class methods.  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(DisplayName:="SampleComponent", ComponentType:=ComponentType.Transform)> _  
Public Class BasicComponent  
  
    Inherits PipelineComponent  
  
    ' TODO: Override the base class methods.  
  
End Class  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Développement d’une Interface utilisateur pour un composant de flux de données](../../../integration-services/extending-packages-custom-objects/data-flow/developing-a-user-interface-for-a-data-flow-component.md)  
  
  