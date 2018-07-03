---
title: Componentes clave de WCF LOB Adapter SDK | Microsoft Docs
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
ms.openlocfilehash: 3d033e452c4f67b66ed7e3b50b2c553def558015
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972237"
---
# <a name="key-components-of-the-wcf-lob-adapter-sdk"></a>Principales componentes del SDK del adaptador LOB de WCF
Desarrollar un adaptador mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] requiere el uso de muchos de los componentes básicos siguientes:  

- **Componentes de la conexión** para ayudar a establecer y mantener una conexión con el sistema de línea de negocio.  

- **Los componentes del controlador** definir e implementar procedimientos que se usan para trabajar con los mensajes entrantes y salientes y las operaciones de metadatos.  

- **Componentes de metadatos** definen y manipulan los metadatos utilizados para comunicarse con el sistema de línea de negocio.  

- **Componentes personalizados** proporcionan compatibilidad con transacciones, mensajería confiable y seguridad.  

- **Los componentes principales** unir todos los componentes y asegurar una integración sin problemas en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].  

  Estos componentes son el objetivo de este tema.  

## <a name="connection-components"></a>Componentes de la conexión  
 Los componentes de conexión incluyen interfaces y clases que ayudan a definirán y controlan la duración de las conexiones, así como administración los atributos de la consulta (URI) de identificadores uniformes de recursos y atributos de usuario. Componentes de la conexión incluyen las interfaces y clases que se describen en la tabla siguiente.  

|Componente de conexión|¿Requerido?|Descripción|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionUri`|Obligatorio|Clase base que proporciona un URI personalizado Crear experiencia para los usuarios que consumirá el adaptador.|  
|`Microsoft.ServiceModel.Channels.Common.IConnection`|Obligatorio|Interfaz que define el comportamiento de una conexión. Los desarrolladores deben implementar esta interfaz para definir una conexión al sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`|Obligatorio|Clase base para un generador de conexión. Los desarrolladores creará una subclase al definir el generador de conexión para el sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`|Opcional|Contiene valores que controlan el comportamiento de la agrupación de conexiones. Los programadores pueden desear ajustar estos valores en función del comportamiento del sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`|Opcional|Contiene valores estáticos que controlan el comportamiento de la agrupación de conexiones. Los programadores pueden desear ajustar estos valores para su sistema de destino.|  

 El [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] creará las implementaciones de `Microsoft.ServiceModel.Channels.Common.IConnection``Microsoft.ServiceModel.Channels.Common.ConnectionUri` y `Microsoft.ServiceModel.Channels.Common.IConnectionFactory` sin tener en cuenta el elegido las opciones de asistente. Estas implementaciones contendrá el código para la compatibilidad con las opciones elegidas en el Asistente (incluidas las propiedades de conexión en el URI de conexión), pero el programador de adaptadores tendrá que proporcionar implementaciones para abrir, cerrar y otros métodos de `Microsoft.ServiceModel.Channels.Common.IConnection` y `Microsoft.ServiceModel.Channels.Common.ConnectionUri`.  

## <a name="handler-components"></a>Componentes del controlador  
 Los componentes de controlador proporcionan soporte técnico para patrones de intercambio de mensajes distintos incluidos entrante, saliente y asincrónica de entrada, asincrónica saliente y búsqueda de metadatos, examinar y resolver las operaciones. Los componentes del controlador incluyen las interfaces y clases que se describen en la tabla siguiente.  

|Componente de controlador|¿Requerido?|Descripción|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|Opcional|Se utiliza para recibir mensajes de forma asincrónica desde el sistema de destino. Compatibilidad asincrónica es opcional.|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|Opcional|Se utiliza para enviar mensajes de forma asincrónica desde el sistema de destino. Compatibilidad asincrónica es opcional.|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|Opcional|Se utiliza para recibir mensajes desde el sistema de destino. Los desarrolladores deben implementar este controlador si el adaptador debe escuchar mensajes desde el sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|Opcional|Proporciona compatibilidad para enviar mensajes al sistema de destino. Aunque es opcional, es necesario para el patrón de mensaje de solicitud y respuesta. Las tecnologías más importantes de comunicación se basan en este patrón como HTTP, RPC y muchos otros.|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|Opcional|Este controlador se implementa cuando el adaptador admite la exploración de metadatos. Aunque es opcional, los desarrolladores a menudo implementará este controlador para proporcionar una lista de operaciones disponibles en el sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|Opcional|Cuando el adaptador recupera y devuelve los metadatos del sistema de destino que representa la lógica específica del sistema y los tipos de datos, se debe implementar este controlador. Se pueden recuperar desde el sistema de destino real, o se puede crear para representar las capacidades del sistema de destino. Por ejemplo, crear un adaptador de FTP GET y PUT operaciones.<br /><br /> Aunque no es necesario, los desarrolladores generalmente implementará este controlador para proporcionar información sobre una operación específica.|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|Opcional|Este controlador se implementa cuando el adaptador es compatible con la búsqueda de metadatos.|  

 El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] creará las implementaciones de `Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`, `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`, `Microsoft.ServiceModel.Channels.Common.IInboundHandler` y los controladores de metadatos según las selecciones realizadas por el desarrollador. Se proporciona código de soporte técnico; Sin embargo, el programador de adaptadores tendrá que proporcionar código para iniciar y detener el agente de escucha entrante y otro código marcada con comentarios de la lista de tareas.  

## <a name="metadata-components"></a>Componentes de metadatos  
Los componentes de metadatos proporcionan compatibilidad para controlar las solicitudes de metadatos y para describir los tipos y las operaciones en la aplicación de destino. Los componentes de controlador controlan cómo se tratan las solicitudes de metadatos. Los componentes de metadatos describen los tipos de datos y las operaciones expuestas por el sistema de destino.  

 Los componentes de metadatos están diseñados para contener dos tipos de información de metadatos: tipo de metadatos y los metadatos de la operación.  

- *Metadatos de tipo* se describen los tipos de datos que están disponibles en el sistema de destino e incluye el nombre del tipo, sus propiedades de la matriz si es una matriz, y si es un tipo de esquema XSD simple o un tipo complejo.  

- *Los metadatos de la operación* describe las operaciones que están disponibles en el sistema de destino. Las propiedades incluyen un tipo de valor devuelto, una lista de parámetros y el nombre de la operación.  

  Compatibilidad con metadatos de un adaptador es opcional pero recomendado. Una de las ventajas de usar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] para crear un adaptador en comparación con la implementación de la funcionalidad como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service es la capacidad de exponer y enlazar a un conjunto dinámico de operaciones.  

> [!NOTE]
>  Si tiene que exponer un conjunto limitado de métodos estáticos, considere la posibilidad de usar el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].  

  Los componentes disponibles para el control, que describe y trabajar con los metadatos se describen en la tabla siguiente.  

|Componente de metadatos|Descripción|  
|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`|Una clase que representa un tipo complejo calificado para un adaptador. Por ejemplo, si el sistema de destino es una base de datos relacional, una tabla, la fila o tipo de valor devuelto de procedimiento definido por el usuario es posible que todos sean completos tipos personalizados.|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadata`|Clase base para representar la operación de metadatos para el sistema de destino. Por ejemplo, podría subclase OperationMetadata para contener información sobre los procedimientos almacenados en un adaptador de destino es una base de datos relacional.|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadataTraceRecord`|Proporciona una manera de capturar los metadatos de la operación en un archivo de seguimiento. El seguimiento recopila información como identificador único, última vez acceso, marca de tiempo, nombre para mostrar, nombre original, parámetros y otros detalles.|  
|`Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`|Proporciona una manera de definir los atributos de una operación como parámetros y tipo de valor devuelto.|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameter`|Describe un parámetro que se usa para invocar una operación en el sistema de destino. Las propiedades incluyen el nombre, el nombre original, dirección del parámetro y una marca que indica si el parámetro está vacío o no.|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameterDirection`|Un tipo enumerado que describe la dirección de un parámetro para una operación. Un parámetro puede ser entrante solo (PDA), solo saliente (salida) o bidireccional (InOut).|  
|`Microsoft.ServiceModel.Channels.Common.OperationResult`|Representa un resultado de la operación. Puede ser OperationResult.Empty para las operaciones que devuelven void o null y una cadena, entero u otro valor según la operación.|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedType`|Diseñado para ser la clase base para calificar las propiedades de tipo y se usa para describir las propiedades de metadatos de tipo para un sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedTypeContainer`|Proporciona un contenedor para un conjunto de tipos calificados relacionados.|  
|`Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`|Describe las propiedades de metadatos de tipo para un sistema de destino cuando ese tipo se asigna directamente a un tipo de esquema XSD de W3C. Para obtener una lista de tipos permitidos, consulte [XmlTypeCode enumeración](https://msdn.microsoft.com/library/system.xml.schema.xmltypecode(v=vs.110).aspx).|  
|`Microsoft.ServiceModel.Channels.Common.TypeMember`|Proporciona una manera de definir a un miembro de datos simples o complejos en los metadatos de tipo estructurado.|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadata`|Clase base para representar los metadatos de tipo para el sistema de destino.|  
|`Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`|Proporciona una manera de definir una estructura de datos que contiene a los miembros de tipo simple o complejo.|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataCollection`|Proporciona un contenedor para un conjunto de metadatos de tipo relacionado.|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataTraceRecord`|Proporciona una manera de capturar los metadatos de tipo en un archivo de seguimiento. El seguimiento recopila información como identificador único, acceder a última hora, marca de tiempo y otros detalles.|  

## <a name="custom-components"></a>Componentes personalizados  
 Componentes personalizados proporcionan compatibilidad con transacciones, seguridad, mensajería confiable y otras características que son altamente dependientes en el sistema de destino. Como programador de adaptadores mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], deberá comprender las capacidades del sistema de destino y determinar el grado al que desee admitirlos.  

## <a name="core-components"></a>Componentes principales  
 Componentes principales proporcionan un conjunto de clases base e interfaces que permiten el adaptador en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]. En la tabla siguiente, se describen los componentes principales.  


|                     Componente principal                      | ¿Requerido? |                                                                                                                                                                                          Descripción                                                                                                                                                                                          |
|---------------------------------------------------------|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `Microsoft.ServiceModel.Channels.Common.Adapter`     | Obligatorio  |                                                      La clase base de un adaptador escrito con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Es responsable de interactuar con el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal                                                      |
| `Microsoft.ServiceModel.Channels.Common.AdapterBinding` | Obligatorio  | Clase que contiene valores que controlan diversas configuraciones para el adaptador como la agrupación de conexiones (`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`), memoria caché (`Microsoft.ServiceModel.Channels.Common.CacheSettings`), los metadatos (`Microsoft.ServiceModel.Channels.Common.MetadataSettings`) y la mensajería (`Microsoft.ServiceModel.Channels.Common.MessagingSettings`). |

 Los adaptadores personalizados se exponen a través de enlaces de WCF. Para obtener más información, consulte la documentación de WCF en [ http://go.microsoft.com/fwlink/?LinkId=100308 ](http://go.microsoft.com/fwlink/?LinkId=100308).  

 El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] crear implementaciones de `Microsoft.ServiceModel.Channels.Common.Adapter`, `Microsoft.ServiceModel.Channels.Common.AdapterBinding`, `System.ServiceModel.Configuration.StandardBindingElement`, y `System.ServiceModel.Configuration.StandardBindingCollectionElement` para exponer el enlace del adaptador al sistema de configuración de WCF. El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] también generará una implementación de `System.ServiceModel.Configuration.BindingElementExtensionElement` para habilitar `Microsoft.ServiceModel.Channels.Common.Adapter` para su uso en un enlace personalizado de WCF desde un archivo de configuración de equipo o una aplicación.  

 Para obtener más información acerca de StandardBindingElement, StandardBindingCollectionElement y BindingElementExtensionElement, consulte la documentación de WCF.  

 Para obtener más información acerca de cómo configurar un adaptador escrito con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], consulte [implementar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md).  

## <a name="see-also"></a>Vea también  
 [Comprender el sistema LOB con el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)