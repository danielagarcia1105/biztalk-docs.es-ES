---
title: Resolución ESB y marco de proveedores de adaptador | Documentos de Microsoft
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
ms.openlocfilehash: a350ac19ac1fa95ffb8eb6782380bda78a457b75
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="the-resolver-and-adapter-provider-framework"></a>La resolución y el marco de proveedores de adaptador
La resolución y el marco de proveedores de adaptador es compatible con la resolución de itinerario, transformación y punto de conexión y el enrutamiento. El marco de trabajo puede resolver los puntos de conexión y establecer las propiedades de salida del adaptador dinámicamente. Después de la resolución de una componente resuelve un punto de conexión (por ejemplo, mediante Universal Description, Discovery e integración [UDDI] para buscar un extremo de servicio Web salientes), un componente de proveedor de adaptador establece propiedades específicas del servidor BizTalk Server registrado adaptadores. Por ejemplo, el proveedor del adaptador de WCF-BasicHttp es responsable de establecer el mensaje de BizTalk específico de propiedades de contexto para el extremo de URI que se va a utilizar el adaptador de BizTalk específico; el proveedor de adaptador FTP es responsable de establecer las propiedades específicas del adaptador de FTP.  
  
 Uno de los objetivos de la resolución y el marco de proveedores de adaptador es compatible con la resolución y el enrutamiento en el nivel mensajería, sin requerir el uso de las orquestaciones de BizTalk, o en el nivel de orquestación. En ambos casos, el marco acoplable proporciona fácil desarrollo, la implementación y el registro de proveedores de adaptador y resoluciones nuevo. Todas las resoluciones y proveedores de adaptador implementan interfaces bien definidas y están demanda de carga en tiempo de ejecución a través del registro en los archivos de configuración.  
  
 El distribuidor de ESB y ESB distribuidor desensamblar los componentes de canalización usan la resolución y el marco de proveedores de adaptador, pase la cadena de conexión desde el encabezado SOAP de itinerario o la configuración de canalización con el Administrador de resolución.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuración contiene los detalles de todos los solucionadores y proveedores de adaptador. En tiempo de ejecución, los administradores de resolución y administradores de adaptador leer detalles de los proveedores de adaptador y resoluciones registradas desde los archivos de configuración, cargar los ensamblados adecuados y almacenarlos en una caché de nivel del host de BizTalk. Esta técnica de almacenamiento en caché elimina la necesidad de repetidas de lectura de archivos de configuración y la carga de ensamblados para cada mensaje enviado.  
  
 Para obtener más información sobre cómo funciona la resolución y marco de proveedores de adaptador y cómo puede ampliarlo mediante la creación de solucionadores personalizados y los proveedores de adaptador, vea [modificar y extender el Kit de herramientas de ESB de BizTalk](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).  
  
## <a name="supported-resolution-mechanisms-resolvers"></a>Mecanismos de resolución admitidos (resoluciones)  
 El Kit de herramientas de ESB de BizTalk incluye las siguientes resoluciones: **estático, UDDI, UDDI3, XPATH, BRE, BRI, itinerario, itinerario estático** y **LDAP**.  
  
 Cadena de conexión de una resolución siempre consta de un **moniker** (como **BRE**) seguido de ":\\\\" y los detalles de conexión o el procesamiento. El moniker coincide con la definición de la resolución asociada en el archivo de configuración. Las propiedades asociadas a cada cadena de conexión son únicas y no todas las propiedades son necesarias. El esquema para cada uno de los solucionadores puede encontrarse en ESB. Proyecto de Resolvers.Schemas.  
  
 Los siguientes son ejemplos de cadenas de conexión:  
  
-   **ESTÁTICO**  
  
     ESTÁTICO:\\\TransportType=;  
  
     TransportLocation =http://localhost/ESB.CanadianServices/SubmitPOService.asmx;  
  
     Acción =;  
  
     EndPointConfig =;  
  
     JaxRpcResponse = false;  
  
     MessageExchangePattern=;  
  
     TargetNamespace =http://globalbank.esb.dynamicresolution.com/canadianservices/;  
  
     TransformType =;  
  
-   **UDDI**  
  
     UDDI:\\\serverUrl=http://localhost:9901/rmengine;  
  
     serviceName=OrderPurchaseWebService;  
  
     serviceProvider = ESB de prácticas de Microsoft  
  
-   **XPATH**  
  
     XPATH:\\\TransportType=;  
  
     `TransportLocation=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='ID' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
     Acción =;  
  
     EndPointConfig =;  
  
     JaxRpcResponse =;  
  
     MessageExchangePattern=;  
  
     `TargetNamespace=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='customerName' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
     TransformType =;  

-   **BRE**  
  
     BRE:\\\policy=GetCanadaEndPoint;  
  
     versión =;  
  
     useMsg =;  
  
-   **BRI**  
  
     BRI:\\\policy=ResolveItinerary;  
  
     versión =;  
  
     useMsg =;  
  
-   **ITINERARIO**  
  
     ITINERARIO:\\\name=TwoWayTestItinerary;  
  
     versión =;  
  
-   **ITINERARIO ESTÁTICOS**  
  
     ITINERARIO estático:\\\name=TwoWayTestItinerary;  
  
     versión =;  
  
-   **LDAP**  
  
     LDAP:\\\TransportType=SMTP;  
  
     TransportLocation = {correo}  
  
     Filtro = (&(objectClass=User) (| () userPrincipalName =yourname@domain.com)));  
  
     SearchRoot =;  
  
     SearchScope = subárbol;  
  
     EndpointConfig = sujeto = mensaje de prueba de itinerario a {mail} & 
  
     SMTPAuthenticate = 0 &
  
     SMTPHost = 127.0.0.1 &
  
     FROM =test@globalbank.com&
  
     DeliveryReceipt = false &
  
     MessagePartsAttachments = 0 &
  
     ReadReceipt = false;  
  
     ThrowErrorIfNotFound = false;  
  
     Acción =;  
  
     JaxRpcResponse = false;  
  
     MessageExchangePattern=;  
  
     TargetNamespace =;  
  
     TransformType =;  
  
 No todos los atributos de la cadena de conexión son obligatorios. Además, **EndPointConfig** es un atributo especial que puede rellenar y devolver cualquier resolución. Si lo desea, la resolución puede almacenar los pares de nombre/valor que se corresponden con determinadas propiedades de contexto del adaptador de BizTalk, que a su vez, pueden escribir en el contexto del mensaje de BizTalk.  
  
 En este caso, el **ResolverDictionary** instancia que contiene todas las propiedades resueltas devuelto por el proceso de resolución, a continuación, pasa al administrador de adaptador. El Administrador de adaptador pasa el diccionario con el proveedor de adaptador específico que se establece propiedades para el mensaje de todo el específicas de punto de conexión y adaptador de BizTalk el contexto. Buscan las resoluciones el **EndPointConfig** propiedad, extraer los pares de nombre/valor que se corresponden con sus propiedades de adaptador correspondiente y, a continuación, establecer estos valores en el mensaje.  
  
## <a name="supported-adapter-providers"></a>Proveedores compatibles con el adaptador  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye los siguientes proveedores de adaptador integrado: **archivo, FTP, SMTP, MQSeries, WCF-BasicHttp, WCF-WSHttp,** y **WCF-Custom**. El nombre de cada proveedor de adaptador es idéntico al nombre del adaptador asociado (tipo de transporte) en BizTalk Server.  
  
 Una ventaja fundamental de la resolución y el marco de proveedores de adaptador es que puede ampliarlo mediante la creación y registrar sus propio solucionadores personalizados para resolver la información de extremo y los proveedores de adaptador personalizado para establecer las propiedades específicas de los adaptadores de BizTalk registrados. Para obtener más información, consulte [modificar y extender el Kit de herramientas de ESB de BizTalk](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).
