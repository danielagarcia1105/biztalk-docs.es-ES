---
title: Los servicios Web de rampa de itinerario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7551974-b9d2-4ae3-b54c-3aa5ba058e95
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e0f30d93514fded12d20a06d9fa27fbcd632bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980717"
---
# <a name="the-itinerary-on-ramp-web-services"></a>Los servicios Web de rampa de itinerario
El servicio Web de itinerarios es un itinerario en rampa que expone un método que permite a los clientes enviar los mensajes para las operaciones de ESB o procesamiento por el servicio de itinerarios y, después, en el destino de Microsoft BizTalk.  
  
 El servicio Web de itinerario pasa la carga a los componentes de canalización de itinerarios de ESB que valida el itinerario para comprobar que estos servicios se definen en el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuración. A continuación, el componente agrega las propiedades de contexto especial para el mensaje que contiene el itinerario validado.  
  
 En el caso de una genérica itinerario en rampa, no se proporciona un encabezado SOAP que contiene un itinerario durante el envío del mensaje. En consecuencia, se usa el componente de canalización de Selector de itinerarios de ESB en lugar del componente de canalización de itinerarios de ESB. El componente de canalización de Selector de itinerarios de ESB resuelve el itinerario basándose en una cadena de conexión de resolución predefinidos y proporciona la misma validación que proporciona el componente de canalización de itinerarios de ESB.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye dos variaciones del servicio de itinerarios para admitir tanto unidireccional y patrones de intercambio de mensajes de solicitud y respuesta. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF) de ambos servicios, y proporciona versiones genéricas de los servicios WCF.  
  
 Los nombres de los servicios de itinerario unidireccionales proporcionados son **ESB. ItineraryService**, **ESB. ItineraryServices.WCF**, y **ESB. ItineraryServices.Generic.WCF**.  
  
 Los nombres de los servicios de itinerario bidireccionales proporcionados son **ESB. ItineraryServices.Response**, **ESB. ItineraryServices.Response.WCF**, y **ESB. ItineraryServices.Generic.Response.WCF**.  
  
 Cada uno de los servicios Web de itinerario expone los métodos siguientes:  
  
- **SubmitRequest**. Para el servicio basados en ASMX, este método toma una instancia de la **XmlNode** clase que contiene el mensaje que se va a enviar. Para el servicio basado en WCF, este método toma una cadena XML que contiene el mensaje que se va a enviar.  
  
- **SubmitRequestResponse**. Para el servicio basados en ASMX, este método toma una referencia a una instancia de la **XmlNode** clase que contiene el mensaje para enviar y devuelve el mensaje de respuesta de la instancia de la **XmlNode** pasa a él. Para el servicio basado en WCF, este método toma una referencia a un **objeto** tipo que es una cadena XML que contiene el mensaje para enviar y devuelve una matriz de **XmlNodes** en el **objeto** que se pasó a él.  
  
  Para obtener más información sobre el uso de los servicios Web de itinerario, consulte [instalar y ejecutar el ejemplo de rampa de itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).  
  
> [!NOTE]
>  De forma predeterminada, los servicios Web de itinerario no están configurados para que requiera Secure Sockets Layer (SSL) cuando obtiene acceso a los clientes. Debe configurar el servicio para requerir SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor que hospeda la base de datos ESBExceptions con un nivel de red de IPSec y proceda permisos de lista (ACL) de control de acceso de nivel de archivo.