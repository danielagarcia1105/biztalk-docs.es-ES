---
title: Explorar, buscar y obtener metadatos de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metadata, retrieving
- metadata, surfacing
- retrieving, metadata
- metadata, browsing
- browsing, metadata
- metadata, searching
- searching, metadata
ms.assetid: 48fc3bb1-b949-4b8d-ab62-a41cd8c2f0a0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef1ed7d74b4e69f56c53beda8273533bb6891a55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-siebel-metadata"></a>Explorar, buscar y obtener metadatos de Siebel
El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies metadatos en el sistema Siebel que describe la estructura del mensaje para la comunicación con un sistema de Siebel utilizando el adaptador. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es compatible con dos interfaces para recuperar los metadatos.  
  
-   MetadataExchange proporcionada por [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. WCF proporciona un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes obtener metadatos del sistema Siebel.  
  
-   IMetadataRetrievalContract proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], que es compatible con los metadatos de exploración y búsqueda capacidades del adaptador.  
  
 El objetivo de la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] consiste en exponer el sistema Siebel como un servicio WCF. El adaptador de superficies de artefactos de Siebel (objetos de negocios y servicios de negocio) como las operaciones que los clientes de adaptador pueden invocar.  
  
 Los clientes de adaptador pueden examinar, buscar y recuperar metadatos mediante el modelo de servicio WCF, mediante el modelo de canal WCF o mediante la creación de un BizTalk project en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Al utilizar el modelo de servicio WCF, debe utilizar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar las clases de proxy para realizar operaciones en el sistema Siebel. Al utilizar un proyecto de BizTalk, debe utilizar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar metadatos para las operaciones que desea realizar en el sistema Siebel. Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).  
  
## <a name="browsing-metadata"></a>Examinar los metadatos  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes de adaptador examinar los objetos de negocios y los servicios de negocios expuestos por el sistema Siebel. Como parte de la operación de exploración de metadatos, el adaptador clasifica los artefactos en varios niveles lógicos y expone una vista jerárquica de los metadatos para los clientes de adaptador. Los metadatos de un sistema Siebel se clasifica por categorías en los nodos siguientes:  
  
-   **Objetos comerciales**. Este nodo contiene los objetos de negocio en un sistema Siebel, que es una colección lógica de componentes empresariales. Los objetos de negocio se clasifican como componentes empresariales. En el nivel más bajo de la jerarquía son las operaciones que se pueden invocar en los componentes empresariales.  
  
-   **Servicios para la empresa**. Este nodo contiene los servicios de negocios expuestos por un sistema Siebel. Un servicio de negocios de Siebel es una colección de métodos de servicio empresarial o funciones que se pueden invocar directamente en el sistema Siebel.  
  
 Para obtener más información acerca de cómo se clasifica por categorías de los metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).  
  
## <a name="searching-metadata"></a>Buscar metadatos  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes de adaptador buscar metadatos en un sistema Siebel. Esto lo hace mediante el uso de expresiones de búsqueda compatible con Siebel LIKE (operador) en el campo [Name] del componente de negocio de Siebel repositorio utilizado para la exploración de metadatos de Siebel válido. En la tabla siguiente se enumera los artefactos de Siebel y la jerarquía de metadatos en la que puede buscar.  
  
|Artefacto|Búsquedas en el nodo en la GUI|  
|--------------|----------------------------------------|  
|Objeto de negocios|O objetos de negocios|  
|Componente empresarial|O nombre del objeto de objetos/Business business|  
|Servicio de negocios|/ Servicios de negocio|  
  
 En la tabla siguiente se enumera los caracteres especiales que se pueden usar para buscar y su interpretación por la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|? (signo de interrogación)|Coincide exactamente con un carácter.<br /><br /> ¿Por ejemplo, un signo? coincide con AB, CA, AD|  
|* (asterisco)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un * encuentra una, AB, ABC.|  
  
## <a name="retrieving-metadata"></a>Recuperar metadatos  
 Al recuperar los metadatos, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede extraer metadatos en un esquema, incluidos todos los datos o un subconjunto de objetos comerciales o servicios de negocio con los parámetros de operación respectiva. Muestra las entidades en el sistema Siebel como nombres de elementos en XML. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes de adaptador recuperar metadatos para el sistema Siebel, incluidas las características de metadatos detallados:  
  
-   Para los componentes empresariales, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] recupera elementos tales como el nombre del objeto de negocios, el nombre del componente de negocio, los nombres de campo, tipos de datos, longitudes de campo, campo obligatorio, campo opcional y campo de lista desplegable. El adaptador también recupera las operaciones posibles en el componente empresarial, como INSERT, UPDATE, DELETE y consulta.  
  
-   Para los métodos de servicio de negocio, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] recupera elementos tales como el nombre del servicio de negocio, el nombre del método (igual que la operación), los parámetros de método y los tipos de datos de parámetro.  
  
 Para obtener más información acerca de cómo recuperar los metadatos, vea [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general del adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)