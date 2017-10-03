---
title: "Cómo funciona el ejemplo del controlador NAK FRR | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f11bd20-3a0e-4d96-8e0a-32fecc7eed7e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009cb0c3dffce5f88c72207866f6778e3deb7b28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-frr-nak-handler-sample-works"></a>Cómo funciona el ejemplo del controlador FRR NAK
El ejemplo de controlador personalizado FRR NAK actúa como intermediario entre la orquestación de conciliación de respuesta de FIN (FRR) y la orquestación de reparación de mensajes. La orquestación FRR identifica el error que se produjo al intentar realizar la red SWIFT recibir el mensaje. El resultado de la orquestación FRR es un mensaje de una parte con un objeto de error. El controlador personalizado FRR NAK transforma ese mensaje en un mensaje de dos partes, con una parte de error que indica el error que se ha producido, permitir al mensaje ser recogidas por la orquestación de reparación de mensajes. La orquestación de reparación de mensajes, abre el mensaje en una [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario que le permite averiguar cuál fue el error, repare el mensaje en consecuencia y reenviarlo, por lo que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puede enviarlo a AAS.  
  
 Cuando el controlador personalizado FRR NAK procesa un mensaje que la red SWIFT no pudo recibir correctamente, se producen los pasos siguientes:  
  
1.  Después de la orquestación FRR ha correlacionado el mensaje con errores al mensaje MTS21_FIN_ACKNAK NAK, la orquestación RepairSWIFTRejectedMessage (el controlador personalizado) recoge el mensaje original desde el cuadro de mensajes. Por lo que porque filtra en A4SWIFT_FRRFailed == True y A4SWIFT_SendingServiceType = "A4SWIFT_FrrService".  
  
2.  El controlador personalizado no recoge el mensaje de MTS21_FIN_ACKNAK NAK FRR correlacionado con el mensaje original. En su lugar, crea un objeto de colección de errores, se rellena con un error de validación del BRE que indica lo que la propiedad A4SWIFT_FRRFailedReason y lo agrega al mensaje original. La orquestación de reparación de mensajes puede procesar este mensaje de dos partes.  
  
3.  El controlador personalizado promociona las siguientes propiedades para hacer que el mensaje ser recogidas por la orquestación de reparación de mensajes: A4SWIFT_Failed == True, A4SWIFT_SwiftBound == True y BTS. Operación = "A4SWIFT_DASMMarkedAsFailed". El número de partes de la propiedad se establece en 2 y establece las propiedades de error adecuado.  
  
4.  Como resultado de las propiedades promocionadas, la reparación de mensajes de orquestación recoge el mensaje y se interrumpe la orquestación RepairSWIFTRejectedMessage.