---
title: En pendientes y desactivar pendientes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0cce5d2-f16f-4bda-94ac-20c4f457cfc7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0aafa69315dba07219ad8510c77cdc9de2d4bce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="on-ramps-and-off-ramps"></a>En pendientes y desactivar pendientes
En un entorno donde [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] está implementado, BizTalk ubicación de recepción responsable de recibir los mensajes destinados a ESB se conoce como "en rampa." Para configurar una ubicación de recepción de BizTalk estándar a ESB en rampa, asociar la ubicación de recepción con una de las canalizaciones que se proporciona como parte del Kit de herramientas y, a continuación, configure correctamente los componentes de dicha canalización para determinar o leer el itinerario para el mensaje entrante, según el escenario.  
  
 Un ESB "fuera de rampa" corresponde a un puerto de envío dinámico de BizTalk. Tal y como se está procesando un itinerario, se promocionan valores a las propiedades de contexto del mensaje asociado con el esquema del sistema-Properties.xsd. BizTalk publicación / suscripción utiliza mecanismo estos promocionan propiedades para enrutar un mensaje a través de un dinámicas de puerto de envío (fuera de rampa) para completar una entrega de mensajes.  
  
 En la tabla siguiente se enumera las en-pendientes que se proporcionan con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
|Nombre|Patrón de intercambio de mensajes|**Description**|  
|----------|------------------------------|---------------------|  
|ESB. ItineraryServices|Unidireccional|ASMX en rampa; espera contenido itinerario de ESB en el encabezado SOAP.|  
|ESB. ItineraryServices.Response|Solicitudes y respuestas|ASMX en rampa; espera contenido itinerario de ESB en el encabezado SOAP.|  
|ESB. ItineraryServices.WCF|Unidireccional|Windows Communication Foundation (WCF) en rampa; espera referencia itinerario de ESB en el encabezado SOAP.|  
|ESB. ItineraryServices.Response.WCF|Solicitudes y respuestas|WCF en rampa; espera referencia itinerario de ESB en el encabezado SOAP.|  
|ESB. ItineraryServices.Generic.WCF|Unidireccional|WCF en rampa; espera que sólo el mensaje de solicitud.|  
|ESB. ItineraryServices.Generic.Response.WCF|Solicitudes y respuestas|WCF en rampa; espera que sólo el mensaje de solicitud.|  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]en-pendientes que no son que asmx debe configurarse para seleccionar itinerarios de ESB. Para obtener más información sobre cómo seleccionar un itinerario ESB, consulte [usando un componente de canalización para seleccionar una existente itinerario](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md).