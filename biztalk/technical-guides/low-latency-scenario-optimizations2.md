---
title: Escenario de baja latencia Optimizations2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19cd78ce-ad7d-4e4b-8188-a63d707905d5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009b1298e90b586830f062c8e884b88995f9e33f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297996"
---
# <a name="low-latency-scenario-optimizations"></a>Optimizaciones de escenario de baja latencia
De forma predeterminada, el servidor BizTalk Server está optimizado para rendimiento en lugar de baja latencia. Las siguientes optimizaciones pueden aplicarse a BizTalk Server en escenarios donde es necesaria reducir la latencia.  
  
> [!NOTE]  
>  Estas optimizaciones mejorarán la latencia, pero pueden hacerlo con algún impacto en el rendimiento global.  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>Aumentar el tamaño de la cola de mensajes interna de host de BizTalk Server  
 Cada host de BizTalk tiene su propia cola en memoria interna. Aumentar el tamaño de esta cola desde el valor predeterminado de 100 a 10000 para mejorar el rendimiento para un escenario de baja latencia. Para obtener más información acerca de cómo modificar el valor del tamaño de cola de mensajes interna, consulte [cómo modificar recursos según configuración de la limitación](http://go.microsoft.com/fwlink/?LinkID=208366) (http://go.microsoft.com/fwlink/?LinkID=208366) en la documentación de BizTalk Server.  
  
> [!NOTE]  
>  Aumentar el valor de tamaño de cola de mensajes interna, aumentará la memoria utilizada por la instancia de host.  
  
## <a name="increase-the-biztalk-server-host-in-process-messages"></a>Aumentar los mensajes en proceso de host de BizTalk Server  
 Aumente los mensajes en curso desde el valor predeterminado de 1000 a 10.000 para mejorar el rendimiento. Para obtener más información acerca de cómo modificar el valor de los mensajes en curso, vea [cómo modificar la configuración predeterminada de limitación de Host](http://go.microsoft.com/fwlink/?LinkID=208366) (http://go.microsoft.com/fwlink/?LinkID=208366) en la documentación de BizTalk Server.  
  
> [!NOTE]  
>  Aumentar el valor de tamaño de cola de mensajes interna, aumentará la memoria utilizada por la instancia de host.  
  
## <a name="optimize-orchestrations-for-low-latency"></a>Optimizar las orquestaciones de baja latencia  
 Siga las recomendaciones de la sección "Recomendaciones para optimizar las orquestaciones escenarios de baja latencia" de [optimizar el rendimiento de la orquestación](../technical-guides/optimizing-orchestration-performance.md).  
  
## <a name="configure-polling-intervals"></a>Configurar intervalos de sondeo  
 Utilice el panel de configuración para configurar los intervalos de sondeo de un host dado en todo el grupo de BizTalk. Para cambiar los intervalos de sondeo:  
  
1.  En el **consola de administración de BizTalk Server**, expanda **administración de BizTalk Server**, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración** .  
  
2.  En el **panel de configuración de BizTalk** cuadro de diálogo la **Hosts** página, en la **General** ficha **intervalos de sondeo**, encontrará el **mensajería** y **orquestación** valores. De forma predeterminada, ambos valores se establecen en 500 milisegundos.  
  
 En la tabla siguiente se enumera los valores de sondeo que hemos usado para realizar pruebas en los Hosts de 64 bits de en curso de BizTalk (RxHost, TxHost y PxHost). Para deshabilitar el sondeo, puede establecer el intervalo de sondeo a un número muy grande que figuran en la tabla.  
  
|Hosts de servidor|Mensajería|Orquestación|  
|------------------|---------------|-------------------|  
|**RxHost**<br /><br /> Dado que solo estamos publicando ubicación de recepción de los mensajes entrantes en el cuadro de mensajes de BizTalk a través de un sentido, sondeo no es necesario en el RxHost (host de recepción).|200000|200000|  
|**TxHost**<br /><br /> Dado que sólo estamos recibiendo instancias de mensajería en el cuadro de mensaje de BizTalk, el sondeo de orquestación no es necesario en el TxHost (host de envío).|50|200000|  
|**PxHost**<br /><br /> Dado que sólo estamos recibiendo las instancias de orquestación en el cuadro de mensaje de BizTalk, el sondeo de mensajería no es necesario en el PxHost (host de procesamiento).|200000|50|  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento de BizTalk Server](../technical-guides/optimizing-biztalk-server-performance.md)