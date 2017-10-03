---
title: "TIBCO Rendezvous eventos y ubicaciones de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive locations, life cycle
ms.assetid: 3576af82-4723-4efc-961e-40b1150cf13d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9278687ff212fc2368eca138780417d7c052824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a>TIBCO Rendezvous eventos y ubicaciones de recepción
Cualquier sistema TIBCO Rendezvous puede enviar mensajes a su nombre de asunto de elección. El concepto de *eventos* es la generación de mensajes de otros programas de TIBCO Rendezvous.  
  
 En los pasos siguientes se describe el ciclo de vida de una ubicación de recepción:  
  
1.  Se crea la ubicación de recepción.  
  
2.  La ubicación de recepción se asocia con un host.  
  
3.  La ubicación de recepción se enlaza con una orquestación.  
  
4.  La ubicación de recepción se habilita.  
  
5.  La ubicación de recepción recibe mensajes.  
  
> [!IMPORTANT]
>  Cada ubicación de recepción debe tener un nombre único. Dos ubicaciones de recepción no pueden tener el mismo nombre en la misma implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!IMPORTANT]
>  Asimismo, conviene establecer listas de control de acceso (ACL) seguras en las ubicaciones de destino de las ubicaciones de recepción. Por ejemplo, debe establecer listas ACL seguras para el directorio desde el que la ubicación de recepción de archivos toma los mensajes, de modo que solo los usuarios autorizados puedan entregar mensajes en esta ubicación.  
  
## <a name="see-also"></a>Vea también  
 [Controladores de recepción de creación TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)