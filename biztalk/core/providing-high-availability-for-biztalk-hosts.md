---
title: Proporcionar alta disponibilidad de Hosts de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- planning, hosts
- hosts, high availability
- messages, routing
- deploying, high availability
- high availability, hosts
- hosts
- hosts, planning
- MessageBox database
ms.assetid: 9583b85c-7cad-4016-8065-5ca7de3f4359
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f964a8e170c2215c4abb2b6b5842f8fe0e159457
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271900"
---
# <a name="providing-high-availability-for-biztalk-hosts"></a>Proporcionar alta disponibilidad a hosts de BizTalk
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona gran flexibilidad a la hora de tratar la alta disponibilidad, porque permite dedicar hosts lógicos de forma estratégica para ejecutar áreas específicas de funcionalidad como la recepción, el envío de mensajes o el procesamiento de orquestaciones.  
  
 Un host de BizTalk es un contenedor lógico en un grupo de servidores BizTalk Server que puede alojar elementos de BizTalk Server como controladores de adaptador, ubicaciones de recepción (incluidas canalizaciones) y orquestaciones. Normalmente, se agrupan elementos que tienen requisitos de escala similares en un host particular. Por ejemplo, se pueden agrupar las ubicaciones de recepción en un host de “recepción”, los puertos de envío en un host de “envío” y las orquestaciones en un host de “procesamiento”.  
  
 Después de crear un host (contenedor lógico), puede configurar instancias del host para que se ejecuten en equipos físicos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Una instancia de host se ejecuta como servicio Windows en el o los equipos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] designados. Aunque no es posible ejecutar varias instancias del mismo host en un equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determinado, puede ejecutar varias instancias de un host en particular configurando las instancias del host en equipos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] separados en un grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. También puede ejecutar varias instancias de host diferentes en un único equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Los elementos que contienen los hosts de BizTalk pueden realizar las siguientes funciones:  
  
-   **Recibir** estos elementos realizan el procesamiento inicial de los mensajes después de haberlos recogido en una ubicación de recepción. Cuando un host contiene un elemento de recepción, como una canalización o una ubicación de recepción, actúa como un límite de seguridad y la descodificación y descifrado de mensajes tiene lugar en una canalización del host.  
  
-   **Enviar** estos elementos realizan el procesamiento final de los mensajes antes de que se envíen al puerto de envío. Cuando un host contiene un elemento de envío, como un puerto de envío o una canalización, el host actúa como un límite de seguridad, y la firma y cifrado de mensajes tiene lugar en una canalización del host.  
  
-   **Procesamiento** estos elementos procesan los mensajes basados en las instrucciones que aparecen en una orquestación.  
  
 Aunque un único host de BizTalk puede contener elementos que reciban, envíen y procesen mensajes, se considera una práctica recomendable crear diferentes hosts para cada función para generar límites de seguridad y para facilitar la administración y la escalabilidad. En concreto, se recomienda utilizar hosts diferentes para operaciones de procesamiento y recepción y envío, así como separar los elementos de confianza de los no confiables.  
  
 Por ejemplo, si recibe un mensaje, ejecuta una orquestación y envía diez mensajes, deseará separar la funcionalidad de recepción y de envío en dos hosts diferentes porque los elementos de envío tendrán diez veces más tráfico que los elementos de recepción. Si recibe un mensaje, ejecuta una orquestación y envía un mensaje, puede pensar en estos elementos como una unidad de trabajo y agruparlos en un solo host. Como alternativa, puede separarlos en tres hosts diferentes para aumentar el rendimiento y la flexibilidad.  
  
 Hosts de BizTalk pueden ser de dos tipos, **en curso** o **Isolated**. Los hosts en curso se ejecutan dentro del proceso de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mientras que los hosts aislados no se ejecutan en el proceso de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. La tabla siguiente enumera los elementos que puede contener cada uno de estos tipos de host.  
  
|**Tipo de host**|**Contenedor lógico para**|  
|-------------------|-------------------------------|  
|En curso|-Orquestaciones<br />-Controladores de envío de adaptador<br />-Adaptador de recepción controladores distintos de HTTP y SOAP|  
|Aislado|Controladores de recepción HTTP y SOAP|  
  
 Para obtener más información sobre los hosts y las instancias de host, consulte [administración de Hosts de BizTalk e instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md).  
  
 Para proporcionar alta disponibilidad a los hosts de BizTalk, debe tener dos o más instancias de hosts para cada host en el entorno (en dos o más equipos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]). Al tener más de una instancia de cada host, garantiza que, si deja de estar disponible una instancia de host, los otros equipos que ejecutan instancias del mismo host pueden reanudar las funciones de la instancia de host problemática y el sistema global puede continuar funcionando con una interrupción mínima.  
  
## <a name="message-persistence"></a>Persistencia de mensajes  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] depende en gran medida de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para la alta disponibilidad porque cada host implicado en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] conserva los mensajes en la base de datos de cuadro de mensajes de BizTalk. Por ejemplo, cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje entrante, el host de recepción lo conserva en la base de datos de cuadro de mensajes antes de que otros hosts lo recuperen para el procesamiento y envío de orquestaciones.  
  
 Si su solución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implica orquestación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enruta el mensaje hacia el host que ejecuta el proceso empresarial (host de procesamiento) y guarda el mensaje en la base de datos de cuadro de mensajes cuando finaliza la orquestación. El host de envío recupera entonces el mensaje de la base de datos de cuadro de mensajes antes de enviarlo a la aplicación externa a través del adaptador de envío correspondiente.  
  
## <a name="separating-the-host-and-database-functions"></a>Separar las funciones de host y base de datos  
 Puesto que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] separa los datos de los hosts que procesan los datos, un paso que puede realizar para crear un entorno altamente disponible es separar las funciones de host (envío, recepción y procesamiento) que se producen en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de las funciones de base de datos que se producen en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Mediante la separación de estas funciones, puede escalar independientemente los hosts de procesamiento, envío y recepción y las bases de datos que almacenan los datos. Las capas de tiempo de ejecución y de base de datos están relacionadas, es decir, si aumenta el número de equipos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] probablemente necesitará aumentar el número de equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para manejar la carga adicional. Sin embargo, no hay una relación directa entre la capa de base de datos y la capa de BizTalk. Son dos capas independientes y puede escalarlas por separado.  
  
 Lo que debe hacer para que los hosts tengan una alta disponibilidad es diferente de lo que debe hacer para que las bases de datos tengan una alta disponibilidad. Las secciones siguientes explican lo que debe hacer para lograr una alta disponibilidad en los hosts de recepción, envío y procesamiento. Para obtener más información acerca de cómo hacer que la capa de base de datos sea alta disponibilidad, vea [proporcionar una alta disponibilidad para bases de datos de BizTalk Server](../core/providing-high-availability-for-biztalk-server-databases.md).  
  
 Para las implementaciones en las que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa más que SQL Server, puede configurar varios equipos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que usen el mismo equipo que ejecuta SQL Server. Esta configuración utiliza los recursos disponibles en cada equipo. Por ejemplo, si se hace un gran uso (más del 75%) de la CPU o de la memoria en el equipo con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], pero el uso es bajo (menos del 25%) en el equipo que ejecuta SQL Server, puede incluir equipos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adicionales para distribuir la carga de trabajo a la vez que aumenta el uso de recursos en el equipo que ejecuta SQL Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Hosts de recepción escalados](../core/scaled-out-receiving-hosts.md)  
  
-   [Hosts de procesamiento de escala horizontal](../core/scaled-out-processing-hosts.md)  
  
-   [Hosts de envío de escala horizontal](../core/scaled-out-sending-hosts.md)  
  
-   [Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)  
  
## <a name="see-also"></a>Vea también  
 [Proporcionar una alta disponibilidad para bases de datos de servidor BizTalk Server](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [Alta disponibilidad para el inicio de sesión único empresarial](../core/high-availability-for-enterprise-single-sign-on.md)