---
title: "Ajustar umbrales de limitación: Cuándo y por qué | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9afb26c8-e5f4-4b78-9a45-a1263e3cb6ab
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b49ae78d4b2d0cf2dabfc69af9023b1e8676dea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adjusting-throttling-thresholds-when-and-why"></a>Ajustar umbrales de limitación: Cuándo y por qué
Cuando se trata de la limitación, un tamaño no se ajusta a todo. Existe una serie de factores que determinarán lo que será una configuración óptima. BizTalk Server proporciona los valores predeterminados que se ha probado que protegen con eficacia un sistema de aspectos como la sobrecarga que supone el trabajo acumulado. Sin embargo, para determinados escenarios, puede ser demasiado agresivo. Los siguientes ejemplos muestran esta función.  
  
## <a name="example-1-peak-loads-and-database-size"></a>Ejemplo 1: Picos de carga y el tamaño de la base de datos  
 Cada solución basada en BizTalk Server tiene un rendimiento máximo sostenible (MST). Siempre que la carga permanezca por debajo de este nivel, el sistema puede mantener esa carga de forma indefinida, por definición. En la práctica, sin embargo, es más común encontrar en el perfil de carga valores máximos y mínimos que una carga continua que no varíe con el tiempo.  
  
 En lugar de crear un sistema que sea capaz de mantener los valores máximos de carga de forma indefinida, resulta más eficaz crear un sistema que pueda controlar algunos trabajos acumulados durante períodos de carga máxima, y que se recupere en situaciones de valores mínimos. Sin embargo, si el trabajo acumulado que se espera durante cargas máximas es mayor que el valor de limitación predeterminado para el tamaño de la base de datos, el sistema bloqueará el trabajo acumulado limitando la entrada. Si esto no es deseable, por ejemplo, porque necesita que se consuman todos los archivos de entrada tan pronto como sea posible, la solución es aumentar el umbral del tamaño de la base de datos para aceptar el trabajo acumulado esperado antes de la limitación.  
  
## <a name="example-2-memory-usage-optimization"></a>Ejemplo 2: Optimización del uso de memoria  
 Otro recurso que usa la limitación para estimar la velocidad de procesamiento es de cuánta memoria se dispone para alojar procesos. Si la memoria disponible es muy poca comparada con el umbral, la limitación reducirá el número de mensajes que recupera el motor desde las colas del host en las que se va a trabajar. Dada la diferencia en cantidad y disponibilidad de memoria de los servidores de clases empresariales actuales, especialmente con compatiblidad con x64 en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es probable que el umbral deba elevarse o bajarse para optimizar el uso de memoria.  
  
## <a name="recommendation"></a>Recomendación  
 La limitación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está configurada de forma predeterminada para proporcionar una buena protección para el sistema. Sin embargo, no debería darse por sentado que la configuración predeterminada sea óptima. Supervise el estado de limitación de los contadores de rendimiento para ver si se está aplicando la limitación, analice si el recurso en el que se basa la limitación (por ejemplo, el tamaño de la base de datos o el uso de la memoria) se está infrautilizando o utilizando en exceso y ajuste, a continuación, los umbrales de limitación según corresponda.