---
title: Arquitectura de JD Edwards OneWorld | Documentos de Microsoft
description: Describe los servicios de entrada en tiempo de diseño y tiempo de ejecución y eventos de salida en tiempo de diseño y tiempo de ejecución en el adaptador de JD Edwards OneWorld en BizTalk
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9200a090-a587-4b60-9447-d281580f2078
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f866e5d72e392136d19c155785aaf6b71db2ce3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014795"
---
# <a name="architecture-of-jd-edwards-oneworld"></a>Arquitectura de JD Edwards OneWorld
Microsoft BizTalk Adapter para JD Edwards OneWorld proporciona acceso a las funciones de negocio de JD Edwards OneWorld. JD Edwards OneWorld se comunica entre los equipos cliente y servidor usando una arquitectura de mensajería patentada llamada JDENet. JDENet se implementa mediante las clases de conector de JD Edwards OneWorld que se encuentran en los archivos JAR, Connector.jar y Kernel.jar. La comunicación se implementa con TCP/IP como protocolo de transporte, con un puerto predeterminado 6009 o 6010. Para obtener una descripción de dónde se establece este valor, consulte [agregar los artefactos a la administración de BizTalk Server](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).  
  
 **Arquitectura para el adaptador de BizTalk para JD Edwards OneWorld**  
  
 ![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")  
  
 Las llamadas a las funciones de negocio de JD Edwards OneWorld necesitan dos mensajes:  
  
-   El primer mensaje responde con la ubicación del servidor que procesa la función de negocio. Esto se logra mediante la realización de una búsqueda en un conjunto de tablas denominadas *asignación de configuración de objeto (OCM)*.  
  
-   El segundo mensaje envía un búfer de mensajes formateados que contienen los argumentos que se deben pasar a JD Edwards OneWorld o desde éste al servidor adecuado, y espera una respuesta. Los búferes están formateados según las typedefs de las estructuras C++ subyacentes.  
  
## <a name="inbound-services-at-design-time"></a>Servicios de entrada en tiempo de diseño  
  
-   En tiempo de diseño, se crea el puerto, se selecciona el adaptador y se proporciona información de credenciales para conectar con el servidor JD Edwards OneWorld. El entorno de desarrollo de Visual Studio llama al marco del adaptador para solicitar información en tiempo de diseño para este puerto. BizTalk Adapter para JD Edwards OneWorld usa Browsingagent para este puerto.  
  
-   En tiempo de diseño, BizTalk Server solicita información realizando llamadas al adaptador.  
  
-   Browsingagent convierte la solicitud en código nativo de JD Edwards OneWorld y, a continuación, transmite las solicitudes a JD Edwards OneWorld mediante la conexión de API ThinNet (establecida en Connector.jar y Kernel.jar).  
  
-   Una función empresarial personalizada se instala a través de la instalación de BTSREL: expone las funciones de negocio principales.  
  
-   Inicialmente se devuelve una lista de módulos de JD Edwards OneWorld y se transporta a Visual Studio, donde llena el asistente para adaptador.  
  
-   Puede expandir la jerarquía para mostrar el nombre de biblioteca y el nombre de módulo.  
  
-   Cuando seleccione un módulo específico, verá esquemas para todas las funciones del módulo. El adaptador obtiene la información necesaria de JD Edwards OneWorld, y browsingagent crea los esquemas.  
  
-   Los esquemas se agregan a la orquestación del proyecto de BizTalk Server.  
  
## <a name="inbound-services-at-run-time"></a>Servicios de entrada en tiempo de ejecución  
  
-   BizTalk Server llama a BizTalk Adapter para JD Edwards OneWorld para enviar un mensaje en un puerto específico.  
  
-   El agente de tiempo de ejecución convierte el XML en código JD Edwards nativo.  
  
-   El agente de tiempo de ejecución envía la solicitud a través de ThinNet al sistema de negocio JD Edwards especificado en las propiedades de transporte del puerto de envío.  
  
-   La función de negocio principal se ejecuta en el sistema JD Edwards, que luego genera un documento de respuesta que indica el éxito o error, así como los parámetros de datos devueltos por la función de negocio.  
  
-   El mensaje enviado a JD Edwards OneWorld es una arquitectura de un solo mensaje y una sola respuesta. No se puede procesar varios mensajes al mismo tiempo.  
  
-   El documento de respuesta se devuelve a través de ThinNet, se convierte en XML y se vuelve a transmitir a BizTalk Server.  
  
## <a name="outbound-events-at-design-time"></a>Eventos de salida en tiempo de diseño  
  
-   Ninguna creación sistemática de metadatos de eventos está disponible.  
  
-   Debe proporcionarse a Visual Studio un facsímil del documento del evento de modo que pueda generarse un esquema e incorporarse al proyecto junto con el espacio de nombres de destino.  
  
## <a name="outbound-events-at-run-time"></a>Eventos de salida en tiempo de ejecución  
  
-   Se establece un mecanismo de transporte de archivos en el servidor de negocio JD Edwards para transportar el documento XML resultante, desencadenado por la finalización del evento, al directorio de destino en ese servidor.  
  
-   El equipo de BizTalk Server tiene una unidad asignada al directorio en el servidor de negocio.  
  
-   Las propiedades de transporte del puerto de recepción se configuran para la unidad asignada. El puerto de recepción recibe los mensajes publicados en el directorio por el servidor de negocio.  
  
-   La identificación de espacio de nombres de destino asegura que se enruten los mensajes correctos al puerto de recepción configurado.  
  
-   El puerto de recepción envía el documento XML a BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Agregar los artefactos a la administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [Planificación y arquitectura](../core/planning-and-architecture17.md)