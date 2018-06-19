---
title: Archivo de adaptador FileAct e identificación de transferencia | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a9aaff1-8816-42cf-b100-fedf964caaf5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5340f9ad739009ff1cb1257365ceeeb7459511a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223156"
---
# <a name="fileact-adapter-file-and-transfer-identification"></a>Archivo de adaptador FileAct e identificación de transferencia
El adaptador de FileAct de A4SWIFT permite al desarrollador proporcionar detalles de identificación de archivo y la transferencia en tiempo de ejecución. Estos parámetros incluyen lo siguiente:  
  
-   **Nombre de archivo físico** : la ruta de acceso completa y el nombre del archivo que se pueden leer o escribir. Este parámetro nunca se pase y es local para el componente de controlador de archivo.  
  
-   **Nombre de archivo lógico** : el nombre de archivo que se pasa desde la aplicación de envío a la aplicación receptora a través de SWIFTNet. Esto es opcional y, si no se proporciona, se utiliza el nombre de archivo físico sin la ruta de acceso.  
  
-   **Punto de conexión del evento de transferencia de archivo** : el nombre especificado en el evento suscribirse primitivos por la aplicación que controla los eventos de transferencia de archivos. Este parámetro vincula la transferencia de archivos a la aplicación que recibe los informes de eventos.  
  
-   **Referencia de transferencia de archivos** : una cadena de token creado y utilizado por el subsistema de FileAct como un identificador en la transferencia, sí. Esto es simplemente una cadena única para esta transferencia, tal y como lo que se refiere el adaptador de FileAct.  
  
-   **Transferir la clave** : una cadena asignada por la aplicación para identificar la transferencia para anular fines. Si no proporciona la aplicación, este es el GUID asociado al archivo.  
  
-   **Transferencia de partición** : una cadena que se utiliza para relacionar varias transferencias. Si no se proporciona en las llamadas realizadas por el desarrollador, esto se el "nombre de aplicación" especificado cuando se definió el envío relevante o ubicación de recepción.  
  
-   **Referencia de usuario** : una cadena definida por la aplicación para identificar de forma exclusiva la transferencia para sin repudio. Si no proporciona la aplicación, este es el GUID asociado al archivo.  
  
-   **Id. de mensaje** : el identificador de definición de forma única la solicitud inicial o la respuesta. Este es el GUID asociado a la solicitud adecuada o el mensaje de respuesta, como las generadas por el adaptador de envío. Por lo tanto, el cliente genera el identificador de mensaje para las solicitudes y el servidor lo hace para las respuestas.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [Almacenamiento de adaptador FileAct y reenvío](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [Transferencia de información de soporte de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [Estado del adaptador de FileAct supervisión](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)