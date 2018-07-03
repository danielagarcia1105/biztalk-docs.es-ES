---
title: Instalar y ejecutar el ejemplo de resolución dinámica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4359987-b18c-44f5-a2cf-e30e17ac5e9f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0939111bc0a62ecf31286045f412ed160a97c3f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967733"
---
# <a name="installing-and-running-the-dynamic-resolution-sample"></a>Instalar y ejecutar el ejemplo de resolución dinámica
El ejemplo de resolución dinámica muestra escenarios de uso habituales para el distribuidor de ESB y componentes de canalización de desensamblador de distribuidor de ESB. Muestra cómo puede usar los componentes para resolver la ubicación del extremo dinámicamente, establecer las propiedades de enrutamiento y resolver y ejecutar asignaciones de BizTalk de Microsoft en el nivel de mensajería sin usar una orquestación. También muestra los modelos de mensajería unidireccionales y bidireccionales.  
  
> [!NOTE]
>  Para obtener unos resultados óptimos al familiarizarse con el mecanismo de resolución en el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], debe ejecutar el [instalar y ejecutar el ejemplo de servicio de resolución](../esb-toolkit/installing-and-running-the-resolver-service-sample.md) antes de ejecutar el ejemplo de resolución dinámica.  
  
 La aplicación de ejemplo contiene dos ubicaciones de recepción y dos puertos de envío dinámico, el ejemplo se usa para mostrar varios casos de uso para los componentes de resolución dinámica. Cada caso de uso muestra cómo las resoluciones y proveedores de adaptador en la resolución y marco de proveedores de adaptador, cuando se usa en combinación, pueden proporcionar la base para una variedad de soluciones de mensajería con acoplamiento flexible.  
  
## <a name="one-way-messaging-scenarios"></a>Escenarios de mensajería unidireccional  
 Mensajería escenarios (excepto el que utiliza a la resolución de XPATH) use el archivo NAOrderDoc.xml, ubicado en la carpeta \Source\Samples\DynamicResolution\Test\Data, unidireccionales como entrada para la recepción, ubicación denominada DynamicResolution_FILE. Hay siete ejemplos de mensajes unidireccionales, todas las representado por un enlace único archivo que debe importar antes de ejecutar cada ejemplo.  
  
## <a name="two-way-messaging-scenarios"></a>Escenarios de mensajería bidireccional  
 Todos los escenarios de mensajería bidireccionales usan el ejemplo ESB. Servicio NorthAmericanServices Web ubicado en http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx para publicar el mensaje de solicitud en BizTalk. Puede ejecutar este servicio Web con Microsoft InfoPath o a través de una utilidad como disponible en Storm [CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409).  
  
 Cada ejemplo resuelve dinámicamente la dirección URL del extremo para enviar el mensaje en el ejemplo de ESB. Servicio CanadianServices Web ubicado en http://localhost/ESB.CanadianServices/SubmitPOService.asmx. En el ejemplo se ejecutará bien el **submitOrder** acción o el **submitPurchase** acción, dependiendo de los resultados del proceso de resolución. La ubicación de recepción para escenarios de mensajería bidireccionales es DynamicResolutionReqResp_SOAP. Hay 10 ejemplos de mensajes bidireccionales, todas las representado por un enlace único archivo que debe importar antes de ejecutar cada ejemplo.  
  
## <a name="binding-files"></a>Archivos de enlace  
 Los archivos de enlace para este ejemplo se encuentran en la carpeta denominada \Source\Samples\DynamicResolution\Samples\Release.  
  
 Iniciar todos los nombres de archivo de enlace con GlobalBank.ESB.DynamicResolution_SubmitOrder_To, seguido de una indicación del ejemplo individual a los que se aplican. Por ejemplo, el archivo de enlace para el ejemplo de "Archivo de entrada a la salida de archivo mediante la resolución estática" es GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml.  
  
 Cada vez que importar uno del enlace recepción archivos a la aplicación de GlobalBank.ESB BizTalk, subyacente se restablece la ubicación dentro de la aplicación de ejemplo. Los filtros de puertos de envío dinámicos asociados en el nombre del puerto de recepción. Por lo tanto, para ejecutar una prueba, simplemente importa uno de los archivos de enlace y la opción de soltar el mensaje con el nombre adecuado en la carpeta de entrada (para escenarios de mensajería unidireccional) o llamar al servicio NorthAmerican Web con InfoPath, la utilidad de Storm o cualquier otro cliente adecuado.  
  
## <a name="sample-dependencies"></a>Dependencias de ejemplo  
 El ejemplo de resolución dinámica tiene dependencias en un número de ensamblados que forman parte de la instalación de ESB core. Estos ensamblados son los siguientes:  
  
- **Microsoft.Practices.ESB.PipelineComponents.dll**. Contiene el componente de canalización de distribuidor de ESB.  
  
- **Microsoft.Practices.ESB.Resolver.dll**. Esto se implementa el Administrador de solucionador llamado por la canalización.  
  
- **Microsoft.Practices.ESB.Resolver.BRE.dll**. Esto implementa a la resolución de motor de reglas de negocio.  
  
- **Microsoft.Practices.ESB.Resolver.STATIC.dll**. Esto implementa a la resolución estática.  
  
- **Microsoft.Practices.ESB.Resolver.UDDI.dll**. Esto implementa a la resolución UDDI.  
  
- **Microsoft.Practices.ESB.Resolver.UDDI3.dll**. Esto implementa a la resolución de UDDI3.  
  
- **Microsoft.Practices.ESB.Resolver.XPATH.dll**. Esto implementa a la resolución de XPATH.  
  
- **Microsoft.Practices.ESB.Resolver.Schemas.dll**. Este archivo contiene los esquemas de resolución.  
  
- **Microsoft.Practices.ESB.Adapter.dll**. Esto implementa el Administrador de adaptador.  
  
- **Microsoft.Practices.ESB.Adapter.FTP.dll**. Esto implementa el proveedor del adaptador FTP.  
  
- **Microsoft.Practices.ESB.Adapter.FILE.dll**. Esto implementa el proveedor del adaptador de archivo.  
  
- **Microsoft.Practices.ESB.Adapter.MQSeries.dll**. Esto implementa el proveedor del adaptador de MQSeries.  
  
- **Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**. Esto implementa el proveedor del adaptador WCF-BasicHttp.  
  
- **Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**. Esto implementa el proveedor del adaptador WCF-WSHttp.  
  
  El ejemplo de resolución dinámica también es dependiente de la configuración correcta de los adaptadores y las resoluciones anterior. Asegúrese de completar el proceso para configurar estos, como se describe en instalar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
  Esta sección contiene los siguientes temas:  
  
- [Instalación del ejemplo de resolución dinámica](../esb-toolkit/installing-the-dynamic-resolution-sample.md)  
  
- [Ejecución del ejemplo de resolución dinámica](../esb-toolkit/running-the-dynamic-resolution-sample.md)
