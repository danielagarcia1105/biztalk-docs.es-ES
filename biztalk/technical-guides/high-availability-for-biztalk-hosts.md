---
title: Alta disponibilidad para los Hosts de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3153f7f7-7e82-4b0c-9b48-e9f871de285d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f500deb38df3f8145a2cba582164f14c87ac33d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="high-availability-for-biztalk-hosts"></a>Alta disponibilidad para los Hosts de BizTalk
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]proporciona gran flexibilidad para tratar la alta disponibilidad, porque permite dedicar hosts lógicos para ejecutar áreas específicas de funcionalidad, como la recepción y envío de mensajes o el procesamiento de orquestaciones, que se pueden implementar físicamente en forma estratégica varios servidores.  
  
 Un Host de BizTalk es un contenedor lógico dentro de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo que puede alojar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] elementos como adaptador (incluidas las canalizaciones) de controladores de envío, ubicaciones de recepción y orquestaciones. Normalmente, se agrupan elementos que tienen propiedades de escala similares en un host particular.  
  
 Después de crear un host, puede implementarla en un física [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo como una instancia de host. Una instancia de host se ejecuta como un servicio de Windows, BTSNTSvc.exe (o BTSNTSvc64.exe para la instancia de host de 64 bits), en designado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo. Para cada host, puede tener sólo una instancia en un determinado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo. Sin embargo, puede tener instancias de un host concreto en uno o varios [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y puede tener instancias de distintos hosts en un determinado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo.  
  
 Elementos que se encuentran en Hosts de BizTalk pueden realizar las siguientes funciones:  
  
-   **Recibir**. Estos elementos realizan el procesamiento inicial de los mensajes después de haberlos recogido en una ubicación de recepción. Cuando un host contiene un elemento de recepción, como una ubicación de recepción (con una canalización), el mensaje de descodificación y descifrado se produce en una canalización del host.  
  
-   **Enviar**. Estos elementos realizan el procesamiento final de los mensajes antes de enviarlos al puerto de envío. Cuando un host contiene un elemento de envío, por ejemplo, un puerto de envío, la firma del mensaje y el cifrado se produce en una canalización del host.  
  
-   **Procesamiento**. Estos elementos procesan los mensajes basados en las instrucciones que aparecen en las orquestaciones.  
  
 Un host de BizTalk puede contener elementos que reciben, envían y procesan mensajes. Para facilitar la administración y escalabilidad, se recomienda crear diferentes hosts designados para cada función. En concreto, se recomienda utilizar hosts diferentes para el procesamiento y para las operaciones de envío y recepción.  
  
 Por ejemplo, si recibe un mensaje, ejecuta una orquestación y envía diez mensajes, deseará separar la funcionalidad de recepción y de envío en dos hosts diferentes porque los elementos de envío tendrán diez veces más tráfico que los elementos de recepción. Si recibe un mensaje, ejecuta una orquestación y envía un mensaje, puede pensar en estos elementos como una unidad de trabajo y agruparlos en un solo host. Como alternativa, puede separarlos en tres hosts diferentes para aumentar el rendimiento y la flexibilidad, aunque esto también aumenta el costo de administración.  
  
 Hosts de BizTalk pueden ser de dos tipos, *en curso* o *Isolated*. Hosts en curso se ejecutan dentro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proceso de tiempo de ejecución (BTSNTSvc.exe o BTSNTSvc64.exe) y los hosts aislados no se ejecutan en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proceso en tiempo de ejecución. Hosts aislados solo se usan en el lado receptor para adaptadores de recepción la aislado. La tabla siguiente enumera los elementos que puede contener cada uno de estos tipos de host.  
  
|Tipo de host|Contenedor lógico para|  
|---------------|---------------------------|  
|En curso|-Orquestaciones<br />-Controladores de envío de adaptador<br />-Controladores de recepción de adaptador en curso|  
|Aislado|-Controladores de recepción HTTP, SOAP<br />-Cualquier otro adaptador aislado controladores de recepción|  
  
 Para obtener más información acerca de cómo administrar Hosts de BizTalk e instancias de host, consulte [administración de Hosts de BizTalk e instancias de Host](http://go.microsoft.com/fwlink/?LinkID=154191) (http://go.microsoft.com/fwlink/?LinkID=154191) en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
 Para proporcionar alta disponibilidad para los Hosts de BizTalk, debe tener dos o más instancias de host para cada host (en dos o más equipos) en su entorno. Al tener más de una instancia de host para cada host Asegúrese de que, si una instancia de host no está disponible, el host de instancias en otros equipos que ejecutan instancias del mismo host puede reanudar las funciones de la instancia de host problemática, y que el sistema global puede continuar funcionando con interrupciones mínimas.  
  
## <a name="disadvantages-of-additional-hosts"></a>Desventajas de Hosts adicionales  
 Aunque hay ventajas de creación de instancias de host adicionales, también hay posibles inconvenientes si hay demasiadas instancias de host se crean. Cada instancia de host es un servicio de Windows (BTSNTSvc.exe o BTSNTSvc64.exe), que genera una carga adicional en la base de datos de cuadro de mensajes y consume recursos del equipo, como CPU, memoria y subprocesos. Distintos de estos, tiene las siguientes razones para no configurar demasiadas instancias de host adicional:  
  
-   Se muestran varios contadores de rendimiento por host con demasiada granularidad. Esto afecta a la facilidad de uso para el administrador que necesite desplazarse por una gran cantidad de datos. Esto tiene un impacto negativo en la vista general, que el administrador tiene.  
  
-   Cada host consume una cantidad considerable de memoria que podría dar lugar a una situación de limitación y una reducción del rendimiento.  
  
-   Si los hosts haya adaptadores de recepción que continuamente realizan sondeo, cada host sondeará la base de datos a intervalos cortos, lo que resulta en un rendimiento degradado.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [El escalado de Hosts de recepción](../technical-guides/scaling-out-receiving-hosts.md)  
  
-   [Clústeres de Hosts de recepción](../technical-guides/clustering-receiving-hosts.md)  
  
-   [Ajuste de escala en Hosts de procesamiento](../technical-guides/scaling-out-processing-hosts.md)  
  
-   [El escalado de Hosts de envío](../technical-guides/scaling-out-sending-hosts.md)  
  
## <a name="see-also"></a>Vea también  
 [Configuración de Hosts e instancias de Host](../technical-guides/configuring-hosts-and-host-instances.md)   
 [Configurar un Host de seguimiento dedicado](../technical-guides/configuring-a-dedicated-tracking-host.md)   
 [Planeación de alta disponibilidad2](../technical-guides/planning-for-high-availability2.md)   
 [Alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md)   
 [Alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md)