---
title: RNIFSend | Microsoft Docs
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
ms.openlocfilehash: 0d9aca64afee9ed979b2eee58a5f2bdafb25b461
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011605"
---
# <a name="rnifsend"></a>RNIFSend
Este ejemplo proporciona un Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] archivo RNIFSend.aspx que prepara un mensaje para el procesamiento de RNIF y envía el mensaje a la página de trabajo RNIFReceive.aspx en el servicio de respuesta. Puede personalizar la página ASPX para hacer lo siguiente:  
  
- Agregar o quitar los contadores de rendimiento  
  
- Agregar funciones a la página, como escribir datos en una base de datos o personalizar la función de seguimiento  
  
- Agregar validación a la página  
  
  Este ejemplo se encuentra en  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\WebApplication\RNIFSender.  
  
## <a name="demonstrates"></a>Demostraciones  
 Este ejemplo muestra cómo preparar los mensajes salientes para RNIF procesar, incluido lo siguiente:  
  
-   Validación de los datos para el encabezado MIME  
  
-   Agregar un encabezado MIME y límites MIME al mensaje  
  
-   Enviar el mensaje al RNIFReceive.aspx del asociado  
  
-   Procesar un mensaje de señal devuelta  
  
## <a name="see-also"></a>Vea también  
 [Enviar y recibir páginas ASPX](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Ejemplos de aplicaciones web](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)