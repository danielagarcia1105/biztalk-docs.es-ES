---
title: Servicios Web ESB | Microsoft Docs
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
ms.openlocfilehash: fe1b2f6bc30982ea05717fd8e151997e2a3f90a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973365"
---
# <a name="esb-web-services"></a>Servicios Web ESB
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene los servicios Web siguientes:  
  
- <strong>Itinerario en rampa servicios Web.</strong> Estos servicios acepten los mensajes externos y envíe los mensajes para su procesamiento. El contenido de un itinerario contiene instrucciones de procesamiento y los metadatos que describen qué servicios se deben ejecutar. Servicios de enrutamiento definen los puntos de conexión a la que se debería enrutar el mensaje mientras que los servicios de transformación especifican cómo deben transformarse los mensajes. Estos servicios de soporte técnico unidireccionales y bidireccionales (solicitud-respuesta) de procesamiento; se proporcionan implementaciones de ASMX y Windows Communication Foundation (WCF). Los servicios Web de itinerario en rampa no son mensajes específicos del tipo, para que acepten cualquier tipo de mensaje.  
  
- <strong>Servicio Web de resolución.</strong> Este servicio permite a las aplicaciones externas llamar a Microsoft ESB resolución Framework para buscar los puntos de conexión ESB basadas en mecanismos de resolución compatibles con el marco de trabajo de resolución. El servicio también ofrece implementaciones de ASMX y WCF.  
  
- <strong>Servicio Web de transformación.</strong> Este servicio permite la ejecución de Microsoft BizTalk Server asigna sin la sobrecarga de persistencia de cuadro de mensaje, extender la funcionalidad de BizTalk Server ejecución mapa a las aplicaciones que no se basan en BizTalk Server. El servicio ofrece implementaciones de ASMX y WCF.  
  
- <strong>Servicio Web control de excepciones.</strong> Este servicio acepta los mensajes de excepción de orígenes externos y se normalizar rutas mediante la canalización del procesador de errores, realizar un seguimiento y publicar el mensaje de excepción en el Portal de administración de ESB. El servicio ofrece implementaciones de ASMX y WCF.  
  
- <strong>Servicio Web de UDDI.</strong> Este servicio permite a las aplicaciones y usuarios buscar puntos de conexión según el nombre del servicio, proveedor empresarial o categoría profesional; también permite manipular los proveedores de negocio, servicios, aplicaciones y a los usuarios y las categorías se almacenan en un Repositorio UDDI. Se trata de un servicio de infraestructura de clave utilizado por el Portal de administración de ESB y proveedores de terceros.  
  
- <strong>Servicio Web de las operaciones de BizTalk.</strong> Basados en ASMX este servicio expone información acerca de los hosts de BizTalk Server, orquestación, aplicaciones y estado de habilitación de usuarios y terceros a fácilmente una consulta para el estado de la aplicación y de host, independientemente de la ubicación de los equipos dentro de el grupo de BizTalk Server. Pueden incluir consultas de estado del mensaje y flujo, los cambios de estado, las instancias de servicio actual y los detalles del mensaje. También puede actualizar el servicio de ubicaciones de recepción. Se trata de un servicio de infraestructura de clave utilizado por el Portal de administración de ESB y proveedores de terceros.  
  
  Para obtener más información acerca de los servicios Web proporcionados como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], consulte [mediante los servicios Web de BizTalk ESB Toolkit](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).