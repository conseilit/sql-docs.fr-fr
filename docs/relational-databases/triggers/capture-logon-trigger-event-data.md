---
title: "Capturer des données d’événement de déclencheur de connexion | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e05b1ab4-c10b-402a-9591-f6ec1e3db8c0
caps.latest.revision: 5
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 790a086c90eeeeb606a86056f239853d805cb091
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="capture-logon-trigger-event-data"></a>Capturer des données d'événements de déclencheurs de connexion
  Pour capturer des données XML relatives à des événements LOGON à utiliser dans des déclencheurs de connexion, utilisez la fonction [EVENTDATA](../../t-sql/functions/eventdata-transact-sql.md) . L'événement LOGON retourne le schéma des données d'événement suivant :  
  
 `<EVENT_INSTANCE>`  
  
 `<EventType>event_type</EventType>`  
  
 `<PostTime>post_time</PostTime>`  
  
 `<SPID>spid</SPID>`  
  
 `<ServerName>server_name</ServerName>`  
  
 `<LoginName>login_name</LoginName>`  
  
 `<LoginType>login_type</LoginType>`  
  
 `<SID>sid</SID>`  
  
 `<ClientHost>client_host</ClientHost>`  
  
 `<IsPooled>is_pooled</IsPooled>`  
  
 `</EVENT_INSTANCE>`  
  
 `<EventType>`  
 Contient `LOGON`.  
  
 `<PostTime>`  
 Contient l'heure de demande d'établissement d'une session.  
  
 `<SID>`  
 Contient le flux binaire encodé en base 64 du numéro d'identification de sécurité (SID) correspondant au nom de connexion spécifié.  
  
 `<ClientHost>`  
 Contient le nom d'hôte du client à partir duquel a été établie la connexion. La valeur est '`<local_machine>`' si le nom du serveur et du client sont identiques. Sinon, la valeur est l'adresse IP du client.  
  
 `<IsPooled>`  
 Valeur égale à `1` si la connexion est réutilisée à l'aide du groupement de connexions. Sinon, la valeur est `0`.  
  
  