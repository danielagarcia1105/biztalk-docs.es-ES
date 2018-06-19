---
title: Primitivos locales de FileAct adaptador en tiempo real | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef4da4f8-3de2-4d35-8f8a-1e12937e52a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcc0f1d093d56b8cd4580ef068007d02aab6346f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223076"
---
# <a name="fileact-adapter-real-time-local-primitives"></a>Primitivos locales de FileAct adaptador en tiempo real
Primitivos locales implican dos mensajes de cada uno, que se intercambian entre el cliente SWIFTNet vínculo (SNL) y el subsistema de FileAct local.  
  
 La siguiente ilustración muestra a las primitivas locales de FileAct.  
  
 ![Primitivos locales de FileAct](../../adapters-and-accelerators/fileact-interact/media/67ca0c3b-3c81-401d-87cb-473c68cae63f.gif "67ca0c3b-3c81-401d-87cb-473c68cae63f")  
  
## <a name="get-status-for-a-single-transfer"></a>Obtener el estado de una transferencia única  
 Obtener estado de primitivos recupera información de estado relacionados con las transferencias desde el contexto local persistente.  
  
## <a name="subscribe-to-transfer-events"></a>Suscribirse para transferir eventos  
 Información de estado de transferencia progresiva se reciba en forma de evento al evento utilizando la primitiva eventos suscribirse. Cada transferencia de archivos se puede vincular a una entidad con nombre que se llama a un punto de conexión de eventos durante la negociación. Un servidor de eventos que invoca la primitiva eventos suscribirse dirige todos los informes de eventos para un tal un extremo de eventos a sí mismo.  
  
 Un servidor de eventos puede suscribirse a características (diferentes niveles de detalle, así como a los tipos de evento diferente).  
  
 Un servidor de eventos puede invocar varias veces la primitiva para suscribirse a varios puntos de conexión de eventos. Servidor de un solo evento puede suscribirse a cualquier punto de conexión de evento determinado en un momento dado. Además, un servidor de eventos puede invocar a la primitiva varias veces para el mismo extremo de evento para cambiar las características.  
  
## <a name="receive-transfer-events"></a>Recibir eventos de transferencia  
 Recibir eventos de transferencia es el tipo primitivo que controla la información de estado de evento por evento relativas a las transferencias en curso. Responda a las condiciones de una suscripción que se configura con el evento suscribirse primitivo. Esta primitiva se puede implementar en el lado envío o recepción de una transferencia.  
  
## <a name="abort-transfer"></a>Anular la transferencia  
 Una aplicación de usuario puede anular una transferencia en curso utilizando la primitiva Abort. El tipo primitivo anulación es una primitiva que puede realizarse desde el lado de envío o en el lado de recepción de una transferencia en curso. Cuando se inicie o Aceptar a una transferencia, cada lado tiene la opción de establecer una clave de transferencia que actúa como una tecla de acceso para proteger esa transferencia de su parte. Si se establece una clave de transferencia para una transferencia en curso, se puede no anularse desde ese lado sin proporcionar el valor de clave de transferencia en el ejercicio de la primitiva Abort.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [Almacenamiento de adaptador FileAct y reenvío](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [Transferencia de información de soporte de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [Estado del adaptador de FileAct supervisión](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)