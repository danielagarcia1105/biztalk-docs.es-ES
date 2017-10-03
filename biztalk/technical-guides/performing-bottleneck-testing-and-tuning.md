---
title: "Realización de pruebas y ajustes de cuello de botella | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95d41d95-3a76-4eb0-b07d-14c6b6dccdaa
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d21b558f75824340718f7bd6efa3f10ae9926ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="performing-bottleneck-testing-and-tuning"></a>Realización de pruebas y ajustes de cuello de botella
Debe completar las pruebas de rendimiento para determinar los cuellos de botella en el sistema y para optimizar el sistema en consecuencia.  
  
## <a name="testing-a-subsystem"></a>Probar un subsistema  
 Es una práctica recomendada para identificar cuellos de botella del sistema ejecutar pruebas de rendimiento en los subconjuntos de todo el sistema, por ejemplo:  
  
-   Establecer parámetros de rendimiento de línea de base para los sistemas externos que envían los mensajes o recibir mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Dar de alta de orquestaciones, pero no se inician. Eliminar mensajes en las ubicaciones de archivos o las colas de entrada y permiten la entrada adaptadores purga el archivo de cola/las ubicaciones de recepción y publicar mensajes en la base de datos de cuadro de mensajes. Esto permite aislar la recepción de puertos determinar su velocidad máxima de entrada constante.  
  
-   Una vez que los mensajes se incorporan a la base de datos de cuadro de mensajes, detener los adaptadores de recepción, habilitar los procesos de orquestación, adaptadores, de envío y, a continuación, medir la velocidad en las orquestaciones o adaptadores procesan los mensajes de envío.  
  
## <a name="testing-the-end-to-end-system"></a>Pruebas del sistema to-End  
 Pruebas de las tasas de entrada y salidas, como se describe en la sección anterior es una manera eficaz para aislar el rendimiento del subsistema de aplicación, aunque no se describe el rendimiento de extremo a extremo. También debe probar el rendimiento de extremo a extremo porque no se puede identificar algunos cuellos de botella hasta que empieza a varios recursos compitan por el mismo recurso compartido (por ejemplo, la base de datos de cuadro de mensajes).  
  
 Para generar una carga en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, considere el uso de la herramienta de Microsoft BizTalk LoadGen 2007. Para obtener más información acerca de la herramienta LoadGen 2007 vea [Microsoft BizTalk LoadGen 2007](http://go.microsoft.com/fwlink/?LinkID=59841) (http://go.microsoft.com/fwlink/?LinkID=59841).  
  
 Para generar y analizar un informe de rendimiento para un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, considere el uso de la herramienta de análisis de rendimiento de registros (PAL). Para obtener más información acerca de la herramienta de la PAL, vea [mediante la herramienta de análisis de rendimiento de registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).  
  
## <a name="what-developers-operators-and-administrators-should-know"></a>Deben saber qué a los desarrolladores, operadores y administradores  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]los desarrolladores deben estar familiarizados en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] características de rendimiento y optimización. Operadores y administradores deben tener conocimientos acerca de aspectos de escalabilidad horizontal para la base de datos de cuadro de mensajes, SAN para la optimización, la optimización de red y la optimización de base de datos de SQL Server (por ejemplo, vea [SQL Server configuración que no se debería cambiar](../technical-guides/sql-server-settings-that-should-not-be-changed.md)). Los desarrolladores, operadores y administradores deben tener en cuenta cómo optimizar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de alto rendimiento y baja latencia.