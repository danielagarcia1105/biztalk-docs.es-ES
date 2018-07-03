---
title: Marco de proveedores de adaptador y la resolución ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb7ea42e-b32c-40a8-b36b-c349f56f6edd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95134a1f806398f14a5596149eb605e2de20cac2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002805"
---
# <a name="the-resolver-and-adapter-provider-framework"></a>El marco de proveedores de adaptador y resolución
El marco de proveedores de adaptador y la resolución admite itinerario, transformación y punto de conexión de la resolución y enrutamiento. El marco de trabajo dinámicamente puede resolver los puntos de conexión y establecer propiedades del adaptador de salida. Después de la resolución de una componente se resuelve como un punto de conexión (por ejemplo, el uso de Universal Description, Discovery and Integration [UDDI] para buscar un punto de conexión de servicio Web salientes), un componente de proveedor de adaptador establece propiedades específicas de servidor BizTalk Server registrado adaptadores. Por ejemplo, el proveedor del adaptador WCF-BasicHttp es responsable de establecer el mensaje de BizTalk específico de propiedades de contexto para el punto de conexión de URI que se usará el adaptador de BizTalk específico; el proveedor del adaptador FTP es responsable de establecer las propiedades específicas para el adaptador de FTP.  
  
 Es uno de los objetivos de la resolución y el marco de proveedores de adaptador admitir la resolución y enrutamiento en el nivel mensajería, sin requerir el uso de las orquestaciones de BizTalk, o en el nivel de orquestación. En ambos casos, el marco acoplable proporciona fácil desarrollo, implementación y registro de las resoluciones nuevo y proveedores de adaptador. Todas las resoluciones y proveedores de adaptador implementan interfaces bien definidas y son de carga a petición en tiempo de ejecución a través del registro en los archivos de configuración.  
  
 El distribuidor de ESB y desensamblar distribuidor de ESB componentes de canalización usan el marco de proveedores de adaptador y la resolución pasando la cadena de conexión desde el encabezado SOAP del itinerario o la configuración de canalización para el Administrador de solucionador.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuración contiene los detalles de todas las instancias registradas resoluciones y proveedores de adaptador. En tiempo de ejecución, los administradores de resolución y administradores de adaptador que se leen los archivos de configuración en los detalles de los proveedores de adaptador y resoluciones registradas, cargar los ensamblados adecuados y almacenarlos en una caché de nivel del host de BizTalk. Esta técnica de almacenamiento en caché elimina el requisito para repetidas de lectura de archivos de configuración y carga de ensamblados para cada mensaje enviado.  
  
 Para obtener más información sobre cómo el marco resolución y adaptadores proveedor funciona y cómo puede ampliarlo mediante la creación de los solucionadores personalizados y proveedores de adaptador, vea [modificación y extensión del Kit de herramientas de BizTalk ESB](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).  
  
## <a name="supported-resolution-mechanisms-resolvers"></a>Resolución admite mecanismos (resoluciones)  
 El Kit de herramientas de ESB de BizTalk incluye las siguientes resoluciones: **estático, UDDI, UDDI3, XPATH, BRE, BRI, itinerario, itinerario estático** y **LDAP**.  
  
 Cadena de conexión de una resolución siempre consta de un **moniker** (como **BRE**) seguido de ":\\\\" y los detalles de conexión o procesamiento. El moniker coincide con la definición de la resolución asociada en el archivo de configuración. Las propiedades asociadas con cada cadena de conexión son únicas y no todas las propiedades que son necesarias. El esquema para cada una de las resoluciones puede encontrarse en el ESB. Proyecto Resolvers.Schemas.  
  
 Los siguientes son ejemplos de cadenas de conexión:  
  
- **ESTÁTICO**  
  
   ESTÁTICO:\\\TransportType=;  
  
   TransportLocation =<http://localhost/ESB.CanadianServices/SubmitPOService.asmx>;  
  
   Acción =;  
  
   EndPointConfig =;  
  
   JaxRpcResponse = false.  
  
   MessageExchangePattern=;  
  
   TargetNamespace =<http://globalbank.esb.dynamicresolution.com/canadianservices/>;  
  
   TransformType =;  
  
- **UDDI**  
  
   UDDI:\\\serverUrl=<http://localhost:9901/rmengine>;  
  
   serviceName=OrderPurchaseWebService;  
  
   serviceProvider = ESB de prácticas de Microsoft  
  
- **XPATH**  
  
   XPATH:\\\TransportType=;  
  
   `TransportLocation=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='ID' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   Acción =;  
  
   EndPointConfig =;  
  
   JaxRpcResponse =;  
  
   MessageExchangePattern=;  
  
   `TargetNamespace=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='customerName' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   TransformType =;  

- **BRE**  
  
   BRE:\\\policy=GetCanadaEndPoint;  
  
   versión =;  
  
   useMsg =;  
  
- **BRI**  
  
   BRI:\\\policy=ResolveItinerary;  
  
   versión =;  
  
   useMsg =;  
  
- **ITINERARIO**  
  
   ITINERARIO:\\\name=TwoWayTestItinerary;  
  
   versión =;  
  
- **ITINERARIO ESTÁTICO**  
  
   ITINERARIO estático:\\\name=TwoWayTestItinerary;  
  
   versión =;  
  
- **LDAP**  
  
   LDAP:\\\TransportType=SMTP;  
  
   TransportLocation = {correo electrónico de}  
  
   Filtro = (&(objectClass=User) (| () userPrincipalName =yourname@domain.com)));  
  
   SearchRoot =;  
  
   SearchScope = subárbol;  
  
   EndpointConfig = asunto = mensaje de prueba de itinerario para correo electrónico de {} & 
  
   SMTPAuthenticate = 0 &
  
   SMTPHost = 127.0.0.1 &
  
   FROM =test@globalbank.com&
  
   DeliveryReceipt = false &
  
   MessagePartsAttachments = 0 &
  
   ReadReceipt = false.  
  
   ThrowErrorIfNotFound = false.  
  
   Acción =;  
  
   JaxRpcResponse = false.  
  
   MessageExchangePattern=;  
  
   TargetNamespace =;  
  
   TransformType =;  
  
  No todos los atributos en la cadena de conexión son obligatorios. Además, **EndPointConfig** es un atributo especial que puede rellenar y devolver cualquier resolución. Opcionalmente, la resolución puede almacenar los pares nombre/valor que se corresponden con determinadas propiedades de contexto del adaptador de BizTalk, que a su vez, pueden escribir en el contexto del mensaje de BizTalk.  
  
  En este caso, el **ResolverDictionary** instancia que contiene todas las propiedades resueltas devuelto por el proceso de resolución, a continuación, pasa al administrador de adaptador. El Administrador de adaptador pasa el diccionario con el proveedor de adaptador específico que se establece propiedades para el mensaje de todo el específicas del punto de conexión y adaptador de BizTalk el contexto. Busque las resoluciones del **EndPointConfig** propiedad, extraer los pares nombre/valor que se corresponden con sus propiedades de adaptador correspondiente y, a continuación, establezca estos valores en el mensaje.  
  
## <a name="supported-adapter-providers"></a>Proveedores compatibles con el adaptador  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye los siguientes proveedores de adaptador integrado: **archivo, FTP, SMTP, MQSeries, WCF-BasicHttp, WCF-WSHttp,** y **WCF-Custom**. El nombre de cada proveedor de adaptador es idéntico al nombre del adaptador asociado (tipo de transporte) en BizTalk Server.  
  
 Una ventaja fundamental de la resolución y el marco de proveedores de adaptador es que puede ampliarlo mediante la creación y registro de sus propias resoluciones personalizadas para resolver la información de punto de conexión y los proveedores de adaptador personalizado para establecer propiedades específicas de los adaptadores de BizTalk registrados. Para obtener más información, consulte [modificación y extensión del Kit de herramientas de BizTalk ESB](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).
