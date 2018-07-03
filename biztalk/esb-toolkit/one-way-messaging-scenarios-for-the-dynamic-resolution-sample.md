---
title: Escenarios de mensajería unidireccional para el ejemplo de resolución dinámica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38237840-e957-4298-84c9-700ec72f2bc5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 359b91a1a5da9ce435d3d9aa5884d6928d0e0a9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987541"
---
# <a name="one-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>Escenarios de mensajería unidireccional para el ejemplo de resolución dinámica
Este tema muestra cómo se pueden ejecutar los escenarios de mensajería unidireccionales para el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplo de resolución dinámica.  

 **Para ejecutar los escenarios de mensajería unidireccionales para el ejemplo de resolución dinámica**  

1. Antes de ejecutar este ejemplo por primera vez, asegúrese de que la recepción ubicación URL señala al directorio adecuado. Especifique el \Source\Samples\DynamicResolution\Test\Filedrop\In subcarpeta origen para el DynamicResolution_FILE la ubicación de recepción. Además, asegúrese de que existe el puerto de envío dinámico denominado DynamicResolutionOneWay.  

   > [!NOTE]
   >  El ejemplo de resolución dinámica usa el mecanismo de resolución dinámica para enviar mensajes a la carpeta de salida, el sitio FTP o la cola de MQSeries. Este es el motivo por el puerto de envío estático no está definido para este ejemplo. El componente de resolución dinámica recupera la dirección URL de salida de la resolución y la ubicación de recepción del adaptador de marco de proveedores cuando se llama por la canalización ESBReceiveXml, que se configura en el DynamicResolution_FILE.  

2. Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de Microsoft BizTalk para iniciarlo.  

3. Decidir qué ejemplo que desea ejecutar. Unidireccionales mensajería ejemplos (excepto el que utiliza a la resolución de XPATH) use el archivo que naorderdoc.XML ubicado en la carpeta \Source\Samples\DynamicResolution\Test\Data como entrada a la ubicación de recepción denominada DynamicResolution_FILE. Hay siete ejemplos de mensajes unidireccionales, cada uno representado por un archivo de enlace único. Las tablas siguientes muestran estos ejemplos, con sus descripciones y los archivos de enlace asociada.  

   |Archivo de entrada al archivo de salida mediante la resolución estática|  
   |-------------------------------------------------------------|  
   |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
   |Establece las asignaciones de forma estática en el puerto de recepción.|  
   |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  

   |Archivo de entrada al archivo de salida mediante la resolución UDDI|  
   |-----------------------------------------------------------|  
   |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
   |Establece las asignaciones de forma estática en el puerto de recepción.|  
   |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  

   |Archivo de entrada al archivo de salida mediante la resolución UDDI con una clave de servicio UDDI|  
   |----------------------------------------------------------------------------|  
   |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
   |Establece las asignaciones de forma estática en el puerto de recepción.|  
   |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  

   > [!NOTE]
   >  El ejemplo anterior, debe cambiar la clave de servicio en el archivo de enlace a uno que existe en el servidor de destino UDDI.  

   |Archivo de entrada a FTP saliente con la resolución estática|  
   |------------------------------------------------------------|  
   |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
   |Establece las asignaciones de forma estática en el puerto de recepción.|  
   |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  

   |Archivo de entrada a FTP saliente con la resolución estática y el parámetro ENDPOINTCONFIG|  
   |-----------------------------------------------------------------------------------------|  
   |El archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml se usa para establecer la ubicación de recepción y propiedades de puerto de envío.|  
   |Establece las asignaciones de forma estática en el puerto de recepción.|  
   |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  
   |Pasa los pares nombre/valores adicionales para el proveedor del adaptador establecer.|  

   |Archivo de entrada a MQS saliente con la resolución estática|  
   |------------------------------------------------------------|  
   |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
   |Establece las asignaciones de forma estática en el puerto de recepción.|  
   |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  

   |                                                                             Archivo de entrada al archivo de salida mediante la resolución XPATH                                                                             |
   |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                        Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.                        |
   |                                                                                 Establece las asignaciones de forma estática en el puerto de recepción.                                                                                  |
   |                                                                    Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.                                                                    |
   | Usa información dentro del mensaje para determinar el punto de conexión adecuado. Los archivos de prueba que puede usar con este ejemplo son NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml y NAOrderDoc_XPATH_MQS.xml. |


4. Importe el archivo de enlace para el ejemplo de mensajería que desee ejecutar en la aplicación GlobalBank.ESB.  

5. En el Explorador de Windows, abra la carpeta \Source\Samples\DynamicResolution\Test\Data y copie el archivo de entrada correspondiente en la carpeta \Source\Samples\DynamicResolution\Test\Filedrop\In. El archivo que se usa depende en el ejemplo se que ha decidido ejecutar:  

   -   Por ejemplo, XPATH, utilice uno de los siguientes archivos: NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml o NAOrderDoc_XPATH_MQS.xml.  

   -   Para obtener todos los otros ejemplos, use el archivo NAOrderDoc.xml.  

6. Busque en la ubicación adecuada para el mensaje entregado. La ubicación depende de que usa el archivo de enlace. Estos son algunos ejemplos:  

   -   El archivo de entrada a FTP saliente del ejemplo entrega el mensaje en el directorio virtual FTP denominado Out que creó al instalar el ejemplo.  

   -   El archivo de entrada al ejemplo de salida de archivo, se entrega el mensaje a la subcarpeta \DynamicResolution\Test\Filedrop\Out.  

   -   El archivo de entrada al ejemplo MQS saliente se entrega el mensaje a la prueba. FUERA de la cola que creó cuando instaló el ejemplo.  

   -   El archivo de entrada al archivo de salida en el ejemplo de resolución de XPATH se entrega el mensaje a la ubicación especificada en el mensaje. Los documentos de ejemplo contienen el tipo de transporte y la ubicación de destino (el tipo de transporte se anexa al nombre del archivo de mensaje; por ejemplo, el mensaje NAOrderDoc_XPATH_FTP.xml contiene la especificación de tipo de transporte FTP).  

   Para comprender cómo el ejemplo usa el distribuidor de ESB y componentes de canalización de desensamblador de distribuidor de ESB, consulte [dinámica resolución ejemplo funcionamiento](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).