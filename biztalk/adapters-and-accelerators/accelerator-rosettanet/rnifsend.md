---
title: RNIFSend | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 780f7446-56c5-40bf-95e2-25d0cff12f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73cf8a832e495944ce7c891421645ae2566e3575
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963409"
---
# <a name="rnifsend"></a>RNIFSend
Este ejemplo proporciona un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] archivo RNIFSend.aspx que prepara un mensaje para el procesamiento de RNIF y envía el mensaje a la página de trabajo RNIFReceive.aspx en el servicio de respuesta. Puede personalizar la página ASPX para hacer lo siguiente:  
  
-   Agregar o quitar los contadores de rendimiento  
  
-   Agregar funciones a la página, como escribir datos en una base de datos o personalizar la función de seguimiento  
  
-   Agregar validación a la página  
  
 Este ejemplo se encuentra en  *\<unidad\>*: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\WebApplication\RNIFSender.  
  
## <a name="demonstrates"></a>Demostraciones  
 Este ejemplo muestra cómo preparar los mensajes salientes para RNIF de procesamiento, como los siguientes:  
  
-   Validación de los datos para el encabezado MIME  
  
-   Agregar un encabezado MIME y límites MIME para el mensaje  
  
-   Enviar el mensaje al RNIFReceive.aspx del asociado  
  
-   Procesar un mensaje de señal devuelto  
  
## <a name="see-also"></a>Vea también  
 [Enviar y recibir páginas ASPX](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Ejemplos de aplicaciones web](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)