---
title: Introducción a la arquitectura de SDK de adaptador LOB de WCF | Documentos de Microsoft
description: Introducción a los controladores, implementación de canal, administración de conexiones, metadatos y usar WSDL en el SDK de adaptador LOB de WCF
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dbd9b63c-54a4-4f63-b3a8-8600f6009a74
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd86d2104fff0e227d9cdda4c9fb3faf1ea7cb84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226628"
---
# <a name="architecture-overview-of-the-wcf-lob-adapter-sdk"></a>Introducción a la arquitectura de SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se basa en el modelo de canal de WCF y proporciona extensiones de tiempo de diseño y tiempo de ejecución para los programadores del adaptador crear adaptadores en sistemas de línea de negocio que tengan metadatos grande y dinámico. Un adaptador creado mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparece al consumidor como un enlace personalizado de WCF. En la siguiente ilustración muestra la arquitectura interna y los componentes principales del SDK de adaptador LOB de WCF.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7183bded-465e-45b9-af78-fbb87cf2df92.gif "7183bded-465e-45b9-af78-fbb87cf2df92")  
  
## <a name="handlers"></a>Controladores  
 *Controlador* define los patrones de intercambio de mensajes admitidos por el adaptador.  
  
 En la tabla siguiente se resume los tipos de controlador disponible, su función y el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canales que se asignan.  
  
|**Tipo de controlador**|**Función**|**Se asigna a los canales de WCF.**|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|Admite el envío unidireccional o patrón de solicitud/respuesta.|IOutputChannel,<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|Admite el envío unidireccional asincrónico o patrón de solicitud/respuesta.|IOutputChannel,<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|Admite unidireccional de recepción o patrones de respuesta.|IInputChannel,<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|Admite variantes asincrónicas de métodos unidireccionales de recepción o patrones de respuesta.|IInputChannel<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|Admite la exploración de metadatos en el sistema de destino.|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|Admite la búsqueda de metadatos en el sistema de destino.|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|Admite la recuperación de metadatos desde el sistema de destino.|IRequestChannel|  
  
## <a name="channel-implementation"></a>Implementación de canal  
 Un adaptador que se generan con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es básicamente un canal de transporte (System.ServiceModel.Channels.IServiceListner). Un adaptador que se generan con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparece al consumidor como un enlace WCF, donde el enlace se utiliza para crear la pila de canales. Este enlace puede considerarse como un elemento del mismo nivel para otros enlaces de WCF predefinidos como BasicHttpBinding, WsHttpBinding, NetTcpBinding y puede establecerse a través de app.config o en código de la aplicación cliente al llamar a un servicio. Este enlace contiene un conjunto ordenado de elementos de enlace con el adaptador está el elemento de enlace de clave que se deriva de la clase T:System.ServiceModel.Channels.TransportBindingElement. En un escenario de salida, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en tiempo de ejecución usa un generador de canales para crear el adaptador (es decir, el canal de transporte). En un escenario de entrada, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en tiempo de ejecución hace uso de agentes de escucha del canal para los canales entrantes en una aplicación de servicio.  Mensajes de tiempo de ejecución así como tiempo de diseño se pasan a través de este componente.  
  
## <a name="connection-factory-connection-and-connection-uri-builder"></a>Generador URI de fábrica, conexión y conexión de conexión  
 *ConnectionFactory* proporciona un modelo de generador para crear conexiones basadas en URI y credenciales de usuario. Para obtener más información, consulte `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`.  
  
 *Conexión* define un contrato de comunicaciones de nivel inferior con el sistema de destino y encapsula identificadores de conexión y las API de comunicación nativo. Para obtener más información, consulte `Microsoft.ServiceModel.Channels.Common.IConnection`.  
  
 El *generador de Uri de conexión* permite que los consumidores de adaptador crear mediante programación conexión URI sin un conocimiento específico de sintaxis. Para obtener más información, consulte `Microsoft.ServiceModel.Channels.Common.ConnectionUri`.  
  
## <a name="connection-management"></a>Administración de las conexiones  
 *Administración de conexiones* es responsable de la administración de la duración de las conexiones de un adaptador. Internamente mantiene un grupo de conexiones de listo para su uso. Este grupo de conexiones es credencial y basado en URI. La credencial contiene un nombre de usuario y contraseña que definen el contexto de seguridad de la conexión se ejecuta bajo.  
  
 Cuando se usan las mismas credenciales y URI, cualquiera de los canales que se abre en la misma fábrica de conexión obtiene la conexión del grupo si hay uno disponible.  
  
 Administrador de conexiones de grupo guarda los registros de cuántas conexiones abiertas que hay a ese URI independientemente de las credenciales y por los límites del generador del canal. Por ejemplo, en un sistema, puede tener dos usuarios que tienen credenciales diferentes, lo que significa que hay dos generadores de canales que se conecte al sistema.  
  
> [!NOTE]
>  El adaptador puede ser limitado en relación con el número de conexiones puede admitir, generalmente limitado por los recursos del sistema.  
  
 Para ayudar a los programadores del adaptador a configurar las opciones de grupo de conexión, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona dos clases, `Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings` y `Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`.  
  
## <a name="metadata-management"></a>Administración de metadatos  
 *Administración de metadatos* es responsable de la representación orientada a objetos del almacenamiento en caché de los metadatos del sistema de destino. Metadatos se pueden guardar en una memoria caché común accesible a través de todas las credenciales, o puede ser almacenados en caché base por cada credencial.  
  
 El ciclo de vida de metadatos comienza con sus definiciones de tiempo de diseño y continúa a través del uso en tiempo de ejecución. En tiempo de diseño, los programadores del adaptador deben identificar el conjunto de operaciones y deben generar al proxy del lado WSDL y cliente necesario. En tiempo de ejecución, los adaptadores basados en el marco de trabajo usan la metadatos predefinidos para interpretar los mensajes devueltos por las llamadas del sistema de destino.  
  
 Para ayudar a los escritores del adaptador a configurar la configuración de metadatos, el marco de trabajo proporciona tres clases `Microsoft.ServiceModel.Channels.Common.CacheSettings`, `Microsoft.ServiceModel.Channels.Common.MetadataSettings` y `Microsoft.ServiceModel.Channels.Common.CommonCacheSettings`.  
  
## <a name="wsdl-builder"></a>Generador de WSDL  
 *El generador de WSDL* proporciona la generación automática de WSDL del modelo de objetos de metadatos interno de la WCF SDK de adaptador LOB (se puede invalidar para escenarios que requieren la generación de WSDL personalizado).  
  
 Consulte `Microsoft.ServiceModel.Channels.Common.IWsdlRetrieval` para obtener más información.  
  
## <a name="metadata-browsesearch"></a>Búsqueda de exploración de metadatos  
 *Búsqueda de exploración de metadatos* permite examinar y buscar todos los metadatos LOB.  
  
 Para obtener más información, consulte `Microsoft.ServiceModel.Channels.IMetadataRetrievalContract`.  
  
## <a name="metadata-generation"></a>Generación de metadatos  
 *Generación de metadatos* permite la generación de código para el cliente (para escenarios de salida) y para el servicio (para escenarios de entrada) en función de las operaciones seleccionadas por el consumidor de adaptador. Aunque se recomienda que los consumidores de adaptadores usan las herramientas de [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] ([!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] en el caso de aplicaciones de BizTalk), el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una interfaz pública `Microsoft.ServiceModel.Channels.MetadataRetrievalClient.GetMetadata%2A` para recuperar el System.Web.Services.Description.ServiceDescription, que representa un lenguaje de descripción de servicio de Web (WSDL) que contiene información sobre operaciones seleccionadas y tipos. Cometen los escritores de adaptador utiliza el modelo de objetos de metadatos para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] que incluye las clases derivadas de `Microsoft.ServiceModel.Channels.Common.OperationMetadata` y `Microsoft.ServiceModel.Channels.Common.TypeMetadata` para describir los detalles de cada operación y el tipo.  
  