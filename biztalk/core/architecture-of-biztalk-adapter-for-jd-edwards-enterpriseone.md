---
title: Arquitectura de BizTalk Adapter para JD Edwards EnterpriseOne | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: architecture
ms.assetid: 0441c5d2-6a46-45b6-8ab5-0bdac3590f56
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 828d0ed6affc44edbf49beb204cd4afe21196747
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a>Arquitectura del adaptador de BizTalk para JD Edwards EnterpriseOne
El Adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne proporciona acceso a las funciones empresariales de JD Edwards EnterpriseOne. JD Edwards EnterpriseOne se comunica entre equipos cliente y servidor usando una arquitectura de mensajería propia denominada JDENet. JDENet se implementa mediante las clases de conector de JD Edwards EnterpriseOne que se encuentran en los archivos JAR, Connector.jar y Kernel.jar. La comunicación se implementa con TCP/IP como protocolo de transporte, con un puerto predeterminado 6009 o 6010. Para obtener una descripción de dónde se establece este valor, consulte [cómo establecer la propiedades de transporte de JD Edwards OneWorld](../core/how-to-set-jd-edwards-oneworld-transport-properties.md).  
  
 En la siguiente ilustración se muestra la arquitectura del Adaptador de BizTalk para JD Edwards EnterpriseOne.  
  
 ![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")  
  
## <a name="inbound-services-at-design-time"></a>Servicios de entrada en tiempo de diseño  
  
-   En tiempo de diseño, cree un puerto, seleccione un adaptador y proporcione información de credencial para conectar con el servidor JD Edwards EnterpriseOne de destino. El entorno de desarrollo de Visual Studio llama al marco del adaptador para solicitar información en tiempo de diseño para este puerto. El adaptador usa el Browsingagent para este puerto.  
  
-   En tiempo de diseño, BizTalk Server solicita información realizando llamadas al adaptador.  
  
-   El Browsingagent convierte la solicitud en código nativo de JD Edwards EnterpriseOne y transmite las solicitudes a JD Edwards EnterpriseOne a través de la conexión ThinNet API (establecida en Connector.jar y Kernel.jar).  
  
-   Una lista de módulos de JD Edwards EnterpriseOne se devuelve inicialmente y transporta al entorno de desarrollo de Visual Studio, donde rellena el Asistente para adaptador.  
  
-   Puede expandir la jerarquía mostrando el nombre de la biblioteca y, a continuación, el nombre del módulo.  
  
-   Cuando seleccione un módulo específico, verá esquemas para todas las funciones del módulo. El adaptador recibe la información necesaria de JD Edwards EnterpriseOne, y el browsingagent crea los esquemas.  
  
-   Los esquemas se agregan a la orquestación del proyecto de BizTalk Server.  
  
## <a name="inbound-services-at-run-time"></a>Servicios de entrada en tiempo de ejecución  
  
-   BizTalk Server llama al adaptador para enviar un mensaje en un puerto específico.  
  
-   El agente de tiempo de ejecución convierte XML en código JDE nativo.  
  
-   El agente de tiempo de ejecución envía la solicitud a través de ThinNet al sistema JD Edwards EnterpriseOne especificado en las propiedades de transporte del puerto de envío.  
  
-   La función empresarial principal se ejecuta en el sistema JD Edwards EnterpriseOne, que a continuación genera un documento de respuesta que indica éxito o fracaso, así como parámetros de datos que devuelve la función empresarial.  
  
-   El mensaje enviado a JD Edwards EnterpriseOne es una arquitectura de un único mensaje, una única respuesta. No se puede procesar varios mensajes al mismo tiempo.  
  
-   El documento de respuesta se devuelve a través de ThinNet, se convierte en XML y se vuelve a transmitir a BizTalk Server.  
  
## <a name="outbound-events-at-design-time"></a>Eventos de salida en tiempo de diseño  
  
-   Ninguna creación sistemática de metadatos de eventos está disponible.  
  
-   Debe proporcionarse a Visual Studio un facsímil del documento del evento de modo que pueda generarse un esquema e incorporarse al proyecto junto con el espacio de nombres de destino.  
  
## <a name="outbound-events-at-run-time"></a>Eventos de salida en tiempo de ejecución  
  
-   Se establece un mecanismo de transporte de archivo en el servidor JD Edwards EnterpriseOne para transportar el documento XML resultante, activado por la finalización del evento, al directorio de destino en dicho equipo.  
  
-   El equipo de BizTalk Server tiene una unidad asignada al directorio en el servidor EnterpriseOne.  
  
-   Las propiedades de transporte del puerto de recepción se configuran para la unidad asignada. El puerto de recepción recibe mensajes, que se registran en un directorio por el servidor EnterpriseOne.  
  
-   La identificación del espacio de nombres de destino asegura que se enruten los mensajes correctos al puerto de recepción configurado  
  
-   El puerto de recepción envía el documento XML en BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Planeamiento y arquitectura](../core/planning-and-architecture8.md)