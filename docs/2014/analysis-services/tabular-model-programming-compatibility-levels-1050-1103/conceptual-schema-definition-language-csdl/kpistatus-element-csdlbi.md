---
title: Élément KpiStatus (CSDLBI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
ms.assetid: 6fee5b82-caa8-46a1-ad68-bbce3e11e01e
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: ab554d47678b336ebfa763a7f3bd05f027e92945
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48164539"
---
# <a name="kpistatus-element-csdlbi"></a>Élément KpiStatus (CSDLBI)
  L'élément KpiStatus définit une référence à la colonne qui contient la valeur utilisée comme un indicateur d'état dans un indicateur de performance clé (KPI).  
  
## <a name="elements-and-attributes"></a>Éléments et attributs  
 Le tableau suivant répertorie les éléments et les attributs qui définissent l'élément KpiStatus.  
  
|Nom   |Est obligatoire|Description|  
|----------|-----------------|-----------------|  
|PropertyRef|Oui|Référence à une colonne qui contient la valeur utilisée comme un indicateur d'état dans un indicateur de performance clé (KPI).<br /><br /> Cet élément DOIT contenir exactement une référence de colonne, tel que le définit le type TPropertyRefComplex.|  
  
## <a name="example"></a>Exemple  
 **Tabulaire**  
  
 L'exemple suivant, en CSDLBI version 1.1, illustre un indicateur de performance clé de l'exemple de modèle tabulaire AdventureWorks. L'élément KpiStatus fait référence à une colonne (représentée en tant que PropertyRef) qui contient la valeur.  
  
```  
  
<Property Name="InternetCurrSalesPerf" Type="Double">  
   <bi:Measure>  
     <bi:Kpi StatusGraphic="Three Stars Colored">  
       <bi:KpiGoal>  
         <bi:PropertyRef Name="v_InternetCurrSalesPerf_Goal" />  
       </bi:KpiGoal>  
       <bi:KpiStatus>  
         <bi:PropertyRef Name="v_InternetCurrSalesPerf_Status" />  
       </bi:KpiStatus>  
     </bi:Kpi>  
   </bi:Measure>  
</Property>  
  
```  
  
## <a name="example"></a>Exemple  
 **(Multidimensionnel)**  
  
 L'exemple suivant, en CSDLBI version 1.1, illustre un indicateur de performance clé du cube Contoso Operations. L'élément KpiStatus référence une mesure qui calcule la valeur de l'état de l'indicateur de performance clé (KPI).  
  
```  
<bi:Measure   
       Caption="Sum of SalesAmount"   
       ReferenceName="Sum of SalesAmount"   
       FormatString="\$#,0.00;(\$#,0.00);\$#,0.00">  
  
    <bi:Kpi   
       StatusGraphic="Three Circles Colored">  
  
      <bi:KpiGoal>  
         <bi:PropertyRef   
          Name="v_Sum_of_SalesAmount_Goal" />  
       </bi:KpiGoal>  
  
       <bi:KpiStatus>  
          <bi:PropertyRef   
          Name="v_Sum_of_SalesAmount_Status" />  
        </bi:KpiStatus>  
  
       </bi:Kpi>  
</bi:Measure>  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Élément KPI &#40;CSDLBI&#41;](kpi-element-csdlbi.md)  
  
  
