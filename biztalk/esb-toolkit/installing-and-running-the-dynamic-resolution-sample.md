---
title: "Instalar y ejecutar el ejemplo de resolución dinámica | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4359987-b18c-44f5-a2cf-e30e17ac5e9f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d697028eb76cf922cf4bf5e5db85c561c67d00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-running-the-dynamic-resolution-sample"></a>Instalar y ejecutar el ejemplo de resolución dinámica
El ejemplo de resolución dinámica muestra escenarios de uso habituales para el distribuidor de ESB y componentes de canalización de desensamblador de distribuidor de ESB. Muestra cómo puede utilizar los componentes para resolver la ubicación del extremo dinámicamente, establecer las propiedades de enrutamientos y resolver y ejecutar asignaciones de BizTalk de Microsoft en el nivel de mensajería sin utilizar una orquestación. También muestra los patrones de mensajería unidireccionales y bidireccionales.  
  
> [!NOTE]
>  Para obtener resultados óptimos al familiarizarse con el mecanismo de resolución en el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], se debe ejecutar el [instalar y ejecutar el ejemplo de servicio de resolución](../esb-toolkit/installing-and-running-the-resolver-service-sample.md) antes de ejecutar el ejemplo de resolución dinámica.  
  
 La aplicación de ejemplo contiene dos ubicaciones de recepción y dos puertos de envío dinámico, lo que el ejemplo se usa para mostrar varios casos de uso para los componentes de resolución dinámica. Cada caso de uso muestra cómo las resoluciones y proveedores de adaptador en la resolución y marco de proveedores de adaptador, cuando se utiliza en combinación, pueden proporcionar la base para una amplia variedad de soluciones de mensajería con acoplamiento flexible.  
  
## <a name="one-way-messaging-scenarios"></a>Escenarios de mensajería unidireccionales  
 Todos los unidireccional mensajería escenarios (excepto el que utiliza al Solucionador de XPATH) use el archivo NAOrderDoc.xml, que se encuentra en la carpeta \Source\Samples\DynamicResolution\Test\Data, como entrada para la recepción, ubicación denominada DynamicResolution_FILE. Hay siete ejemplos de mensajes unidireccionales, todas las representado por un enlace único archivo que debe importar antes de ejecutar cada ejemplo.  
  
## <a name="two-way-messaging-scenarios"></a>Escenarios de mensajería bidireccionales  
 Todos los escenarios de mensajes bidireccionales usan el ejemplo ESB. Servicio de NorthAmericanServices Web situado en http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx para publicar el mensaje de solicitud en BizTalk. Puede ejecutar este servicio Web con Microsoft InfoPath o mediante una utilidad como el aluvión disponible en [CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409)).  
  
 Cada ejemplo dinámicamente resuelve la dirección URL del extremo para enviar el mensaje en el ejemplo de ESB. Servicio de CanadianServices Web situado en http://localhost/ESB.CanadianServices/SubmitPOService.asmx. En el ejemplo se ejecutará en el **submitOrder** acción o **submitPurchase** acción, dependiendo de los resultados del proceso de resolución. La ubicación de recepción para escenarios de mensajería bidireccionales es DynamicResolutionReqResp_SOAP. Hay 10 ejemplos de mensajes bidireccionales, todas las representado por un enlace único archivo que debe importar antes de ejecutar cada ejemplo.  
  
## <a name="binding-files"></a>Archivos de enlace  
 Los archivos de enlace de este ejemplo se encuentran en la carpeta denominada \Source\Samples\DynamicResolution\Samples\Release.  
  
 Todos los nombres de archivo de enlace que se inicie con GlobalBank.ESB.DynamicResolution_SubmitOrder_To, seguido de una indicación del ejemplo individual a las que se apliquen. Por ejemplo, el archivo de enlace para el ejemplo de "Archivo de entrada a la salida de archivo mediante la resolución estática" es GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml.  
  
 Cada vez que importe uno del enlace recepción de archivos en la aplicación de GlobalBank.ESB BizTalk subyacente se restablece la ubicación dentro de la aplicación de ejemplo. Los filtros de puertos de envío dinámicos asociados en el nombre de puerto de recepción. Por lo tanto, para ejecutar una prueba, simplemente importa uno de los archivos de enlace y cualquier colocar el mensaje con el nombre adecuado en la carpeta de entrada (para escenarios de mensajería unidireccionales) o llamar al servicio NorthAmerican Web con InfoPath, la utilidad tormenta o cualquier otro cliente adecuado.  
  
## <a name="sample-dependencies"></a>Dependencias de ejemplo  
 El ejemplo de resolución dinámica tiene dependencias en un número de ensamblados que forman parte de la instalación de ESB de núcleo. Estos ensamblados son los siguientes:  
  
-   **Microsoft.Practices.ESB.PipelineComponents.dll**. Contiene el componente de canalización de distribuidor de ESB.  
  
-   **Microsoft.Practices.ESB.Resolver.dll**. Esto implementa el Administrador de resolución que se llama a la canalización.  
  
-   **Microsoft.Practices.ESB.Resolver.BRE.dll**. Implementa a la resolución de motor de reglas de negocios.  
  
-   **Microsoft.Practices.ESB.Resolver.STATIC.dll**. Implementa a la resolución estática.  
  
-   **Microsoft.Practices.ESB.Resolver.UDDI.dll**. Implementa a la resolución de UDDI.  
  
-   **Microsoft.Practices.ESB.Resolver.UDDI3.dll**. Implementa a la resolución de UDDI3.  
  
-   **Microsoft.Practices.ESB.Resolver.XPATH.dll**. Implementa a la resolución de XPATH.  
  
-   **Microsoft.Practices.ESB.Resolver.Schemas.dll**. Contiene los esquemas de resolución.  
  
-   **Microsoft.Practices.ESB.Adapter.dll**. Implementa el Administrador de adaptador.  
  
-   **Microsoft.Practices.ESB.Adapter.FTP.dll**. Esto implementa el proveedor de adaptador FTP.  
  
-   **Microsoft.Practices.ESB.Adapter.FILE.dll**. Esto implementa el proveedor de adaptador de archivo.  
  
-   **Microsoft.Practices.ESB.Adapter.MQSeries.dll**. Esto implementa el proveedor de adaptador de MQSeries.  
  
-   **Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**. Esto implementa el proveedor de adaptador de WCF-BasicHttp.  
  
-   **Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**. Esto implementa el proveedor de adaptador de WCF-WSHttp.  
  
 El ejemplo de resolución dinámica también es dependiente de la configuración correcta de los adaptadores y las resoluciones anteriores. Asegúrese de completar el proceso para configurar estos elementos, como se describe en instalar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
 Esta sección contiene los siguientes temas:  
  
-   [Instalar el ejemplo de resolución dinámica](../esb-toolkit/installing-the-dynamic-resolution-sample.md)  
  
-   [Ejecutar el ejemplo de resolución dinámica](../esb-toolkit/running-the-dynamic-resolution-sample.md)