---
title: Componentes clave de WCF LOB Adapter SDK | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59b8029b-4799-471b-8825-15d79a30bf1f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c034c1006ed898a28aab04cde201524e4c3b13b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226996"
---
# <a name="key-components-of-the-wcf-lob-adapter-sdk"></a>Componentes clave de SDK del adaptador LOB de WCF
Desarrollar un adaptador mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] requiere el uso de muchos de los componentes básicos siguientes:  
  
-   **Componentes de la conexión** para ayudar a establecer y mantener una conexión con el sistema de línea de negocio.  
  
-   **Componentes del controlador** definir e implementar procedimientos usados para trabajar con mensajes entrantes y salientes y las operaciones de metadatos.  
  
-   **Componentes de metadatos** definir y manipular los metadatos utilizados para comunicarse con el sistema de línea de negocio.  
  
-   **Componentes personalizados** proporcionan compatibilidad para las transacciones, mensajería de confianza y seguridad.  
  
-   **Componentes principales** unir todos los componentes y garantizar una integración sin problemas en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].  
  
 Estos componentes son el objetivo de este tema.  
  
## <a name="connection-components"></a>Componentes de la conexión  
 Los componentes de conexión incluyen interfaces y clases que ayudan a definirán y controlan la duración de las conexiones, así como administración los atributos de la consulta de recursos uniforme (URI) de identificadores y los atributos de usuario. Componentes de la conexión incluyen las interfaces y clases que se describen en la tabla siguiente.  
  
|Componente de conexión|¿Requerido?|Description|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionUri`|Necesario|Clase base para proporcionar un URI personalizado compilar experiencia para los usuarios que consumirá el adaptador.|  
|`Microsoft.ServiceModel.Channels.Common.IConnection`|Necesario|Interfaz que define el comportamiento de una conexión. Los programadores deben implementar esta interfaz para definir una conexión con el sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`|Necesario|Clase base para un generador de conexiones. Los desarrolladores creará una subclase al definir el generador de conexiones para el sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`|Opcional|Contiene valores que controlan el comportamiento de la agrupación de conexiones. Los desarrolladores que desee ajustar estos valores en función del comportamiento del sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`|Opcional|Contiene la configuración estática que controlan el comportamiento de la agrupación de conexiones. Los desarrolladores que desee ajustar estos valores para su sistema de destino.|  
  
 El [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] creará las implementaciones de `Microsoft.ServiceModel.Channels.Common.IConnection``Microsoft.ServiceModel.Channels.Common.ConnectionUri` y `Microsoft.ServiceModel.Channels.Common.IConnectionFactory` , independientemente de la elección de opciones de asistente. Estas implementaciones contiene código para admitir opciones elegidas en el Asistente (incluidas las propiedades de conexión en el URI de conexión), pero el desarrollador de adaptadores debe proporcionar implementaciones para abrir, cerrar y otros métodos de `Microsoft.ServiceModel.Channels.Common.IConnection` y `Microsoft.ServiceModel.Channels.Common.ConnectionUri`.  
  
## <a name="handler-components"></a>Componentes de controlador  
 Los componentes de controlador proporcionan compatibilidad para patrones de intercambio de mensajes diferentes incluidas entrante, saliente, asincrónica de entrada, asincrónica salientes y búsqueda de metadatos, examinar y resolver las operaciones. Componentes de controlador incluyen las interfaces y clases que se describen en la tabla siguiente.  
  
|Componente de controlador|¿Requerido?|Description|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|Opcional|Utilizado para recibir mensajes de forma asincrónica desde el sistema de destino. Compatibilidad asincrónica es opcional.|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|Opcional|Se utiliza para enviar mensajes de forma asincrónica desde el sistema de destino. Compatibilidad asincrónica es opcional.|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|Opcional|Se utiliza para recibir mensajes desde el sistema de destino. Los programadores deben implementar este controlador si el adaptador debe realizar escuchas de mensajes desde el sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|Opcional|Proporciona compatibilidad para enviar mensajes al sistema de destino. Aunque es opcional, es necesario para el patrón de mensaje de solicitud y respuesta. Tecnologías de comunicación más importantes se basan en este patrón como HTTP, RPC y muchas otras.|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|Opcional|Este controlador se implementa cuando el adaptador admite la exploración de metadatos. Aunque es opcional, a los desarrolladores a menudo implementará este controlador para proporcionar una lista de operaciones disponibles en el sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|Opcional|Cuando el adaptador recupera y devuelve los metadatos desde el sistema de destino que representa la lógica específica del sistema y tipos de datos, se debe implementar este controlador. Los metadatos se pueden recuperar desde el sistema de destino real, o bien se puede crear para representar las capacidades del sistema de destino. Por ejemplo, un adaptador de FTP puede crear GET y las operaciones PUT.<br /><br /> Si bien no es necesario, los desarrolladores generalmente implementar este controlador para proporcionar información sobre una operación específica.|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|Opcional|Este controlador se implementa cuando el adaptador es compatible con la búsqueda de metadatos.|  
  
 El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] creará las implementaciones de `Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`, `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`, `Microsoft.ServiceModel.Channels.Common.IInboundHandler` y los controladores de metadatos en función de las selecciones realizadas por el desarrollador. Se proporciona código de soporte; Sin embargo, el desarrollador de adaptadores tendrá que proporcionar código para iniciar y detener el agente de escucha de entrada y otro código marcado por TODO (comentarios).  
  
## <a name="metadata-components"></a>Componentes de metadatos  
Los componentes de metadatos proporcionan compatibilidad para controlar las solicitudes de metadatos y para describir los tipos y las operaciones en la aplicación de destino. Los componentes de controlador controlan cómo se tratan las solicitudes de metadatos. Los componentes de metadatos describen los tipos de datos y las operaciones expuestas por el sistema de destino.  

 Los componentes de metadatos están diseñados para contener dos tipos de información de metadatos: tipo de metadatos y los metadatos de la operación.  
  
-   *Metadatos del tipo* describe los tipos de datos que están disponibles en el sistema de destino e incluye el nombre del tipo, sus propiedades de la matriz si es una matriz, y si es un tipo de esquema XSD simple o un tipo complejo.  
  
-   *Metadatos de operación* describe las operaciones que están disponibles en el sistema de destino. Las propiedades incluyen un tipo de valor devuelto, una lista de parámetros y el nombre de la operación.  
  
 Compatibilidad de los metadatos de un adaptador es opcional pero recomendado. Una de las ventajas del uso de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] para generar un adaptador frente a la implementación de funcionalidad como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio es la capacidad de exponer y enlazar a un conjunto dinámico de operaciones.  

> [!NOTE]
>  Si es necesario exponer un conjunto limitado de métodos estáticos, considere la posibilidad de usar el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].  
 
  Los componentes disponibles para el control, describir y trabajar con metadatos se describen en la tabla siguiente.  
  
|Componente de metadatos|Description|  
|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`|Una clase que representa un tipo complejo completo para un adaptador. Por ejemplo, si el sistema de destino es una base de datos relacional, una tabla, fila o tipo de valor devuelto de procedimiento definido por el usuario pueden ser tipos de acceso personalizados.|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadata`|Clase base para que representa metadatos de operación para el sistema de destino. Por ejemplo, podría subclase OperationMetadata para incluir información acerca de los procedimientos almacenados en un adaptador que se dirige a una base de datos relacional.|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadataTraceRecord`|Proporciona una manera de capturar metadatos de la operación en un archivo de seguimiento. El seguimiento recopila información como identificador único, última vez que accede a, marca de tiempo, nombre para mostrar, nombre original, parámetros y otros detalles.|  
|`Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`|Proporciona una forma de definir atributos de una operación como parámetros y tipo de valor devuelto.|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameter`|Describe un parámetro que se utiliza para invocar una operación en el sistema de destino. Propiedades incluyen el nombre, nombre original, dirección del parámetro y una marca que indica si el parámetro está vacío o no.|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameterDirection`|Un tipo enumerado que describe la dirección de un parámetro para una operación. Un parámetro puede ser entrante solo (PDA), solo de salida (salida) o bidireccional (InOut).|  
|`Microsoft.ServiceModel.Channels.Common.OperationResult`|Representa un resultado de la operación. Puede ser OperationResult.Empty para operaciones que devuelven void o null y una cadena, entero u otro valor dependiendo de la operación.|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedType`|Diseñado para ser la clase base para calificar las propiedades de tipo y se utiliza para describir las propiedades de metadatos de tipo para un sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedTypeContainer`|Proporciona un contenedor para un conjunto de tipos completos relacionados.|  
|`Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`|Describe las propiedades de metadatos de tipo para un sistema de destino cuando ese tipo se asigna directamente a un tipo de esquema XSD de W3C. Para obtener una lista de tipos permitidos, consulte [XmlTypeCode enumeración](https://msdn.microsoft.com/library/system.xml.schema.xmltypecode(v=vs.110).aspx).|  
|`Microsoft.ServiceModel.Channels.Common.TypeMember`|Proporciona una manera de definir a un miembro de datos simples o complejas en los metadatos de tipo estructurado.|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadata`|Clase base para que representa los metadatos de tipo para el sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`|Proporciona una manera de definir una estructura de datos que contiene a los miembros de tipo simple o complejo.|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataCollection`|Proporciona un contenedor para un conjunto de metadatos de tipo relacionado.|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataTraceRecord`|Proporciona una manera de capturar metadatos de tipo en un archivo de seguimiento. El seguimiento recopila información como identificador único, acceso a última hora, marca de tiempo y otros detalles.|  
  
## <a name="custom-components"></a>Componentes personalizados  
 Componentes personalizados proporcionan compatibilidad para las transacciones, seguridad, mensajería confiable y otras características que son altamente dependientes en el sistema de destino. Como programador de adaptadores mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], debe conocer las capacidades del sistema de destino y determinar el alcance a la que desea admitirlas.  
  
## <a name="core-components"></a>Componentes principales  
 Componentes principales proporcionan un conjunto de clases base e interfaces que habilitan el adaptador para incluirse en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]. Se describen los componentes principales en la tabla siguiente.  
  
|Componente principal|¿Requerido?|Description|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.Adapter`|Necesario|La clase base de un adaptador escrito con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Es responsable de interactuar con el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal|  
|`Microsoft.ServiceModel.Channels.Common.AdapterBinding`|Necesario|Clase que contiene configuraciones que controlan diversas configuraciones para el adaptador incluido el grupo de conexión (`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`), caché (`Microsoft.ServiceModel.Channels.Common.CacheSettings`), metadatos (`Microsoft.ServiceModel.Channels.Common.MetadataSettings`) y la mensajería (`Microsoft.ServiceModel.Channels.Common.MessagingSettings`).|  
  
 Adaptadores personalizados se exponen a través de enlaces de WCF. Para obtener más información, consulte la documentación de WCF en [http://go.microsoft.com/fwlink/?LinkId=100308](http://go.microsoft.com/fwlink/?LinkId=100308).  
  
 El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] crear implementaciones de `Microsoft.ServiceModel.Channels.Common.Adapter`, `Microsoft.ServiceModel.Channels.Common.AdapterBinding`, `System.ServiceModel.Configuration.StandardBindingElement`, y `System.ServiceModel.Configuration.StandardBindingCollectionElement` para exponer el enlace del adaptador en el sistema de configuración de WCF. El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] también generará una implementación de `System.ServiceModel.Configuration.BindingElementExtensionElement` para habilitar `Microsoft.ServiceModel.Channels.Common.Adapter` a utilizarse en un enlace personalizado de WCF desde un archivo de configuración de equipo o una aplicación.  
  
 Para obtener más información acerca de StandardBindingElement, StandardBindingCollectionElement y BindingElementExtensionElement, consulte la documentación de WCF.  
  
 Para obtener más información acerca de cómo configurar un adaptador escrito con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], consulte [implementar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md).  
  
## <a name="see-also"></a>Vea también  
 [Comprender el sistema LOB con el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)