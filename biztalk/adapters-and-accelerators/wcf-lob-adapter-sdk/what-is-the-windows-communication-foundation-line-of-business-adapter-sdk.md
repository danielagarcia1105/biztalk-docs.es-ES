---
title: "¿Qué es la línea de negocio SDK del adaptador de Windows Communication Foundation | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc690e8f-fd37-44b5-a277-89952e631ae6
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084201d9680cb8d17c37c2218ebe7622c4cc4495
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-windows-communication-foundation-line-of-business-adapter-sdk"></a>¿Qué es la línea de negocio SDK del adaptador de Windows Communication Foundation
Información general sobre las características y componentes en la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. En este tema también describe los conceptos básicos, incluidos los metadatos, la administración de conexión y términos que debe conocer, como el enlace y el canal.

## <a name="features-overview"></a>Introducción a las características
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se ha diseñado para satisfacer las necesidades de los desarrolladores que crean adaptadores que exponen los datos y las operaciones de los sistemas de línea de negocio. Algunas de las características proporcionadas por el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] incluyen:  
  
-   Un mecanismo coherente para exponer los protocolos de transporte y de datos
  
-   Exposición del adaptador como un enlace de WCF
  
-   Extensibilidad a través de la arquitectura de canal WCF
  
-   [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]
  
-   Búsqueda de metadatos común y la interfaz de usuario de exploración mediante el[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]integración de tiempo de diseño con la[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]
  
 Dado que la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es una extensión a WCF, también proporciona las siguientes características:  
  
-   Una unificación de las tecnologías de comunicación de .NET Framework existentes
  
-   Compatibilidad con la interoperabilidad entre proveedores, incluidos la confiabilidad, seguridad y transacciones
  
-   Una orientación a servicios explícita
  
## <a name="components-overview"></a>Información general de componentes
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una experiencia coherente y repetible para el desarrollador de adaptadores y el consumidor de adaptador a través de un conjunto de componentes de tiempo de diseño y tiempo de ejecución, un modelo de objetos .NET y componentes de soporte técnico incluidos:  
  
|Componente|Description|  
|---------------|-----------------|  
|[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]|Proporciona instrucciones paso a paso de la creación de [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] dentro de los proyectos [!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)].|  
|[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]|Proporciona instrucciones paso a paso para crear un proyecto Web para hospedar un adaptador en Internet Information Services (IIS).|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]sistema de tiempo de ejecución|Admite la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] extendiendo la WCF channel arquitectura y proporcionan otros servicios de tiempo de ejecución.|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]modelo de objetos|Una colección de clases, tipos e interfaces que permiten realizar tareas comunes de adaptador, como la normalización de metadatos, el almacenamiento en caché, administración de conexiones y la agrupación y mensajería inspección.|  
|[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]|Permite a las aplicaciones .NET personalizadas para consumir adaptadores desarrollados con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].|  
|[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]|Proporciona [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] la posibilidad de consumir adaptadores desarrollados con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].|  

## <a name="sdk-fundamentals"></a>Conceptos básicos SDK  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] consta de un tiempo de ejecución, una colección de API y herramientas en tiempo de diseño para la creación de adaptadores que exponen datos y las operaciones de sistemas de línea de negocio. Adaptadores de administración mensajes entre el consumidor del adaptador y el sistema de línea de negocio y pueden consistir en metadatos, datos u otra información.  
  
### <a name="metadata"></a>Metadatos  
 Una de las características distintivas de un adaptador escrito con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el otro se implementan utilizando el modelo de objetos de modelo de servicio de Windows Communication Foundation (WCF) metadatos. Los metadatos describen los datos, las operaciones, propiedades y otras características dinámicas de un sistema y se usan por el consumidor de adaptador para detectar, consumir e interactuar con un sistema de destino.  
  
 Un ciclo programación del servicio WCF típica incluye un programador del servicio WCF crear y hospedar un servicio. Un punto de conexión de servicio WCF consta de una dirección, un enlace y un contrato, también se conoce como el "A, B y del C" de WCF.  La dirección es la ubicación del servicio, mientras que el enlace especifica los protocolos y los transportes utilizados para comunicarse con el servicio.  Un programador del servicio WCF define un contrato con el modelo de objetos de System.ServiceModel de WCF, proporciona su implementación en el formulario de un servicio WCF y lo hospeda con ServiceHost. SvcUtil.exe o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] puede utilizarse para crear el cliente correspondiente a los metadatos del servicio publicado. Una vez que el servicio está en funcionamiento, se puede ejecutar la herramienta de tiempo de diseño en la dirección del extremo de servicio para generar al proxy WCF en un idioma preferido y un archivo app.config para la implementación del cliente que se corresponde con los detalles del servicio WCF.  
  
 Un programador de adaptadores LOB de WCF, por otro lado, implementa el modelo de objetos de metadatos proporcionado en la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] para definir las operaciones y los tipos admitidos por el adaptador. Puesto que el adaptador de salida es un enlace personalizado de WCF, está hospedado en proceso dentro de la aplicación de consumidor.  Una vez que el adaptador está instalado en un equipo, [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] puede utilizarse para examinar y buscar los metadatos y para generar, por consiguiente, el proxy WCF en un idioma preferido junto con un archivo app.config que contiene los detalles de configuración. El contrato se crea y genera a petición mediante el adaptador de WCF LOB consultando los metadatos activos disponibles en el sistema de línea de negocio.  
  
 Por ejemplo, un sistema de línea de negocio que realizan la adjudicación distintos tipos de notificaciones de atención sanitaria y puede contener una creciente recopilación de operaciones exclusivas, tipos de datos, reglas de negocios y los informes creados por los usuarios del sistema. Si esta información se expone como un contrato estático, tiene que modificarse como nuevos negocios objetos se agregan al sistema o simplemente no proporcionan acceso a los nuevos objetos de negocios. Sin embargo, si información sobre el objeto de negocio dinámicas en el sistema de adjudicación de notificaciones es examinable (y que permiten búsqueda), nuevos objetos como una nueva regla de validación para notificaciones institucionales o un nuevo informe se exponen y pueden ser utilizados.  
  
### <a name="connection-management"></a>Administración de conexiones  
 Para poder intercambiar información con el sistema de línea de negocio, el adaptador debe establecer una conexión. Una conexión vincula el adaptador (consumidor) con el sistema de línea de negocio (el proveedor) y controla el ciclo de vida de conexión incluidos abrir, cerrar, se cancelará y comprobar la validez de la conexión. En función de los requisitos del sistema de línea de negocio, la conexión puede requerir una o varias credenciales y parámetros de conexión, como el nombre del servidor, el directorio predeterminado o el número de puerto.  
  
 Duración de la conexión se administra mediante un grupo de conexiones. Cuando se solicita una nueva conexión mediante el adaptador, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una conexión existente si está disponible; en caso contrario, una nueva conexión se creará y colocada en el grupo y, a continuación, se proporciona al adaptador. Cuando el adaptador se realiza con la conexión, se coloca en el grupo. Las conexiones que están inactivas más allá de un umbral determinado se cierran y se quita del grupo.  
  
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es una extensión de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], un modelo de programación unificado para crear aplicaciones orientadas a servicios con código administrado. Adaptadores escritos mediante la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparecen como [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces que pueden ser utilizados por cualquier aplicación compatible con WCF.  
  
## <a name="important-terms"></a>Términos importantes  

| | |
|---|---|
| enlazar | Define cómo se comunica un adaptador. Se crean enlaces por el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y definir el transporte, codificación y otros detalles. Puede haber uno o más elementos de enlace en un enlace. |
|canal | La implementación de un elemento de enlace. Colecciones de canales para una pila de enlace encima de otra para crear una pila de canales. |
| message  |  Una unidad independiente de los datos que pueden estar compuestos de varias partes, incluyendo un cuerpo y encabezados.|
| metadatos | Describe las características del sistema de línea de negocio que incluya las operaciones y los datos que están disponibles.|
| operación | Las funciones y los métodos expuestos por un sistema de línea de negocio. Funcionan en los datos y realizar actividades útiles como contratante notificaciones, crear un pedido o consultar los datos de ventas.  |
 
   
## <a name="see-also"></a>Vea también  
 [BizTalk Server y el SDK del adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/using-biztalk-server-and-the-wcf-lob-adapter-sdk.md)   
   [Tutoriales del SDK de adaptador de LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)