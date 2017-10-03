---
title: "Traducir los patrones de la solución de administración de procesos empresariales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, patterns
- patterns [process management solutions], orchestration boundaries
- patterns [process management solutions], translating patterns to artifacts
- orchestrations, patterns
- orchestrations, boundaries
ms.assetid: 69f37732-f235-4bbb-bc85-31b4971c95ce
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23603e66e80461baecea88648100442eb9da0166
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="translating-the-patterns-of-the-business-process-management-solution"></a>Traducir los patrones de la solución de administración de procesos empresariales
En esta sección se describe cómo traduce la solución el diagrama de patrones en artefactos de BizTalk Server.  
  
 ![Patrones de solución de administración de procesos de negocio](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
## <a name="connections"></a>Conexiones  
 Las conexiones son las rutas de los mensajes entre los componentes de la solución. El lugar más fácil para empezar es la interfaz de servicio. BizTalk Server facilita la presentación de una orquestación como servicio Web. Para obtener información acerca de cómo exponer orquestaciones como servicios web, consulte [cómo orquestaciones de mapa a los servicios Web](../core/how-to-map-orchestrations-to-web-services.md).  
  
 Existen otras conexiones entre el servicio y la sección de preprocesamiento, entre la sección de preprocesamiento y el administrador de procesos, y entre el administrador de procesos y las fases de procesamiento. Las conexiones también incluyen las conexiones entre las fases y los sistemas servidor, y entre el preprocesamiento y la base de datos de historial y el sistema de servicio.  
  
> [!NOTE]
>  Los traductores corresponden a asignaciones de BizTalk. Las asignaciones son a su vez, partes de canalizaciones o **transformar** formas de orquestación.  
  
 La decisión de hacer que la conexión al administrador de procesos sea síncrona o asíncrona requiere cierta consideración. A diferencia de una comprobación de crédito, no es probable que un pedido en un proceso como el de la solicitud de servicios de cable finalice rápidamente. La lógica de administración del proceso es más compleja si la conexión con el administrador de procesos es asíncrona y requiere correlación. De hecho, esta solución utiliza una conexión asíncrona con el administrador de procesos mediante la publicación de mensajes en el Cuadro de mensajes.  
  
 Las conexiones entre el administrador de procesos y las fases representan un equilibrio similar al de la conservación de recursos de servidor y la simplificación de la lógica. Las fases tienen tiempos de procesamiento más cortos que el administrador de procesos. Cada fase debe finalizar su procesamiento antes de que éste continúe en la siguiente fase. No obstante, puesto que podríamos desear modificar las fases, el administrador de procesos no puede estar acoplado estrechamente a las fases. En la aplicación, se puede describir la conexión como un modelo de publicación-suscripción limitado. El administrador de procesos envía mensajes a las fases a través de un único puerto dedicado. Las fases, a su vez, filtran para reconocer mensajes específicamente para ellos.  
  
## <a name="determining-orchestration-boundaries"></a>Determinar los límites de la orquestación  
 El patrón queda incluida en tres áreas principales: preprocesar los mensajes, administrar los procesos empresariales y el proceso empresarial en Sí. El preprocesamiento consiste en controlar la conexión con el servicio Web, traducir los mensajes a mensajes para la respuesta, notificar al sistema de servicio, realizar entradas en la base de datos de historial y transmitir mensajes al administrador de procesos. En la aplicación, una única orquestación controla el preprocesamiento. Otra orquestación controla la administración del proceso empresarial. El proceso empresarial que se está administrando se divide en las fases correspondientes. Cada fase corresponde a una orquestación para permitir las adiciones y eliminaciones que representan cambios en el proceso de pedido. Para obtener más información sobre el diseño de las fases del proceso de pedido, vea "Dividir procesos empresariales" en [algunos principios de diseño de la solución de administración de procesos empresariales](../core/some-design-principles-in-the-business-process-management-solution.md).  
  
## <a name="translating-the-components-into-orchestrations"></a>Traducir los componentes a orquestaciones  
 La primera orquestación, **OrderBroker**, traduce el diagrama de forma sencilla y directa. La orquestación asigna principalmente formas utilizadas para construir los mensajes de notificación y el mensaje de pedido para el administrador de procesos. Para obtener una lista completa de las formas de orquestación, consulte [formas de orquestación](../core/orchestration-shapes.md).  
  
 La lógica del administrador de procesos y sus ensamblados satélite es bastante compleja. Para obtener información acerca de la lógica de la orquestación de administrador de procesos, **OrderManager**, consulte [lógica del Administrador de procesos](../core/process-manager-logic.md).  
  
## <a name="see-also"></a>Vea también  
 [Patrones de la solución de administración de procesos empresariales](../core/patterns-in-the-business-process-management-solution.md)   
 [Diseñar con patrones: la solución de administración de procesos empresariales](../core/designing-with-patterns-the-business-process-management-solution.md)   
 [Catálogo de patrones para la solución de administración de procesos empresariales](../core/pattern-catalog-for-the-business-process-management-solution.md)