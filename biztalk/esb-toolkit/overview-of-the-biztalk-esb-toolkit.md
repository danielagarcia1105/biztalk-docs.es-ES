---
title: "Información general sobre el Kit de herramientas ESB en BizTalk Server | Documentos de Microsoft"
description: "Explicación del Kit de herramientas de ESB, y lo que hace en BizTalk Server"
caps.latest.revision: "6"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e190b34-40bc-4f27-9b4f-56e98591e1d4
ms.author: mandia
ms.openlocfilehash: 9ce0bbe3710530a63127701447db87b0a3135b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-biztalk-esb-toolkit"></a>¿Qué es el Kit de herramientas de ESB de BizTalk

## <a name="overview"></a>Información general
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía las capacidades de BizTalk Server para admitir una arquitectura de mensajería con acoplamiento flexible. Mayoría de los desarrolladores está familiarizada con los paradigmas de desarrollo orientado al código, procedimientos u orientada a objetos. Sin embargo, al empezar a desarrollar soluciones de BizTalk, los desarrolladores suelen pasar por alto las capacidades orientado a mensajes de BizTalk Server.  
  
 BizTalk Server incluye un mecanismo eficaz de publicación/suscripción que funciona mediante la creación y rellenar las suscripciones. Cuando llega un mensaje nuevo en la base de datos de cuadro de mensaje de BizTalk, un agente de mensaje identifica los suscriptores y envía el mensaje a los puntos de conexión que tienen suscripciones. Se pueden crear suscripciones de varias maneras, incluyendo enlazar una orquestación a un puerto de recepción, tener una recepción correlacionada espera un mensaje, o crear un puerto de envío con una condición de filtro que coincide con una propiedad del mensaje (por ejemplo, el tipo, la recepción punto, o el valor de una propiedad enrutable).  
  
 Al proporcionar este enfoque eficaz y escalable, BizTalk Server permite a los desarrolladores crear una serie de subprocesos discretos, defina los tipos de mensajes que desencadenan su invocación y no se preocupe acerca de la secuencia. Un proceso iniciado por la llegada de un mensaje realice su procesamiento en el mensaje; Después de procesar el mensaje, puede entregar este u otro mensaje a la base de datos de cuadro de mensaje, que a su vez, puede activar uno o varios subprocesos.  
  
 Microsoft proporciona los bloques de creación claves que son necesarios para la creación de infraestructuras de orientada al servicio completa, incluido Windows Server, .NET Framework y BizTalk Server. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] se basa en BizTalk Server porque proporciona la base para los servicios ESB más comunes, incluidos los siguientes:  
  
-   Enrutamiento de mensajes  
  
-   Validación del mensaje  
  
-   Transformación de mensajes  
  
-   Marco extensible para la conectividad  
  
-   Orquestación de servicios  
  
-   Motor de reglas de negocios  
  
-   Supervisión de la actividad de negocio  
  
-   Y servicios Web WS-* integración (adaptador de WCF)  

## <a name="core-capabilities"></a>Capacidades principales  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía la funcionalidad de BizTalk Server proporciona una gama de nuevas capacidades que se centra en crear aplicaciones sólidas, conectadas, orientadas a servicios. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] trata los componentes de BizTalk Server como unidades de trabajo que se puede conectar, según sea necesario formar débilmente acoplados soluciones. Los siguientes son algunas de las capacidades básicas de que el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona para mejorar las capacidades de BizTalk Server:  
  
-   **Controlada por mediación de directivas.** El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:  
  
    -   Proporciona el enrutamiento basado en itinerario que admite composición ligera del servicio en el momento de publicación de mensajes. Este enfoque permite la detección dinámica de extremos de servicio y requisitos de mediación para enrutar los mensajes con un registro de servicio o la directiva de reglas de negocios.  
  
    -   Agrega compatibilidad para centralizar la directiva de enrutamiento mediante itinerarios de servidor que se resuelve dinámicamente y se agregan al contexto del mensaje una vez un mensaje basado en itinerario recibido. La administración de itinerarios en una ubicación central permite el procesamiento de mensajes de los clientes que están completamente sin tener en cuenta cómo se enrutan sus solicitudes.  
  
    -   Utiliza una versión mejorada de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y marco de proveedores de adaptador, que permite una resolución dinámica de los puntos de conexión y los requisitos de transformación; esto desacopla eficazmente el consumidor de los servicios.  
  
-   **Conexión de sistemas.** El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:  
  
    -   Proporciona componentes de canalización que normalizan los espacios de nombres de mensaje XML.  
  
    -   Se integra con JMS a través del adaptador de WebSphere MQ para BizTalk Server.  
  
    -   Facilita los patrones de intercambio de mensajes que permiten la agregación de servicios dinámicos, enrutamiento de mensajes, validación de mensajes y transformación de mensajes.  
  
    -   Admite la detección de punto de conexión de servicio de registro y la integración con el repositorio mediante UDDI 3.0.  
  
    -   Admite el enrutamiento de mensajes a través de adaptadores de línea de negocio (LOB) con el adaptador de BizTalk de WCF-Custom para BizTalk Server.  
  
-   **Administración y supervisión.** El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:  
  
    -   Proporciona herramientas y el marco de administración de excepciones.  
  
    -   Facilita la reparación de mensajes y reenvío mediante el portal de administración, como una aplicación de ejemplo. Esta aplicación Web también admite las notificaciones de correo electrónico personalizable cuando se produce un error específico.  
  
    -   Permite la publicación, la administración y la integración de punto de conexión y el registro de BizTalk Server.  
  
    -   Proporciona un repositorio centralizado de itinerarios con control de versiones de servidor.  
  
    -   Admite informes y análisis de aplicaciones de BizTalk Server.  
  
    -   Incluye componentes de supervisión de la actividad de negocio para realizar el seguimiento de ejecución del servicio itinerarios, incluidos la hora de inicio, hora de finalización y la secuencia de mediación de servicio.  
  
-   **Gobierno de SOA.** El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:  
  
    -   Se integra con soluciones de regulación de SOA de terceros, incluidos los agentes de administración integrada de BizTalk Server de AmberPoint y Software de SOA.  

> [!TIP]
> [Descripción de BizTalk Server](../core/understanding-biztalk-server.md) contiene más detalles sobre el motor de mensajería y mucho más.

## <a name="get-some-help"></a>Obtener ayuda
Obtener ayuda y ayudar a otras personas en la [Kit de herramientas de BizTalk ESB foros](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409).

## <a name="next-steps"></a>Pasos siguientes
[Contenido del Kit de herramientas de ESB de BizTalk](contents-of-the-biztalk-esb-toolkit.md)  
