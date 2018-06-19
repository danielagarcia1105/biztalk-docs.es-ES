---
title: RNIFReceive | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf1253b0-ceca-4e7a-91ed-3837bd904472
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57af8140157b901d7e6265fc26249c7fbfef0c46
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963882"
---
# <a name="rnifreceive"></a>RNIFReceive
Este ejemplo proporciona un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx archivo que recibe un mensaje RNIF y se prepara para que lo procese la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proceso público. Puede personalizar la página ASPX para hacer lo siguiente:  
  
-   Agregar o quitar los contadores de rendimiento  
  
-   Agregar funciones a la página, como escribir datos en una base de datos o personalizar la función de seguimiento  
  
-   Agregar validación a la página  
  
 Este ejemplo se encuentra en  *\<unidad\>*: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\WebApplication\RNIFReceiver.  
  
## <a name="demonstrates"></a>Demostraciones  
 Este ejemplo muestra cómo preparar los mensajes entrantes para el proceso público, incluidos los siguientes pasos:  
  
-   Recibir el mensaje del RNIFSend.aspx del asociado  
  
-   Validar el encabezado MIME  
  
-   Quitar el encabezado MIME y los límites del mensaje  
  
-   Redirigir el mensaje al RNIFReceive.aspx del asociado  
  
-   Devolver un mensaje de señal  
  
## <a name="see-also"></a>Vea también  
 [Enviar y recibir páginas ASPX](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Ejemplos de aplicaciones web](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)