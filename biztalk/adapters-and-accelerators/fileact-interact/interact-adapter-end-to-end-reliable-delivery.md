---
title: Entrega confiable de adaptador-to-End de interactuar | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac7c22f2-ee4a-4e9b-af40-da7eb58daf51
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ca0fc7ae5872598ed9a61cd7541017a6a39667
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222996"
---
# <a name="interact-adapter-end-to-end-reliable-delivery"></a>Interactuar entrega confiable de adaptador-to-End
Al enviar mensajes o archivos a un destinatario, se recomienda que se asegure de que se entrega el mensaje o el archivo y que la empresa transacciones contenidas en estas se ejecutan no veces más que prever.  
  
 Cuando ambas entidades que se comunican entre sí pueden usar un almacenamiento persistente (por ejemplo, proporcionada por un middleware orientado a mensajes persistente y una aplicación de interfaz con él), resulta fácil de implementar una entrega confiable si el modo de comunicarse el está normalizado percibido estado del mensaje.  
  
 En la siguiente ilustración muestra un ejemplo de la estructura de la E2EControl.  
  
 ![Terminar &#45; a &#45; control final](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")  
  
 El elemento en el ejemplo que se muestra en la ilustración se envía dentro de la SwInt:Request y entregan sin cambios en la SwInt:RequestHandle a la aplicación receptora. Línea 02 permite asignar un identificador único para la solicitud. Este identificador único se repite en cada retransmisión posterior de la misma solicitud.  
  
 La manera de construir este identificador se deja para el implementador, pero normalmente se basa en una llamada del sistema, como uuidgen() o puede ser el resultado de calcular un SHA-1 en el que se envíe la solicitud (con un Sw:MsgId con prefijo y reemplace; para ello base64 codificado s SHA-1 String). El requisito principal es que es único globalmente (con una probabilidad muy alta).  
  
 El Sw:CreationTime es el momento de creación de la solicitud original. Es un parámetro opcional, pero resulta útil limitar la eventual busca los intentos de comunicación anterior de este mensaje.  
  
 El elemento Sw:PDIndication está presente para indicar que se trata de un segundo o más intento de transmitir el mensaje. La aplicación receptora que conoce el E2EControl, a continuación, puede usar el Sw:MsgId para buscar de nuevo si se ha recibido el mensaje o no. El Sw:EmissionList opcional contiene la hora de los intentos anteriores. Este tiempo es la hora local del remitente (en hora universal) ya que se obtuvo el remitente cuando se usa la función Sw:GetDateTime. Nuevo Esto puede resultar útil para limitar las búsquedas.  
  
## <a name="see-also"></a>Vea también  
 [Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Interactuar mensajes del adaptador para el intercambio de negocios](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [Interactuar sin repudio de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)