---
title: "Méthode getBytes (int) | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerCallableStatement.getBytes (int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 8c2973e6-d57f-4f64-b812-350ce4098ce6
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: a7cfbc1875deed8a4949a89f6a34ff8f666ef5cf
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="getbytes-method-int"></a>Méthode getBytes (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère la valeur du paramètre désigné en tant que valeur de tableau d'octets en fonction de l'index de paramètre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public byte[] getBytes(int index)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *index*  
  
 Un **int** qui indique l’index de paramètre.  
  
## <a name="return-value"></a>Valeur retournée  
 Un tableau de **octets** valeurs.  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Dans une version antérieure de [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)], vous pouviez utiliser SQLServerCallableStatement.getBytes pour convertir des valeurs entre des tableaux d’octets et [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] type de données **date**, **temps**, ** datetime2**, ou **datetimeoffset**. À présent, l'utilisation de cette méthode avec ces types de données lève une exception indiquant que la conversion n'est pas prise en charge.  
  
 Cette méthode getBytes est spécifiée par la méthode getBytes dans l’interface java.sql.CallableStatement.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode getBytes &#40; SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/getbytes-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement, classe](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  