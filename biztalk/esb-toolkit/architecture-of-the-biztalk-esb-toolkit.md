---
title: Arquitectura del Kit de herramientas ESB de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41674f5-5ea4-4a8f-a270-b67fd6854028
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a701b2c0170b8687e48ff61c369ac25ef41ab6bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999389"
---
# <a name="architecture-of-the-biztalk-esb-toolkit"></a>Arquitectura del Kit de herramientas ESB de BizTalk
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consta de una serie de interoperación de los componentes que admiten e implementan un entorno de mensajería con acoplamiento flexible que resulta más fácil crear aplicaciones empresariales basadas en mensajes. Los servicios y componentes se dividen de forma natural en las siguientes siete categorías:  
  
- **Servicios Web.** Estos exponen servicios internos, como el de itinerario de procesamiento, administración de excepciones, la resolución de extremos y asignaciones, las operaciones de BizTalk Server, interoperación de Universal Description, Discovery and Integration (UDDI) y transformación del contenido del mensaje .  
  
- **Servicios de itinerario.** Estas incluyen servicios basados en mensajería y orquestación para realizar las transformaciones y enrutamiento de mensajes. Puede crear servicios personalizados que participan en el procesamiento de itinerario. Estas incluyen servicios basados en mensajería y orquestación para realizar las transformaciones y enrutamiento de mensajes. Puede crear servicios personalizados que participan en el procesamiento de itinerario.  
  
- **Itinerarios con rampas.** Estos recepción los mensajes externos, adjuntar el itinerario adecuado para cada mensaje y realizan el procesamiento de itinerarios; usan el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y el marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y los metadatos.  
  
- **Con rampas.** A diferencia de itinerarios con rampas, estos recibirán los mensajes externos en una variedad de formatos y los transportes, como HTTP, Java Message Service (JMS), IBM WebSphere MQ (WMQ), protocolo de transferencia de archivos (FTP), archivos sin formato y XML. Son típicos de BizTalk Server ubicaciones de recepción que, opcionalmente, use el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes de canalización de interoperabilidad y la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y el marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y los metadatos.  
  
- **Rampas.** Estos implementan puertos de envío para la entrega de mensajes con formatos y los transportes como WCF, JMS, WMQ, FTP, HTTP, archivo sin formato, XML o cualquier otros formatos personalizados. Son los puertos de envío dinámicos que son el enlace directo al cuadro de mensaje y, opcionalmente, utilizan el servidor BizTalk Server típico el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes de canalización de interoperabilidad y la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y el marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y metadatos.  
  
- **Marco de administración de excepciones.** Esto incluye el servicio Web de excepción, la API de administración de excepciones y componentes que enriquecen, procesarán y pasan los detalles de la excepción en el Portal de administración de ESB.  
  
- **Portal de administración de ESB.** Esta aplicación de ejemplo proporciona el aprovisionamiento del registro, mediación de excepción, notificación de alerta y análisis.  
  
  Muchos de estos componentes y servicios se basan en las características implementadas por BizTalk Server, como los motores de orquestación, transformación y las reglas de negocios y la base de datos de cuadro de mensaje. Figura 1 muestra una vista esquemática de las categorías, los componentes y servicios que se producen normalmente dentro de cada categoría, y los componentes principales del sistema de BizTalk Server utilizan por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
  ![Arquitectura ESB](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
  **Figura 1**  
  
  **La arquitectura y los componentes de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>Funcionamiento del kit de herramientas de BizTalk ESB  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] acepta mensajes de entrada y trabaja en ellos, quizás (pero no siempre) mediante la realización de procesos como la transformación, personalizado de enrutamiento, o cualquier otro proceso definido. Para especificar las operaciones necesarias, los componentes de procesamiento principales requieren cada mensaje para tener una lista de distribución que contiene instrucciones asociadas o metadatos que definen los procesos que se va a aplicar y las tareas se ejecuten con el contenido del mensaje. Estas listas de distribución se conocen como itinerarios pueden ser automáticamente resuelto recuperados de un repositorio central y, adjunto a un mensaje cuando se recibe una vía rápida.  
  
 Este enfoque slip enrutamiento proporciona un acoplamiento entre servicios, lo que significa que ESB no requiere conocimiento previo del procesamiento específico para cada mensaje. Solo tiene que saber qué es el intervalo posible de procesos y cómo aplicar cada proceso. La amplia variedad de opciones para especificar los procesos disponibles y la asignación entre los procesos y las instrucciones dentro de los mensajes proporciona un mecanismo flexible para configurar y ajustar el comportamiento, sin requerir cambios en el código ni la nueva implementación de componentes.  
  
## <a name="design-patterns"></a>Patrones de diseño  
 La arquitectura que utiliza ESB, donde los procesos del depósito mensajes en la base de datos de cuadro de mensaje y suscriptores recogerlos en función de una instrucción de procesamiento en el mensaje, implementa el patrón de diseño de la máquina de Estados de forma efectiva. Además, ESB implementa y expone su funcionalidad básica de una manera orientada a servicios, incluyendo a aplicaciones externas a través de un conjunto de servicios Web principales.  
  
 Este enfoque de acoplamiento flexible para el diseño de BizTalk Server y [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]-aplicaciones basadas en da como resultado soluciones muy flexibles y se ha convertido en una práctica recomendada aceptados en el sector.