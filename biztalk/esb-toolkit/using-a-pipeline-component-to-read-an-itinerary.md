---
title: Uso de un componente de canalización para leer un itinerario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e3b40c7-0f17-4d33-a26f-f51346a98be5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c03e4e48b125d7a8236c66ce36e458dd2d51a6f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991133"
---
# <a name="using-a-pipeline-component-to-read-an-itinerary"></a>Uso de un componente de canalización para leer un itinerario
Un mensaje que llega en una canalización de recepción puede contener metadatos en el encabezado SOAP que define sus requisitos de procesamiento (itinerario del lado cliente). Figura 1 ilustra el uso de los componentes de canalización de distribuidor de ESB e itinerarios de ESB.  

 ![Lectura del componente de canalización](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4-PipelineComponentRead")  

 **Figura 1**  

 **Ejemplo de un componente de canalización de itinerarios de ESB**  

 Un componente de canalización de itinerarios de ESB puede usarse para capturar los metadatos de un mensaje como propiedades de contexto que se pueden definir la transformación aplicada por el ESB.  

 Las secciones siguientes describen los pasos realizados por cada componente.  

## <a name="esb-itinerary-pipeline-component-process-steps"></a>Pasos del proceso de componente de canalización itinerarios de ESB  
 En el ejemplo que se muestra en la figura 1, el componente de canalización de itinerarios de ESB ejecuta los pasos siguientes:  

- Lee el encabezado SOAP de itinerario. La entidad envía establece el itinerario rellenando el encabezado SOAP cuando se envía el mensaje. Una serie de propiedades de contexto del mensaje de BizTalk representan el encabezado SOAP; Estas propiedades varían según el tipo de adaptador del servicio Web que se usa. Estos son los adaptadores de servicio Web pertinentes:  

  - **Adaptador de WCF.** Este adaptador analiza los encabezados SOAP y rellena las propiedades de contexto de mensaje de BizTalk aparece en la tabla siguiente.  


    |                                  Propiedades                                  |
    |------------------------------------------------------------------------------|
    |                             **Nombre = itinerario**                             |
    | **Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary** |

    > [!NOTE]
    >  De forma predeterminada, el adaptador de Windows Communication Foundation (WCF) utiliza el nombre raíz del esquema denominado ItineraryDescription.xsd (este esquema se usa para generar el encabezado SOAP de itinerarios de ESB) como el contexto de BizTalk **nombre** argumento, y usa el espacio de nombres de destino del esquema como el contexto de BizTalk **Namespace** argumento.  

  - **Adaptador de SOAP.** Este adaptador analiza los encabezados SOAP y rellena las propiedades de contexto de mensaje de BizTalk aparece en la tabla siguiente.  


    |                              Propiedades                              |
    |----------------------------------------------------------------------|
    |                         **Nombre = itinerario**                         |
    | **Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader** |

    > [!NOTE]
    >  De forma predeterminada, el adaptador de SOAP utiliza el nombre raíz del esquema denominado Itinerary.xsd (este esquema se usa para generar el encabezado SOAP de itinerarios de ESB) como el contexto de BizTalk **nombre** argumento y utiliza el espacio de nombres del encabezado SOAP como el Contexto de BizTalk **Namespace** argumento.  

- Quita el valor original de itinerarios el contexto del mensaje.  

- Valida el itinerario y establece propiedades específicas para preestablecer valores predeterminados si son null en el itinerario; Por ejemplo:  

  - Si el recuento de servicio es menor que 1, el componente produce una excepción.  

  - El componente establece los atributos de itinerarios raíz con los valores para la cuenta de servicio, el identificador (**Uuid**), la hora de inicio (**BeginTime**), y si se trata de una solicitud unidireccional o bidireccional (**IsRequestResponse**).  

  - El componente valida los servicios, Establece los identificadores, Establece la instancia de servicio actual (el servicio para procesar a continuación) y valida los solucionadores asociados.  

  - El componente define el segmento de BizTalk del itinerario mediante las siguientes propiedades:  

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
    |**ServiceType**|Establecer en **orquestación** o **mensajería**|  
    |**IsRequestResponse**|Establecer en **True** o **False**|  
    |**ServiceState**|Establecido en **pendiente**|  

## <a name="esb-dispatcher-pipeline-component-process-steps"></a>Pasos de proceso de componente de canalización ESB distribuidor  
 En el ejemplo que se muestra en la figura 1, el componente de canalización de distribuidor de ESB ejecuta los pasos siguientes:  

- Administra la ejecución de todos los pasos de itinerarios de tipo **mensajería** y hace avanzar el itinerario. El componente de distribuidor de ESB es con reconocimiento de ubicación y ejecuta la lógica basada en su ubicación en el ciclo de procesamiento de mensajería, lo que sería **recepción entrante, enviar transmitir**, **enviar entrada**, o **Recepción saliente**. El componente de canalización de distribuidor de ESB invoca servicios de mensajería itinerarios de ESB especificados en el archivo Esb.config. De forma predeterminada, las propiedades de configuración de este componente para el enrutamiento y transformación están asociadas con los siguientes servicios:  

  - **Microsoft.Practices.ESB.Services.Transform.** Este servicio ejecuta asignaciones de BizTalk en la carga de un mensaje entrante. El servicio valida los requisitos de transformación y actualiza las propiedades de contexto de BizTalk que contienen el nombre de la especificación de documento y el tipo de mensaje. El distribuidor de ESB este servicio se ejecuta sólo si éste es el nombre del servicio de transformación, tal como aparece en la propiedad correspondiente del componente de canalización de distribuidor de ESB.  

  - <strong>Microsoft.Practices.ESB.Services.Routing.</strong> Este servicio utiliza la resolución y el marco de proveedores de adaptador para establecer la información de enrutamiento de punto de conexión adecuado. El distribuidor de ESB este servicio se ejecuta sólo si éste es el nombre del servicio de enrutamiento, tal como aparece en la propiedad correspondiente del componente de canalización de distribuidor de ESB.
