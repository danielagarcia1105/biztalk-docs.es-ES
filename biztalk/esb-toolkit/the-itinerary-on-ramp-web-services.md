---
title: Los servicios Web de itinerario en rampa | Documentos de Microsoft
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
ms.openlocfilehash: 36d3724a6cd57dca8157c05e95d9e196f0fb6cf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295436"
---
# <a name="the-itinerary-on-ramp-web-services"></a>Los servicios Web de itinerario en rampa
El servicio Web de itinerario es itinerario en rampa que expone un método que permite a los clientes enviar mensajes para las operaciones de ESB o procesamiento por el servicio de itinerario y, después, en el destino de Microsoft BizTalk.  
  
 El servicio Web de itinerario pasa la carga para los componentes de canalización de itinerario de ESB, que valida el itinerario para comprobar que estos servicios se definen en el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuración. A continuación, el componente agrega propiedades de contexto especial para el mensaje que contiene el itinerario validado.  
  
 En el caso de una genérica itinerario en rampa, no se proporcionó un encabezado SOAP que contiene un itinerario durante el envío del mensaje. En consecuencia, se utiliza el componente de canalización de Selector de itinerario de ESB en lugar del componente de canalización de itinerario ESB. El componente de canalización de Selector de itinerario ESB resuelve el itinerario basándose en una cadena de conexión de resolución predefinidos y proporciona la misma validación que proporciona el componente de canalización de itinerario ESB.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye dos variaciones de los servicios de itinerario para ser compatible con unidireccional y patrones de intercambio de mensajes de solicitud y respuesta. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene un ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF) de ambos de estos servicios, así como versiones genéricas de los servicios WCF.  
  
 Los nombres de los servicios de itinerarios unidireccionales proporcionados son **ESB. ItineraryService**, **ESB. ItineraryServices.WCF**, y **ESB. ItineraryServices.Generic.WCF**.  
  
 Los nombres de los servicios de itinerarios bidireccionales proporcionados son **ESB. ItineraryServices.Response**, **ESB. ItineraryServices.Response.WCF**, y **ESB. ItineraryServices.Generic.Response.WCF**.  
  
 Cada uno de los servicios Web de itinerario expone los métodos siguientes:  
  
-   **SubmitRequest**. Para el servicio basados en ASMX, este método toma una instancia de la **XmlNode** clase que contiene el mensaje que se va a enviar. Para el servicio basado en WCF, este método toma una cadena XML que contiene el mensaje que se va a enviar.  
  
-   **SubmitRequestResponse**. Para el servicio basados en ASMX, este método toma una referencia a una instancia de la **XmlNode** clase que contiene el mensaje que se va a enviar y devuelve el mensaje de respuesta de la instancia de la **XmlNode** pasa a se. Para el servicio basado en WCF, este método toma una referencia a un **objeto** tipo que es una cadena XML que contiene el mensaje que se va a enviar y devuelve una matriz de **XmlNodes** en la **objeto** que se pasó a él.  
  
 Para obtener más información acerca del uso de los servicios Web de itinerario, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).  
  
> [!NOTE]
>  De forma predeterminada, los servicios Web de itinerario no estén configurados para requerir Secure Sockets Layer (SSL) a los que tienen acceso los clientes. Debe configurar el servicio para requerir SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor que hospeda la base de datos de ESBExceptions con un nivel de red de IPSec y proceda permisos de lista (ACL) de control de acceso de nivel de archivo.