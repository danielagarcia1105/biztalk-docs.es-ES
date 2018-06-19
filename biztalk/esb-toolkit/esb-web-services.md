---
title: Servicios Web ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c122ecdd-344a-4f76-9c73-bf692d479c09
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e6f59770e14e14ed9599d0c26bae187f340e59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294380"
---
# <a name="esb-web-services"></a>Servicios Web ESB
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene los servicios Web siguientes:  
  
-   **Itinerario en rampa servicios Web.** Estos servicios acepte mensajes externos y enviar los mensajes para su procesamiento. El contenido de un itinerario contiene instrucciones de procesamiento y los metadatos que describen qué servicios se deben ejecutar. Servicios de enrutamiento definen los puntos de conexión a la que se debería enrutar el mensaje mientras los servicios de transformación especifican cómo se deben transformar los mensajes. Estos servicios de soporte técnico unidireccionales y bidireccionales (solicitud-respuesta) procesamiento; se proporcionan implementaciones de ASMX y Windows Communication Foundation (WCF). Los servicios Web de itinerario en rampa no son mensajes específicos de tipo, por lo que acepte cualquier tipo de mensaje.  
  
-   **Servicio Web de resolución.** Este servicio permite que las aplicaciones externas llamar el marco de trabajo de la resolución de ESB de Microsoft para buscar los puntos de conexión ESB en función de los mecanismos de resolución admitidos por el marco de trabajo de resolución. El servicio también ofrece las implementaciones de ASMX y WCF.  
  
-   **Servicio Web de transformación.** Este servicio permite la ejecución de Microsoft BizTalk Server asigna sin la sobrecarga de persistencia de cuadro de mensaje, extender la capacidad de BizTalk Server en ejecución de mapa a las aplicaciones que no se basan en BizTalk Server. El servicio proporciona las implementaciones de ASMX y WCF.  
  
-   **Servicio de control Web de excepción.** Este servicio acepta los mensajes de excepción de orígenes externos y se normalizar, realizar un seguimiento y publicar el mensaje de excepción en el Portal de administración de ESB rutas mediante la canalización de procesador de error. El servicio proporciona las implementaciones de ASMX y WCF.  
  
-   **Servicio Web de UDDI.** Este servicio permite a las aplicaciones y usuarios buscar los puntos de conexión basadas en el nombre del servicio, el proveedor empresarial o la categoría de business; también permite manipular los proveedores de negocio, servicios, aplicaciones y a los usuarios y categorías se almacenan en un Repositorio UDDI. Se trata de un servicio de infraestructura de clave utilizado por el Portal de administración de ESB y proveedores de terceros.  
  
-   **Servicio Web de las operaciones de BizTalk.** Basados en ASMX este servicio expone información acerca de los hosts de BizTalk Server, orquestación, aplicaciones y estado, lo que permite a los usuarios y terceros fácilmente consultar el estado de aplicación y de host, independientemente de la ubicación de los equipos dentro de el grupo de BizTalk Server. Pueden incluir consultas de estado del mensaje y flujo, cambios de estado, las instancias de servicio actual y detalles del mensaje. También puede actualizar el servicio de ubicaciones de recepción. Se trata de un servicio de infraestructura de clave utilizado por el Portal de administración de ESB y proveedores de terceros.  
  
 Para obtener más información acerca de los servicios Web proporcionados como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], consulte [mediante los servicios Web de BizTalk ESB Toolkit](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).