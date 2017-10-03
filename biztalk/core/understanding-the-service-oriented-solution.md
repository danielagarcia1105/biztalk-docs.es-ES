---
title: "Descripción del servicio de solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service solution tutorial, background information
- service solutions, about service solutions
- service solution tutorial, about service solution tutorial
- Service Oriented Architecture (SOA)
ms.assetid: 56a2ad90-74bb-489a-ab1d-900f3bea3d64
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8be3a1e7a05c2c60f1ab16c6da4df74dddf7adb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-the-service-oriented-solution"></a>Descripción del servicio de solución orientada a servicios
La solución orientada a servicios presenta una aplicación de informes de saldo de crédito diseñada como un servicio. La aplicación, a su vez, utiliza tres aplicaciones de servidor expuestas como servicios para obtener la información necesaria para el saldo de crédito.  
  
 Una arquitectura orientada a servicios (SOA) es un enfoque que se superpone parcialmente con la generación de sistemas distribuidos. Un enfoque orientado a servicios tiene varias características:  
  
-   Ligeramente acoplado. La lógica empresarial de la aplicación está separada de la lógica de control del servicio.  
  
-   Se puede detectar. Debería haber un mecanismo para que las aplicaciones encuentren el servicio.  
  
-   Contractual. La interfaz del servicio implementa el contrato entre los usuarios y el servicio.  
  
 Aunque en la literatura se trata con frecuencia los enfoques orientados a servicios como sinónimos de los servicios Web, no son necesariamente sinónimos. Los servicios Web presentan un modo atractivo de implementar soluciones orientadas a servicios, pero puede usar otras tecnologías, como el entorno remoto de .NET, para crear servicios.  
  
 Para obtener más información acerca de las arquitecturas orientadas a servicios, vea "Service Interface" en [http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185) y "Service-Oriented Integration" en [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186).  
  
## <a name="reader-guidance"></a>Instrucciones para el lector  
 La documentación de esta solución asume que está familiarizado con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. También asume que comprende los conceptos básicos de la integración de aplicaciones empresariales y los servicios Web.  
  
 Además, para leer y seguir la documentación para desarrolladores, debe estar familiarizado con cómo compilar aplicaciones usando [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y con las siguientes tareas: crear proyectos, establecimiento de referencias y depuración y prueba BizTalk soluciones.  
  
## <a name="credit-card-reporting-at-woodgrove-bank"></a>Informes de tarjetas de crédito en Woodgrove Bank  
 La solución de arquitectura orientada a servicios es un servicio de informes de saldo de tarjetas de crédito para Woodgrove Bank. Aunque el banco es ficticio, no es el escenario, el escenario se basa en una aplicación cliente real, implementado.  
  
 En el escenario, las solicitudes de saldo de tarjeta de crédito proceden de dos orígenes:  
  
-   Una aplicación de respuesta interactiva de voz (IVR).  
  
-   Un cliente interactivo como una página Web o una aplicación cliente personalizada.  
  
 La solución recibe solicitudes de la aplicación de IVR a través de MQSeries. Administra las solicitudes del cliente interactivo a través de un servicio Web que utiliza HTTP y SOAP.  
  
 Las nuevas aplicaciones de arquitectura orientada a servicios tienen que trabajar con frecuencia con aplicaciones heredadas que usan tecnologías más antiguas y con aplicaciones modernas como sitios Web que consumen servicios Web. El escenario representa este requisito del mundo real, la aplicación de IVR representa una aplicación heredada, mientras la aplicación de cliente de servicio al cliente, es moderna.  
  
 La aplicación Woodgrove Bank utiliza datos de tres sistemas de servidor heredados para responder a las solicitudes:  
  
-   Una aplicación que proporciona el límite de crédito global. Es un sistema SAP en un gran sistema (mainframe).  
  
-   Un sistema de transacciones pendientes que informa del importe total de las transacciones pendientes en la cuenta. Es un sistema en un gran sistema (mainframe) o AS/400. La solución utiliza un servicio Web y Microsoft Host Integration Server (HIS) para comunicarse con el gran sistema (mainframe) o el sistema AS/400.  
  
-   Un sistema de seguimiento de pago que da el último pago realizado al sistema. Al sistema de seguimiento de pago se llega usando MQSeries.  
  
 Tras recopilar y compilar la información de los sistemas heredados, la solución envía la respuesta a la aplicación de origen, por tanto, al cliente.  
  
## <a name="business-requirements"></a>Requisitos empresariales  
 Puesto que la aplicación de informes de crédito responde en tiempo real a las solicitudes del cliente, debe tener una latencia baja para administrar las solicitudes con rapidez. Además, debe poder administrar también grandes cantidades de solicitudes simultáneas. La solución utiliza información confidencial y una interfaz pública, de manera que la seguridad es un preocupación importante. Finalmente, el servicio debe ser confiable.  
  
 Para obtener información acerca de cómo la solución cumple estos requisitos, consulte [desarrollar una solución orientada a servicios](../core/developing-a-service-oriented-solution.md).  
  
## <a name="performance-characteristics"></a>Características de rendimiento  
 Para cumplir los requisitos empresariales, el escenario tiene las siguientes características de rendimiento:  
  
-   Rendimiento sostenido de 40 solicitudes entrantes por segundo.  
  
-   Rendimiento máximo de 100 solicitudes entrantes por segundo.  
  
-   90 por ciento de las solicitudes para atender (dentro y fuera de BizTalk Server) en con menos de 1000 milisegundos.  
  
-   95 por ciento de las solicitudes para atender (dentro y fuera de BizTalk Server) en menos de 2.000 milisegundos.  
  
-   100 por ciento de las solicitudes para atender (dentro y fuera de BizTalk Server) en menos de 5000 milisegundos.  
  
> [!NOTE]
>  Estos tiempos no incluyen los tiempos de latencia de los sistemas de servidor.  
  
## <a name="three-versions-of-the-solution"></a>Tres versiones de la solución  
 Hay tres versiones de la solución:  
  
-   La versión de código auxiliar reemplaza todos los sistemas de servidor con código auxiliar. Este código auxiliar simula los sistemas de servidor. Esta versión proporciona un modo rápido de implementar y ejecutar la solución en un solo equipo.  
  
-   La versión de adaptador utiliza adaptadores de BizTalk para conectarse a sistemas de servidor. Esta versión es como se podría pensar en principio implementar la solución. Sin embargo, el envío de mensajes a los sistemas de servidor usando adaptadores supone una latencia importante a la hora de obtener de nuevo las solicitudes. Si bien los adaptadores por sí solos podrían ofrecer una latencia muy baja, la arquitectura distribuida de BizTalk Server requiere que los adaptadores se comuniquen con las instancias de host de la orquestación mediante el cuadro de mensajes. Esto produce acciones de ida y vuelta a la base de datos y afecta a los tiempos de latencia.  
  
-   La versión en línea reemplaza los adaptadores por código en línea que se comunica directamente con los sistemas de servidor. La versión en línea de la solución tiene la latencia más baja y el mayor rendimiento.  
  
 La guía de implementación proporciona instrucciones para crear e implementar todas las versiones de la solución, y también proporciona en cada versión una forma de simular la conexión a través de HIS con el sistema de transacciones pendientes. Para obtener información acerca de cómo crear e implementar la solución, vea [implementar la solución orientada a servicios](../core/deploying-the-service-oriented-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Solución orientada a servicios](../core/service-oriented-solution.md)