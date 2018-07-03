---
title: Realización de pruebas y ajustes de cuello de botella | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d41d95-3a76-4eb0-b07d-14c6b6dccdaa
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 468f7a3a35922c6348369050593cbb56b56457d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018597"
---
# <a name="performing-bottleneck-testing-and-tuning"></a>Realización de pruebas y ajustes de cuello de botella
Debe completar las pruebas de rendimiento para determinar los cuellos de botella en el sistema y ajustar el sistema en consecuencia.  
  
## <a name="testing-a-subsystem"></a>Las pruebas de un subsistema  
 Es una práctica recomendada para identificar cuellos de botella del sistema ejecutar las pruebas de rendimiento en los subconjuntos de todo el sistema, por ejemplo:  
  
- Establecer parámetros de rendimiento de línea de base para los sistemas externos que envían o recepción mensajes desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- Dar de alta de orquestaciones, pero no se inician. Eliminar mensajes en las ubicaciones de colas/archivo de entrada y permitir que la entrada purga de los adaptadores de recepción de las ubicaciones de archivo de cola/y publicar mensajes en la base de datos de cuadro de mensajes. Esto permite aislar la recepción de puertos determinar su tasa de entrada máxima sostenida.  
  
- Una vez que se extraen los mensajes en la base de datos de cuadro de mensajes, detener los adaptadores de recepción, habilitar los procesos de orquestación, los adaptadores de envío y, a continuación, medir la velocidad a la que las orquestaciones o adaptadores están procesando mensajes de envío.  
  
## <a name="testing-the-end-to-end-system"></a>Pruebas del sistema to-End  
 Las pruebas de las tasas de entrada y salidas, como se describe en la sección anterior es una forma eficaz para aislar el rendimiento del subsistema de la aplicación, aunque no se describe el rendimiento de extremo a otro. También debe probar el rendimiento de extremo a otro porque no se puede identificar cuellos de botella en alguna hasta que empieza a varios recursos competir por el mismo recurso compartido (por ejemplo, la base de datos de cuadro de mensajes).  
  
 Para generar cargas en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, considere la posibilidad de usar la herramienta de Microsoft BizTalk LoadGen 2007. Descargar [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).  
  
 Para generar y analizar un informe de rendimiento para un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, considere la posibilidad de usar la herramienta de análisis de rendimiento de los registros (PAL). Para obtener más información acerca de la herramienta de la PAL, vea [mediante la herramienta de análisis de rendimiento de los registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).  
  
## <a name="what-developers-operators-and-administrators-should-know"></a>Deben saber qué los desarrolladores, operadores y administradores  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los desarrolladores deben ser expertos en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] características de rendimiento y optimización. Operadores y administradores deben tener conocimientos acerca de aspectos de escalabilidad horizontal para la base de datos de cuadro de mensajes, SAN optimización, la optimización de red y la optimización de base de datos de SQL Server (por ejemplo, vea [SQL Server configuración que no se debe cambiar](../technical-guides/sql-server-settings-that-should-not-be-changed.md)). Los desarrolladores, operadores y administradores deben ser conscientes de cómo optimizar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de alto rendimiento y baja latencia.