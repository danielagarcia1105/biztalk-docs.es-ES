---
title: Estado del adaptador de FileAct supervisión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 15833004-4276-4975-a0e7-8fff3c82576b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5b717a02631d47b864cc9180cba2fba673c5da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223044"
---
# <a name="fileact-adapter-status-monitoring"></a>Estado del adaptador de FileAct supervisión
Los Estados posibles de una transferencia de archivos y las transiciones entre los Estados se ilustran en la ilustración siguiente.  
  
 ![Estados de transferencia de archivo de adaptador FileAct](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")  
  
 Los Estados de transferencia de archivo son:  
  
-   **Inicia** : el cliente ha enviado el mensaje de negociación con el servidor, pero aún no ha recibido la respuesta. El servidor ha recibido la solicitud de negociación, pero no ha enviado la respuesta.  
  
-   **Acepta** : el servidor ha aceptado la solicitud y ha enviado el TransferAnswer en el mensaje de respuesta, y la transferencia aún está en curso.  
  
-   **Rechazado** : el servidor ha rechazado la solicitud y tiene la TransferAnswer en el mensaje de respuesta y ha finalizado la transferencia.  
  
-   **En curso** : la transferencia está en curso y se está realizando (renovado periódicamente como anteriormente).  
  
-   **Completado** : la transferencia de archivos se completó correctamente en lo que se refiere esa parte de la transferencia, incluida la comparación del valor de síntesis.  
  
-   **No se pudo** : la transferencia de archivos ha fallado por un acceso a los datos, procesar, excepción de comunicaciones o tiempo de espera. (Nota: SWIFTNet vínculo exige el tiempo de espera y el valor se determina mediante SWIFT).  
  
-   **Se anuló** : se ha anulado la transferencia de archivos (ya sea en paralelo mi problema la instrucción abort).  
  
-   **Desconocido y duplicados** : este estado se produce solo debido a tiempo. En el caso de un remitente, el archivo debe ser vuelven a enviar marcado como posiblemente duplicado (PDIndicator). En el caso de un receptor, cuando la PDIndicator implica que el archivo podría haber ya se han enviado, el adaptador de FileAct comprobará la duplicación y si se encuentra, se devolverá un TransferAnswer de duplicados, que finalizará el intento actual.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [Almacenamiento de adaptador FileAct y reenvío](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [Transferencia de información de soporte de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)