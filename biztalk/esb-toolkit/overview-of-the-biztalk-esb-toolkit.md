---
title: Información general sobre el Kit de herramientas ESB en BizTalk Server | Microsoft Docs
description: Explicación del Kit de herramientas de ESB, y lo que hace en BizTalk Server
caps.latest.revision: 6
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e190b34-40bc-4f27-9b4f-56e98591e1d4
ms.author: mandia
ms.openlocfilehash: 404e93739d45cbca0235990dc7d2014bf38e0a84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008789"
---
# <a name="what-is-the-biztalk-esb-toolkit"></a>¿Qué es el Kit de herramientas de ESB de BizTalk

## <a name="overview"></a>Información general
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía las capacidades de BizTalk Server para admitir una arquitectura de mensajería ligeramente acoplada. La mayoría de los desarrolladores están familiarizados con los paradigmas de desarrollo orientado a código, procedimientos u orientada a objetos. Sin embargo, al empezar a desarrollar soluciones de BizTalk, los desarrolladores tienden a pasar por alto las capacidades orientadas a mensajes de BizTalk Server.  
  
 BizTalk Server incluye un mecanismo eficaz de publicación/suscripción que funciona creando y rellenando las suscripciones. Cuando llega un mensaje nuevo en la base de datos de cuadro de mensaje de BizTalk, un agente de mensaje identifica los suscriptores y envía el mensaje a los puntos de conexión que tienen suscripciones. Las suscripciones se pueden crear de varias maneras, como enlazar una orquestación a un puerto de recepción, tener una recepción correlacionada espera un mensaje, o crear un puerto de envío con una condición de filtro que coincide con una propiedad del mensaje (por ejemplo, el tipo, la recepción punto o el valor de una propiedad enrutable).  
  
 Al proporcionar este enfoque eficaz y escalable, BizTalk Server permite a los desarrolladores crear una serie de los subprocesos discretos, definir los tipos de mensajes que desencadenan su invocación y no preocuparse acerca de la secuencia. Un proceso iniciado por la llegada de un mensaje realice su procesamiento en el mensaje; Después de procesar el mensaje, puede entregar este u otro mensaje a la base de datos de cuadro de mensaje, que, a su vez, puede activar uno o varios subprocesos.  
  
 Microsoft proporciona los bloques de creación clave que son necesarios para crear infraestructuras de completa orientada a servicios, incluidos Windows Server, BizTalk Server y el .NET Framework. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] se basa en el servidor BizTalk Server porque proporciona la base para los servicios ESB más comunes, incluidos los siguientes:  
  
-   Enrutamiento de mensajes  
  
-   Validación de mensajes  
  
-   Transformación de mensajes  
  
-   Marco extensible para la conectividad  
  
-   Orquestación de servicios  
  
-   Motor de reglas de negocios  
  
-   La actividad económica  
  
-   Y servicios Web WS-* integración (adaptador de WCF)  

## <a name="core-capabilities"></a>Capacidades principales  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía la funcionalidad de BizTalk Server para proporcionar una gama de nuevas capacidades sobre la creación de aplicaciones robustas, conectadas y orientada a servicios. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] trata los componentes de BizTalk Server como unidades de trabajo que se pueden conectar, según sea necesario formar débilmente acoplados soluciones. Los siguientes son algunas de las capacidades básicas que la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona para mejorar las capacidades de BizTalk Server:  
  
- **Por mediación de directivas.** El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:  
  
  - Proporciona enrutamiento basado en itinerarios que admite la composición de servicio ligero en el momento de publicación de mensajes. Este enfoque permite la detección dinámica de extremos de servicio y los requisitos de mediación para enrutar el mensaje mediante un registro del servicio o la directiva de reglas de negocios.  
  
  - Agrega compatibilidad para centralizar la directiva de enrutamiento mediante itinerarios del lado servidor que se resuelven dinámicamente y se agregan al contexto del mensaje después de un mensaje basado en itinerarios se recibe. Administración de itinerarios en una ubicación central permite el procesamiento de mensajes de los clientes que desconocen por completo de cómo se enrutan las solicitudes.  
  
  - Usa una versión mejorada de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y el marco de proveedores de adaptador, lo que permite la resolución dinámica de los puntos de conexión y requisitos de transformación; esto desacopla eficazmente el consumidor de los servicios.  
  
- **Conexión de sistemas.** El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:  
  
  -   Proporciona componentes de canalización que normalizan los espacios de nombres de mensaje XML.  
  
  -   Se integra con JMS a través del adaptador de WebSphere MQ para BizTalk Server.  
  
  -   Facilita que los patrones de intercambio de mensajes que permiten la agregación de servicio dinámico, el enrutamiento de mensajes, validación de mensajes y transformación de mensajes.  
  
  -   Admite la detección de punto de conexión del servicio de registro y la integración de repositorio con UDDI 3.0.  
  
  -   Admite el enrutamiento de mensajes a través de adaptadores de línea de negocio (LOB) mediante el adaptador de BizTalk de WCF-Custom para BizTalk Server.  
  
- **Administración y supervisión.** El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:  
  
  -   Proporciona herramientas y el marco de administración de excepciones.  
  
  -   Facilita la reparación de mensajes y volver a enviar mediante el portal de administración, se incluye como una aplicación de ejemplo. Esta aplicación Web también es compatible con notificaciones de correo electrónico personalizable cuando se produce un error específico.  
  
  -   Permite la publicación, administración e integración de punto de conexión y del registro de BizTalk Server.  
  
  -   Proporciona un repositorio centralizado de itinerarios de lado servidor con control de versiones.  
  
  -   Admite informes y análisis para aplicaciones de BizTalk Server.  
  
  -   Incluye componentes de la actividad económica para realizar un seguimiento de ejecución de servicio de itinerarios, incluida la hora de inicio, hora de finalización y la secuencia de mediación de servicio.  
  
- **Gobierno de SOA.** El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:  
  
  -   Se integra con las soluciones de gobierno de SOA de terceros, incluidos a los agentes de administración integrada de servidor de BizTalk de AmberPoint y el Software de SOA.  

> [!TIP]
> [Descripción de BizTalk Server](../core/understanding-biztalk-server.md) proporciona más detalles sobre el motor de mensajería y mucho más.

## <a name="get-some-help"></a>Obtener ayuda
Obtener ayuda y ayudar a otros usuarios en el [foros de BizTalk ESB Toolkit](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409).

## <a name="next-steps"></a>Pasos siguientes
[Contenido del kit de herramientas de BizTalk ESB](contents-of-the-biztalk-esb-toolkit.md)  
