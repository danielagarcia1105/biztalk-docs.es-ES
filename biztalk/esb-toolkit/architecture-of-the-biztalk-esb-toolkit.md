---
title: Arquitectura del Kit de herramientas de ESB de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a41674f5-5ea4-4a8f-a270-b67fd6854028
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6a85e8e98e7ea2874935656553b18abac7ca88a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="architecture-of-the-biztalk-esb-toolkit"></a>Arquitectura del Kit de herramientas de ESB de BizTalk
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consta de una serie de interoperar componentes que admiten e implementan un entorno de mensajería con acoplamiento flexible que resulta más fácil crear aplicaciones empresariales basadas en mensajes. Los servicios y componentes se dividen de forma natural en las siete categorías siguientes:  
  
-   **Servicios Web.** Estos exponen servicios internos como itinerario procesamiento, administración de excepciones, la resolución de extremos y asignaciones, las operaciones del servidor de BizTalk, interoperación de Universal Description, Discovery y Integration (UDDI) y transformación del contenido del mensaje .  
  
-   **Servicios de itinerarios.** Estos incluyen servicios basados en la mensajería y orquestación para realizar las transformaciones y enrutamiento de mensajes. Puede crear servicios personalizados que participan en el procesamiento de itinerario. Estos incluyen servicios basados en la mensajería y orquestación para realizar las transformaciones y enrutamiento de mensajes. Puede crear servicios personalizados que participan en el procesamiento de itinerario.  
  
-   **Pendientes en itinerarios.** Estos mensajes externos de recepción, adjuntar el itinerario adecuado para cada mensaje y realizan un procesamiento itinerario; usan el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y los metadatos.  
  
-   **Pendientes.** A diferencia de en itinerarios-pendientes, se reciben mensajes externos en una variedad de formatos y transportes, como HTTP, Java Message Service (JMS), wmq (IBM WebSphere MQ de ESB Web), protocolo de transferencia de archivos (FTP), archivos sin formato y XML. Son típicos BizTalk Server ubicaciones de recepción que, opcionalmente, use la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes de canalización de interoperabilidad y la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y los metadatos.  
  
-   **Desactivar pendientes.** Estos implementan puertos de envío para la entrega de mensajes con formatos y transportes como WCF, JMS, wmq de ESB, FTP, HTTP, archivo sin formato, XML o cualquier otros formatos personalizados. Son los puertos de envío dinámicos que están enlazados directamente en el cuadro de mensaje y, opcionalmente, utilizan el servidor BizTalk Server típico la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes de canalización de interoperabilidad y la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y metadatos.  
  
-   **Marco de administración de excepciones.** Esto incluye el servicio Web de excepción, la API de administración de excepciones y los componentes que enriquecen, procesarán y pasan los detalles de la excepción en el Portal de administración de ESB.  
  
-   **Portal de administración de ESB.** Esta aplicación de ejemplo proporciona el aprovisionamiento del registro, mediación de excepción, notificación de alertas y análisis.  
  
 Muchos de estos componentes y servicios dependen de las características implementadas por BizTalk Server, como los motores de orquestación, transformación y las reglas de negocios y la base de datos de cuadro de mensaje. La figura 1 muestra una vista esquemática de las categorías, los componentes y servicios que normalmente se producen dentro de cada categoría, y los componentes principales del sistema de BizTalk Server utilizan por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
 ![Arquitectura ESB](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
 **Figura 1**  
  
 **La arquitectura y los componentes de la[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>Funcionamiento del kit de herramientas de BizTalk ESB  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] acepta mensajes de entrada y trabaja en ellos, quizás (pero no siempre) mediante la ejecución de procesos como la transformación, personalizado de enrutamiento o cualquier otro proceso definido. Para especificar las operaciones necesarias, los componentes de procesamiento principales requieren cada mensaje que se va a tener una lista de distribución que contiene instrucciones asociadas y las tareas que se ejecutan con el contenido del mensaje y metadatos que definen los procesos que se va a aplicar. Estas listas de distribución se conocen como itinerarios pueden automáticamente resuelto, recuperar desde un repositorio central y adjunto a un mensaje cuando se recibe en rampa.  
  
 Este enfoque de slip enrutamiento proporciona un acoplamiento flexible entre servicios, lo que significa que ESB no requiere el conocimiento previo del procesamiento específico para cada mensaje. Solo tiene que saber qué es el intervalo posible de procesos y cómo aplicar cada proceso. La amplia variedad de opciones para especificar los procesos disponibles y la asignación entre los procesos y las instrucciones dentro de los mensajes proporciona un mecanismo flexible para configurar y ajustar el comportamiento, sin requerir cambios en el código ni la nueva implementación de componentes.  
  
## <a name="design-patterns"></a>Patrones de diseño  
 La arquitectura que utiliza ESB, donde procesos deposite mensajes en la base de datos de cuadro de mensaje y los suscriptores recoge ellos en función de una instrucción de procesamiento en el mensaje, implementa el patrón de diseño de la máquina de Estados de forma efectiva. Además, ESB implementa y expone su funcionalidad básica de una manera orientada a servicios, entre otras, las aplicaciones externas a través de un conjunto de servicios Web principales.  
  
 Este enfoque de acoplamiento flexible para el diseño de BizTalk Server y [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]-aplicaciones basadas en produce soluciones muy flexibles y se ha convertido en un procedimiento recomendado aceptados en el sector.