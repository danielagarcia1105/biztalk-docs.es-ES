---
title: Uso de un componente de canalización para seleccionar un itinerario existente | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b93c5cb6-071f-485d-b0bb-22f95bafa3d0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aceef4385652918ee7326709e7838776501e885
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975501"
---
# <a name="using-a-pipeline-component-to-select-an-existing-itinerary"></a>Uso de un componente de canalización para seleccionar un itinerario existente
## <a name="esb-itinerary-selector-pipeline-component"></a>Componente de canalización de Selector de itinerarios de ESB  
 Se envían mensajes enviados mediante genéricas itinerarios con rampas sin un encabezado de itinerarios. Para resolver el itinerario adecuado y adjuntarlo al mensaje entrante, la vía debe proporcionar un mecanismo que puede configurarse para tener acceso a los itinerarios desde un repositorio central.  

 El componente de canalización de Selector de itinerarios de ESB usa una cadena de conexión de la resolución, junto con los solucionadores especializados, para resolver el contenido de un itinerario de servidor almacenado en un repositorio central (de forma predeterminada, SQL Server).  

 Cuando se usa el componente de canalización de Selector de itinerarios de ESB en WCF rampas junto con la resolución de itinerario estático, el nombre y la versión del itinerario solicitado por el cliente (tal como está representada en el encabezado SOAP) se recupera del contexto del mensaje y se utiliza para seleccionar el itinerario adecuado.  

 De forma predeterminada, el componente de canalización de Selector de itinerarios de ESB reside en los siguientes procesos:  

- ItinerarySelectReceive  

- ItinerarySelectReceivePassthrough  

- ItinerarySelectReceiveXml  

- ItinerarySelectSendReceive  

  Las secciones siguientes describen los pasos realizados por cada componente.  

## <a name="esb-itinerary-selector-pipeline-component-processing-steps"></a>Pasos de procesamiento de componente de canalización de Selector de itinerarios de ESB  
 El componente de canalización de Selector de itinerarios de ESB ejecuta los pasos siguientes:  

- La entidad envía envía un mensaje para su procesamiento. El componente Selector de itinerarios utiliza a una resolución especificada como una cadena de conexión de la propiedad, configurada por el desarrollador, para determinar y seleccionar el itinerario adecuado desde el almacén de itinerarios, según el contexto o el contenido del mensaje.  

- Valida el itinerario y establece propiedades específicas para preestablecer valores predeterminados si son null en el itinerario; Por ejemplo:  

  - Si el recuento de servicio es menor que 1, el componente produce una excepción.  

  - El componente establece los atributos de itinerarios raíz con los valores para la cuenta de servicio, el identificador (**Uuid**), la hora de inicio (**BeginTime**), y si se trata de una solicitud unidireccional o bidireccional (**IsRequestResponse**).  

  - El componente valida los servicios, Establece los identificadores, Establece la instancia de servicio actual (el servicio para procesar a continuación) y valida los solucionadores asociados.  

  - El componente define el segmento de Microsoft BizTalk Server del itinerario mediante las siguientes propiedades:  

    -   **correlationToken**  

    -   **reqRespTransmitPipelineID**  

    -   **interchangeId**  

    -   **receiveInstanceId**  

    -   **epmRRCorrelationToken**  

  - El componente escribe el itinerario modificado las propiedades de contexto de mensaje de BizTalk aparece en la siguiente tabla con las propiedades definidas en el esquema del sistema-Properties.xsd.  


    |                                           Propiedades                                           |
    |------------------------------------------------------------------------------------------------|
    |                                   **Nombre = ItineraryHeader**                                   |
    | **Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties** |


  - El componente promociona las cuatro propiedades de contexto de BizTalk aparece en la tabla siguiente con los valores definidos en el esquema del sistema-Properties.xsd.  

    |Property|Valor|  
    |--------------|-----------|  
    |**ServiceName**|El nombre de la instancia actual del servicio definido en el itinerario.|  
    |**ServiceType**|Establecer en **orquestación** o **mensajería**.|  
    |**IsRequestResponse**|Establecer en **True** o **False**.|  
    |**ServiceState**|Establecido en **pendiente**.|  

## <a name="esb-dispatcher-pipeline-component-process-steps"></a>Pasos de proceso de componente de canalización ESB distribuidor  
 El componente de canalización de distribuidor de ESB ejecuta los pasos siguientes:  

-   Administra la ejecución de todos los pasos de itinerarios de tipo **mensajería** y hace avanzar el itinerario. El componente de distribuidor de ESB es con reconocimiento de ubicación y ejecuta la lógica basada en su ubicación en el ciclo de procesamiento de mensajería, lo que sería **recibir entrada**, **enviar transmitir**, **enviar Entrada**, o **recibir salida**. El componente de canalización de distribuidor de ESB invoca servicios de mensajería itinerarios de ESB especificados en el archivo Esb.config. De forma predeterminada, las propiedades de configuración de este componente para el enrutamiento y transformación están asociadas con los siguientes servicios:  

    -   **Microsoft.Practices.ESB.Services.Transform**. Este servicio ejecuta asignaciones de BizTalk en la carga de un mensaje entrante. El servicio valida los requisitos de transformación y actualiza las propiedades de contexto de BizTalk que contienen el nombre de la especificación de documento y el tipo de mensaje. El distribuidor de ESB este servicio se ejecuta sólo si éste es el nombre del servicio de transformación, tal como aparece en la propiedad correspondiente del componente de canalización de distribuidor de ESB.  

    -   **Microsoft.Practices.ESB.Services.Routing.** Este servicio utiliza la resolución y el marco de proveedores de adaptador para establecer la información de enrutamiento de punto de conexión adecuado. El distribuidor de ESB este servicio se ejecuta sólo si éste es el nombre del servicio de enrutamiento, tal como aparece en la propiedad correspondiente del componente de canalización de distribuidor de ESB.