---
title: Clés symétriques sur les bases de données utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3333ab5b-2518-4753-a0a8-57df5e5af74f
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 213ae962f1dbc45d9e6fc2bed67c94f2eafb1183
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47601737"
---
# <a name="symmetric-keys-on-user-databases"></a>Clés symétriques sur les bases de données utilisateur
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Cette règle vérifie que les clés dont la longueur est inférieure à 128 octets n'utilisent pas l'algorithme de chiffrement RC2 ou RC4.  
  
## <a name="best-practices-recommendations"></a>Meilleures pratiques recommandées  
 Utilisez AES 128 bits ou supérieur pour créer des clés symétriques pour le chiffrement de données. Si AES n'est pas pris en charge par votre système d'exploitation, utilisez 3DES.  
  
## <a name="for-more-information"></a>Pour plus d'informations  
 [Choisir un algorithme de chiffrement](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md)  
  
## <a name="see-also"></a> Voir aussi  
 [Contrôler et appliquer les meilleures pratiques à l'aide de la Gestion basée sur des stratégies](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
