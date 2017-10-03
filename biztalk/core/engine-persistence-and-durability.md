---
title: Motor de persistencia y durabilidad | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9bd209e9-75d2-422f-b3b2-377986f41f2f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13f9f3f1a02ddfe84a963704476e867783f31042
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="engine-persistence-and-durability"></a>Persistencia y durabilidad del motor
En esta sección se explica cómo BizTalk Server integra de forma confiable procesos empresariales de acoplamiento flexible al guardar el estado de los procesos en el disco a través de SQL Server. Al guardar el estado en los momentos oportunos y utilizar transacciones, el sistema garantiza que no se pierda ningún estado de los procesos aunque se produzcan errores de hardware o software. A esto se le denomina durabilidad del sistema.  
  
## <a name="loosely-coupled-business-process-management"></a>Administración de procesos empresariales de acoplamiento flexible  
 Para integrar los sistemas existentes con el fin de ejecutar un único proceso empresarial lógico, es necesario administrar el estado de los procesos fuera de los sistemas existentes. El estado de los procesos empresariales, ya sean de larga o corta duración, se debe mantener de forma independiente para evitar que se produzca una explosión de las rutas de comunicación personalizadas como resultado del acoplamiento de los sistemas.  
  
 Es evidente que el estado de una instancia de proceso empresarial en ejecución debe ser de confianza si el proceso empresarial cumple una función crucial. Para garantizar la confiabilidad y durabilidad de los procesos empresariales, BizTalk utiliza transacciones de SQL Server para guardar el estado de los procesos y los datos empresariales en una base de datos del disco denominada base de datos de cuadro de mensajes. Para obtener más información acerca de la base de datos de cuadro de mensajes, vea [la base de datos de cuadro de mensajes](../core/the-messagebox-database.md).  
  
 Todos los mensajes y todas las instancias de procesos empresariales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (por ejemplo, las instancias de orquestación), excepto las más triviales, se guardan en la base de datos de cuadro de mensajes al menos una vez durante el procesamiento.  
  
## <a name="persistence-and-sustainability"></a>Persistencia y sostenibilidad  
 El hecho de que BizTalk Server guarda todos los mensajes y la mayoría de las orquestaciones tiene un efecto directo en la sostenibilidad como se indicó en [¿qué es rendimiento sostenible?](../core/what-is-sustainable-performance.md) Conforme lleguen mensajes en la base de datos de cuadro de mensajes, son enrutados a los suscriptores de espera (por ejemplo, orquestaciones y enviar puertos) y en cola o publicados en tablas SQL de cuadro de mensajes debe esperar para que suscriptores que toman y procesarlos. Algunos de los mensajes que llegan activan nuevas instancias de suscriptor. Otros mensajes llegan y se enrutan, a través de correlación, a una instancia de un suscriptor que ya está en ejecución y que lo está esperando, como una orquestación correlacionada.  
  
 Para que las orquestaciones correlacionadas continúen el procesamiento, los mensajes correlacionados que llegan no deben estar bloqueados. Para facilitar esto, BizTalk trata de garantizar que se siguen recibiendo los mensajes (tanto de activación como de correlación), incluso si hay una elevada carga, de modo que los suscriptores que esperan los mensajes correlacionados puedan finalizar y dejar espacio para la ejecución de más procesos. Esto significa que es posible recibir mensajes más rápido de lo que se pueden procesar y quitar de la base de datos de cuadro de mensajes, con lo que se crea un registro de mensajes. Al tratarse de una tecnología de almacenamiento y reenvío, es lógico que BizTalk proporcione este tipo de almacenamiento en búfer. Sin embargo, se pueden producir problemas si la velocidad de recepción es constantemente más rápida que la velocidad de procesamiento de forma indefinida, con la consiguiente creación de un registro de gran tamaño.  
  
 Cada mensaje recibido o creado en BizTalk Server es inmutable; es decir, su contenido no cambia una vez recibido o creado. Además, los mensajes recibidos pueden tener varios suscriptores. Cada suscriptor de un mensaje concreto hace referencia a la misma copia única de dicho mensaje. Aunque con este enfoque se reduce al mínimo el almacenamiento, es necesario almacenar un contador de referencia (ref-count) para cada mensaje, así como realizar un mantenimiento periódico para eliminar los mensajes cuyo contador de referencia sea igual a 0.  
  
 Si se permite un registro suficientemente grande en la base de datos de cuadro de mensajes, se retrasarán los procesos de mantenimiento de la base de datos (implementados como un conjunto de trabajos del Agente SQL Server para cada base de datos de cuadro de mensajes) y, en caso de que no se puedan poner al día, probablemente se producirán problemas tales como espacio insuficiente en el disco. Para evitar esta situación, BizTalk Server proporciona un mecanismo de limitación que reduce la velocidad de recepción de mensajes cuando el registro de la base de datos de cuadro de mensajes alcanza un determinado nivel configurado por el usuario. Para obtener más información acerca de la limitación, consulte [optimizar recursos a través de Host de límite de uso](../core/optimizing-resource-usage-through-host-throttling.md).  
  
 Considerando todas las actividades y los procesos que contribuyen a la sostenibilidad, la medida principal de sostenibilidad a lo largo del tiempo es que no se permita de forma indefinida el crecimiento del registro. Es decir, que exista un equilibrio a lo largo del tiempo entre los niveles de rendimiento máximo y mínimo para que la base de datos de cuadro de mensajes pueda mantener un registro medio que sea constante y se pueda administrar. La medida principal de registro es la profundidad de la tabla de cola de impresión, que se expone como un contador de rendimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] denominado BizTalk:Cuadro de mensajes:Contadores generales:Tamaño de cola de impresión. Para obtener más información acerca de este contador de rendimiento, consulte [contadores de rendimiento del cuadro de mensaje](../core/message-box-performance-counters.md).  
  
 Para obtener más información acerca de cómo usar el tamaño de cola de impresión y otros contadores para determinar el rendimiento máximo que puede admitir un sistema, consulte [medir el rendimiento máximo sostenible motor](../core/measuring-maximum-sustainable-engine-throughput.md).  
  
## <a name="recommendations"></a>Recomendaciones  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] guarda todos los mensajes y la mayoría de las orquestaciones y, en caso de que no se controle, puede crear un registro de mensajes que puede producir problemas tales como espacio insuficiente en el disco. La medida principal de registro es la profundidad de la tabla de cola de impresión del cuadro de mensajes, que se expone como un contador de rendimiento denominado: BizTalk cuadro: General contadores: tamaño cola de impresión.  
  
 Con el fin de lograr un rendimiento sostenible, el tamaño de cola de impresión debe admitir un rendimiento medio estable a lo largo del tiempo. Es decir, la cola de impresión no puede seguir creciendo sin control de manera indefinida. En [medir el rendimiento máximo sostenible motor](../core/measuring-maximum-sustainable-engine-throughput.md), este comportamiento se describe con más detalle y se proporciona un método para determinar el rendimiento máximo que puede admitir un sistema que utiliza el tamaño de cola de impresión y otro rendimiento indicadores.  
  
## <a name="see-also"></a>Vea también  
 [Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [¿Qué es rendimiento sostenible?](../core/what-is-sustainable-performance.md)   
 [Trucos y sugerencias de rendimiento](../core/performance-tips-and-tricks.md)   
 [Contadores de rendimiento del cuadro de mensaje](../core/message-box-performance-counters.md)