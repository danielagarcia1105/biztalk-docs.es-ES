---
title: "Emitir y canjear un vale de inicio de sesión único | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0323a6-cc31-460d-b64d-b4d8142c3855
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9988eedb545b3b1a348a5de6275b176abe2be7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a>Emitir y canjear un vale de inicio de sesión único
Después de vincular a un usuario con una aplicación afiliada, puede emitir vales para ayudar a garantizar la seguridad durante las comunicaciones. Single Sign-On vales funciona igual que otras tecnologías de control de vales: antes de enviar el mensaje de, anexe el vale de inicio de sesión único para el mensaje como una cadena. El servidor recibe el mensaje, descodifica el vale y utiliza la información como corresponda.  
  
### <a name="to-issue-a-single-sign-on-ticket"></a>Para emitir un vale de inicio de sesión único  
  
1.  Crear un nuevo objeto de vale con una llamada a I`SSOTicket`.  
  
2.  Emita el vale con una llamada a I`SSOTicket.IssueTicket`.  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a>Para canjear un vale de inicio de sesión único  
  
1.  Crear un nuevo objeto de vale con una llamada a I`SSOTicket`.  
  
2.  Canjee el vale con una llamada a I`SSOTicket.RedeemTicket`.  
  
## <a name="see-also"></a>Vea también  
 [Programar con Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md)