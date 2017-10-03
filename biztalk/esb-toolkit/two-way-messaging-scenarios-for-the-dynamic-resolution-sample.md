---
title: "Escenarios de mensajería bidireccionales para el ejemplo de resolución dinámica | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e89792f1-c725-46c4-946c-23211e2f892a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 852b1f203b693c7783c7eb461c521f3fbe0ceffe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="two-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>Escenarios de mensajería bidireccionales para el ejemplo de resolución dinámica
Este tema muestra cómo ejecutar los escenarios de mensajería bidireccionales para la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplo de resolución dinámica.  
  
 **Para ejecutar los escenarios de mensajería bidireccionales para el ejemplo de resolución dinámica**  
  
1.  Antes de ejecutar este ejemplo por primera vez, asegúrese de que la dirección URL de ubicación de recepción señala al servicio Web adecuado. Especifique el servicio Web /ESB de dirección URL. NorthAmericanServices/CustomerOrder.asmx para el DynamicResolutionReqResp_SOAP la ubicación de recepción. Además, asegúrese de que existe el puerto de envío dinámico denominado DynamicResolutionSolicitResp.  
  
    > [!NOTE]
    >  El ejemplo de resolución dinámica usa resolución dinámica para enviar y recibir respuestas desde el servicio Web canadiense (http://localhost/ESB.CanadianServices/SubmitPOService.asmx). Este es el motivo por el que un puerto de envío estático no está definido para este ejemplo. El componente de resolución dinámica recupera la dirección URL de salida de la resolución y la ubicación de recepción de marco de proveedores de adaptador llama a la canalización ESBReceiveXml, que está configurada en el DynamicResolutionReqResp_SOAP. En algunos de los ejemplos de mensajes bidireccionales, la canalización ESBMapSend resuelve y ejecuta asignaciones de BizTalk de Microsoft.  
  
2.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.  
  
3.  Decidir qué ejemplo que desea ejecutar. Todos los escenarios de mensajes bidireccionales use ESB. Servicio NorthAmericanServices Web situado en http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx para publicar el mensaje de solicitud a BizTalk, que utiliza la ubicación de recepción denominada DynamicResolutionReqResp_SOAP. Hay 10 ejemplos de mensajes bidireccionales, cada uno representado por un archivo de enlace único. Las tablas siguientes muestran estos ejemplos, con sus archivos de enlace asociado y sus descripciones.  
  
    |Entrada SOAP para SOAP salientes (submitOrder acción) mediante el Solucionador de BRE|  
    |---------------------------------------------------------------------------------|  
    |Utiliza el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
    |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  
  
    |Entrada SOAP para SOAP salientes (submitOrder acción) mediante el Solucionador de BRE para punto de conexión y la resolución de transformación|  
    |----------------------------------------------------------------------------------------------------------------------------|  
    |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Routing_AND_ Transform_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
    |Utiliza el componente de distribuidor de ESB en el puerto de envío de salida de la canalización y la salida canalización de recepción ubicación para resolver y ejecutar la asignación dinámicamente.|  
    |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  
  
    |Entrada SOAP para SOAP salientes (submitOrder acción) con la resolución estática|  
    |------------------------------------------------------------------------------------|  
    |Utiliza el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_STATIC_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
    |Establece las asignaciones de forma estática en el puerto de recepción.|  
    |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  
  
    |Entrada SOAP para SOAP salientes (submitOrder acción) con la resolución en el Microsoft UDDI servidor UDDI|  
    |--------------------------------------------------------------------------------------------------------------------|  
    |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_MSFTREGISTRY_ Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
    |Establece las asignaciones de forma estática en el puerto de recepción.|  
    |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  
  
    > [!NOTE]
    >  En el ejemplo anterior, debe cambiar la clave de servicio en el archivo de enlace a uno que existe en el servidor de destino UDDI.  
  
    |Entrada SOAP para SOAP salientes (submitOrder acción) usando el UDDI resolución contra el SOA Software UDDI servidor|  
    |-----------------------------------------------------------------------------------------------------------------------|  
    |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_SOAREGISTRY_ Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
    |Establece las asignaciones de forma estática en el puerto de recepción.|  
    |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  
  
    |Entrada SOAP para SOAP salientes (submitOrder acción) mediante el Solucionador de XPATH|  
    |-----------------------------------------------------------------------------------|  
    |Utiliza el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_XPATH_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
    |Establece las asignaciones de forma estática en el puerto de recepción.|  
    |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  
    |El mensaje contiene el identificador de configuración de punto de conexión = http://localhost/ESB.CanadianServices/SubmitPOService.asmx y customerName = http://globalbank.esb.dynamicresolution.com/canadianservices/.|  
  
    |Entrada SOAP para SOAP salientes (submitPurchase acción) con el punto de conexión de BRE resolución y la resolución de transformación|  
    |---------------------------------------------------------------------------------------------------------------------------|  
    |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_BRE_Routing_ AND_Transform_Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
    |Utiliza el componente de distribuidor de ESB en el puerto de envío de salida de la canalización y la salida canalización de recepción ubicación para resolver y ejecutar la asignación dinámicamente.|  
    |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  
    |Los cambios de resolución de BRE el **acción** de **submitOrder** a **submitPurchase**.|  
  
    |Entrada SOAP para SOAP salientes (submitPurchase acción) con la resolución estática|  
    |---------------------------------------------------------------------------------------|  
    |Usa el archivo de enlace denominado GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_STATIC_ Bindings.xml para establecer la ubicación de recepción y propiedades de puerto de envío.|  
    |Establece las asignaciones de forma estática en el puerto de recepción.|  
    |Utiliza el distribuidor de ESB en la ubicación de recepción para la resolución de punto de conexión.|  
    |Los cambios de resolución estática la **acción** de **submitOrder** a **submitPurchase**.|  
  
4.  Importe el archivo de enlace para el ejemplo de mensajería que desea ejecutar en la aplicación GlobalBank.ESB.  
  
5.  Llame al servicio NorthAmerican Web con Microsoft InfoPath, el servicio de Web .NET Studio o cualquier otro mecanismo adecuado. Asegúrese de que incluya todos los parámetros requeridos por la operación.  
  
6.  Busque la respuesta del mensaje devuelto. Si ha especificado el **submitOrder** acción, el texto "Enviar pedido" estará precedido por el valor de la **identificador** campo en el mensaje devuelto. Si ha especificado el **submitPurchase** acción, el texto "Compra enviar" estará precedido por el valor de la **identificador** campo en el mensaje devuelto.  
  
 Para comprender cómo el ejemplo usa el distribuidor de ESB y componentes de canalización de desensamblador de distribuidor de ESB, consulte [dinámica resolución ejemplo funcionamiento del](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).