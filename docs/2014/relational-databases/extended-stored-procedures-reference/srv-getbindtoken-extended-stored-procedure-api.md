---
title: srv_getbindtoken (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
api_name:
- srv_getbindtoken
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_getbindtoken
ms.assetid: c947d011-08ac-4fb8-b925-3da6e0999277
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: f9904127d1d685b79efd56475a508c500cd317ec
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48062293"
---
# <a name="srvgetbindtoken-extended-stored-procedure-api"></a>srv_getbindtoken (API de procédure stockée étendue)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Utilisez l’intégration CLR à la place.  
  
 Obtient un jeton de liaison de la transaction dans la session cliente actuelle qui appelle la procédure stockée étendue.  
  
 La procédure stockée étendue peut utiliser ensuite **sp_bindsession** pour lier toute nouvelle session qu’elle crée sur le même serveur à la transaction existante, afin que la nouvelle session puisse partager le même espace de verrouillage de transaction avec la session cliente qui a appelé la procédure stockée étendue.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
int srv_getbindtoken (  
SRV_PROC*  
srvproc  
,  
char*  
bindtoken  
);  
  
```  
  
## <a name="arguments"></a>Arguments  
 *srvproc*  
 Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière. La structure contient toutes les informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.  
  
 *bindtoken*  
 Pointeur vers une mémoire tampon où le jeton de liaison sera copié. Le jeton de liaison est représenté sous la forme d'une chaîne terminée par le caractère NULL. La mémoire tampon que vous spécifiez doit avoir une longueur minimale de 255 octets.  
  
## <a name="returns"></a>Valeur renvoyée  
 SUCCEED ou FAIL.  
  
## <a name="remarks"></a>Notes  
  
### <a name="to-bind-an-extended-stored-procedure-session-to-the-client-session-that-called-it-so-they-share-the-same-transaction-lock-space"></a>Pour lier une session de procédure stockée étendue à la session cliente qui l'a appelée pour qu'elles partagent le même espace de verrouillage de transaction  
  
1.  La procédure stockée étendue appelle **svr_getbindtoken** pour obtenir le jeton de liaison pour la transaction en cours dans la session. Le jeton est retourné dans le paramètre *bindtoken* donné.  
  
2.  La procédure stockée étendue ouvre une ou de nouvelles sessions sur le même serveur. Au sein de cette session, la procédure stockée étendue utilise le jeton de liaison avec **sp_bindsession** pour lier la nouvelle session à la même transaction. La procédure stockée étendue peut créer plusieurs sessions et lier toutes les sessions à la même transaction.  
  
3.  Une session liée est détachée quand la procédure stockée externe retourne une chaîne vide ou quand **sp_bindsession** est appelé avec une chaîne vide.  
  
    > [!NOTE]  
    >  Une seule session liée peut avoir accès à une connexion partagée à la fois. Si une session exécute une instruction côté serveur ou si elle attend des résultats du serveur, aucune autre session partageant la même connexion liée ne peut accéder au serveur tant que la session active n'a pas fini d'exécuter l'instruction en cours. Si une session essaie d'accéder à la connexion pendant que le serveur est occupé, une erreur est retournée à la session en conflit, qui indique que la connexion est en cours d'utilisation et que la session doit réessayer ultérieurement.  
  
> [!IMPORTANT]  
>  Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production. Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
## <a name="see-also"></a>Voir aussi  
 [sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql)   
 [sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql)  
  
  
