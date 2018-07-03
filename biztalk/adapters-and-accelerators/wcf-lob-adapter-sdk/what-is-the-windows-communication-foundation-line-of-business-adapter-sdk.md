---
title: ¿Qué es la línea de negocio SDK del adaptador de Windows Communication Foundation | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc690e8f-fd37-44b5-a277-89952e631ae6
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ada608dbac8071af182c26af02c8f47b43e6cca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011989"
---
# <a name="what-is-the-windows-communication-foundation-line-of-business-adapter-sdk"></a>¿Qué es la línea de negocio SDK del adaptador de Windows Communication Foundation
Información general de las características y componentes en el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. En este tema también describe los conceptos clave, incluidos los metadatos, administración de conexiones y términos que debe conocer, como el enlace y el canal.

## <a name="features-overview"></a>Introducción a las características
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se diseñó para satisfacer las necesidades de los desarrolladores que crean los adaptadores que exponen los datos y las operaciones de los sistemas de línea de negocio. Algunas de las características proporcionadas por el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] incluyen:  
  
- Un mecanismo coherente para exponer los protocolos de transporte y de datos
  
- Exposición del adaptador como un enlace WCF
  
- Extensibilidad a través de la arquitectura de canal WCF
  
- [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]
  
- Búsqueda de metadatos comunes y la interfaz de usuario de exploración mediante la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] integración de tiempo de diseño con el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]
  
  Dado que el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es una extensión a WCF, también proporciona las siguientes características:  
  
- Una unificación de las tecnologías de comunicación existentes de .NET Framework
  
- Compatibilidad con la interoperabilidad entre proveedores, incluyendo confiabilidad, seguridad y transacciones
  
- Una orientación a servicios explícita
  
## <a name="components-overview"></a>Información general de componentes
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una experiencia coherente y repetible para el programador de adaptadores y el consumidor de adaptador a través de un conjunto de componentes de tiempo de diseño y tiempo de ejecución, un modelo de objetos .NET y componentes de soporte técnico incluido:  
  

|                                        Componente                                        |                                                                                                       Descripción                                                                                                        |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]        |         Proporciona una guía paso a paso para la creación de [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proyectos dentro de [!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)].         |
|            [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]            |                                                   Proporciona instrucciones paso a paso en la creación de un proyecto Web para hospedar un adaptador de Internet Information Services (IIS).                                                    |
| [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] sistema de tiempo de ejecución |                          Admite la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] mediante la extensión de WCF, canales arquitectura y proporcionar otros servicios de tiempo de ejecución.                           |
|  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] modelo de objetos   |                  Una colección de clases, tipos e interfaces que respaldan tareas habituales de adaptador, como la normalización de los metadatos, almacenamiento en caché, administración de conexiones y la agrupación y mensajería de inspección.                  |
|     [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]     |                               Permite a las aplicaciones de .NET personalizadas para consumir los adaptadores desarrollados con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].                                |
|    [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]    | Proporciona [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] la capacidad de consumir los adaptadores desarrollados mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. |

## <a name="sdk-fundamentals"></a>Aspectos básicos SDK  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] consta de un tiempo de ejecución, una colección de API y herramientas de tiempo de diseño para crear los adaptadores que exponen los datos y las operaciones de sistemas de línea de negocio. Adaptadores de administración los mensajes entre el consumidor del adaptador y el sistema de línea de negocio y pueden constar de metadatos, datos u otra información.  

### <a name="metadata"></a>Metadatos  
 Una de las características distintivas de un adaptador escrito con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y uno se implementa mediante el modelo de objetos de modelo de servicio de Windows Communication Foundation (WCF) es los metadatos. Los metadatos describen los datos, operaciones, propiedades y otras características de un sistema dinámicos y se usan por el consumidor del adaptador para detectar, consumir e interactuar con un sistema de destino.  

 Un ciclo programación del servicio WCF típica incluye un programador del servicio WCF crea y aloja un servicio. Un punto de conexión de servicio WCF consta de una dirección, un enlace y un contrato, también se conoce como la "A, B y del C" de WCF.  La dirección es la ubicación del servicio, mientras que el enlace especifica los protocolos y los transportes utilizados para comunicarse con el servicio.  Un programador del servicio WCF define un contrato mediante el modelo de objetos de System.ServiceModel de WCF, proporciona su implementación en forma de un servicio WCF y lo hospeda con ServiceHost. SvcUtil.exe o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] se puede usar para compilar el cliente correspondiente a los metadatos del servicio publicado. Una vez que el servicio está en funcionamiento, se puede ejecutar la herramienta de tiempo de diseño en la dirección del punto de conexión de servicio para generar al proxy de WCF en un idioma preferido y un archivo app.config para la implementación del cliente que se corresponde con los detalles del servicio WCF.  

 Un programador de adaptadores LOB de WCF, por otro lado, implementa el modelo de objetos de metadatos proporcionado en el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] para definir las operaciones y los tipos admitidos por el adaptador. Puesto que el adaptador de salida es un enlace personalizado de WCF, está hospedado en un proceso dentro de la aplicación de consumidor.  Una vez que el adaptador está instalado en un equipo, [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] puede usarse para examinar y buscar metadatos y generar en consecuencia el proxy de WCF en un lenguaje preferido, junto con un archivo app.config que contiene los detalles de configuración del adaptador. El contrato se crea y genera a petición para el adaptador de WCF LOB consultando los metadatos en vivo disponibles en el sistema de línea de negocio.  

 Por ejemplo, un sistema de línea de negocio que realizan la adjudicación diferentes tipos de reclamaciones de atención médica y puede contener una colección creciente de operaciones únicas, los tipos de datos, las reglas de negocios y los informes creados por los usuarios del sistema. Si esta información se expone como un contrato estática, debe modificarse como nuevos negocios objetos se agregan al sistema o simplemente no proporcionan acceso a los nuevos objetos de negocios. Sin embargo, si la información sobre el objeto de negocio dinámicas en el sistema de notificaciones adjudicación es examinable (y que se pueden buscar), nuevos objetos como una nueva regla de validación para las reclamaciones institucionales o un nuevo informe se exponen y se pueden consumir.  

### <a name="connection-management"></a>Administración de conexiones  
 Para poder intercambiar información con el sistema de línea de negocio, el adaptador debe establecer una conexión. Una conexión vincula el adaptador (consumidor) en el sistema de línea de negocio (el proveedor) y controla el ciclo de vida de la conexión como abrir, cerrar, anulando y comprobar la validez de la conexión. Según los requisitos del sistema de línea de negocio, la conexión puede requerir una o varias de las credenciales y parámetros de conexión como nombre del servidor, el directorio predeterminado o el número de puerto.  

 Duración de la conexión se administra mediante un grupo de conexiones. Cuando se solicita una nueva conexión mediante el adaptador, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una conexión existente si uno está disponible; en caso contrario, se crea una nueva conexión y se coloca en el grupo de y, a continuación, se proporciona al adaptador. Cuando el adaptador se realiza con la conexión, se coloca en la agrupación. Las conexiones que están inactivas más allá de un umbral determinado se cierran y se quita del grupo.  

### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es una extensión de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], un modelo de programación unificado para crear aplicaciones orientadas a servicios con código administrado. Adaptadores escritos mediante la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparecen como [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces que pueden utilizarse en cualquier aplicación compatible con WCF.  

## <a name="important-terms"></a>Términos importantes  

|           |                                                                                                                                                                                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  enlazar  | Define cómo se comunica un adaptador. Los enlaces se crean mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y definir el transporte, codificación y otros detalles. Puede haber uno o más elementos de enlace en un enlace. |
|  canal  |                                                          La implementación de un elemento de enlace. Colecciones de canales para una pila de enlace en la parte superior entre sí para crear una pila de canales.                                                           |
|  message  |                                                                              Una unidad autónoma de datos que pueden constar de varias partes, incluyendo un cuerpo y encabezados.                                                                              |
| metadatos  |                                                                   Describe las características del sistema de línea de negocio, incluidas las operaciones y los datos que están disponibles.                                                                    |
| operación |                             Las funciones y métodos expuestos por un sistema de línea de negocio. Funcionan en los datos y realizar actividades útiles como contratante notificaciones, creación de un pedido o consultar los datos de ventas.                              |
   
## <a name="see-also"></a>Vea también  
 [BizTalk Server y el SDK del adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/using-biztalk-server-and-the-wcf-lob-adapter-sdk.md)   
   [Tutoriales del SDK de adaptador de LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)