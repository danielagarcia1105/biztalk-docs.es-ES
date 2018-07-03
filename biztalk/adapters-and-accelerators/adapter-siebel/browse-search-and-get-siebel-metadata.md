---
title: Examinar, buscar y obtener metadatos de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77a02e62bcea6a1647859b8578279ee97f2349d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980541"
---
# <a name="browse-search-and-get-siebel-metadata"></a>Examinar, buscar y obtener metadatos de Siebel
El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies metadatos en el sistema Siebel que describe la estructura del mensaje para la comunicación con un sistema de Siebel mediante el adaptador. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es compatible con dos interfaces para recuperar los metadatos.  
  
- MetadataExchange proporcionada por [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. WCF ofrece un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes obtener metadatos del sistema de Siebel.  
  
- IMetadataRetrievalContract proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], que es compatible con los metadatos de examinar y buscar las capacidades del adaptador.  
  
  El objetivo de la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] consiste en exponer el sistema Siebel como un servicio WCF. El adaptador expone los artefactos de Siebel (objetos de negocios y servicios empresariales) como operaciones que pueden invocar a los clientes del adaptador.  
  
  Los clientes del adaptador pueden examinar, buscar y recuperar metadatos mediante el modelo de servicio WCF, utilizando el modelo de canal WCF o mediante la creación de un BizTalk project en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Cuando se usa el modelo de servicio WCF, debe usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar las clases de proxy para realizar operaciones en el sistema Siebel. Cuando se usa un proyecto de BizTalk, debe usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar metadatos para las operaciones que desea realizar en el sistema Siebel. Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos utilizando la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).  
  
## <a name="browsing-metadata"></a>Examinar los metadatos  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes del adaptador examinar los objetos de negocios y servicios empresariales expuestos por el sistema Siebel. Como parte de la operación de exploración de metadatos, el adaptador clasifica los artefactos en varios niveles lógicos y expone una vista jerárquica de los metadatos a los clientes del adaptador. Los metadatos de un sistema de Siebel se clasifica por categorías en los nodos siguientes:  
  
- **Objetos de negocios**. Este nodo contiene los objetos de negocio en un sistema de Siebel, que es una colección lógica de componentes empresariales. Los objetos de negocio se clasifican como componentes empresariales. En el nivel más bajo de la jerarquía son las operaciones que se pueden invocar en los componentes empresariales.  
  
- **Servicios empresariales**. Este nodo contiene los servicios empresariales expuestos por un sistema Siebel. Un servicio de negocio de Siebel es una colección de métodos de servicio empresarial o funciones que se pueden invocar directamente en el sistema Siebel.  
  
  Para obtener más información acerca de cómo se clasifica por categorías los metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).  
  
## <a name="searching-metadata"></a>Buscar metadatos  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes del adaptador buscar metadatos en un sistema Siebel. Esto lo hace mediante el uso de expresiones de búsqueda compatible con Siebel LIKE (operador) en el campo [Name] del componente empresarial del repositorio Siebel utilizado para examinar los metadatos de Siebel válido. En la tabla siguiente se enumera los artefactos de Siebel y la jerarquía de metadatos en la que puede buscar.  
  
|Artefacto|Búsquedas en el nodo en la GUI|  
|--------------|----------------------------------------|  
|Objeto de negocios|/ Objetos de negocios|  
|Componente de negocio|O nombre del objeto de objetos o Business business|  
|Servicio de negocio|O los servicios business|  
  
 La tabla siguiente enumeran los caracteres especiales que se pueden usar para la búsqueda y su interpretación por el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|? (signo de interrogación)|Coincide exactamente con un carácter.<br /><br /> ¿Por ejemplo, un? coincide con AB, CA, AD|  
|* (asterisco)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un * coincide con A, AB ABC.|  
  
## <a name="retrieving-metadata"></a>Recuperar metadatos  
 Al recuperar los metadatos, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede extraer metadatos en un esquema, incluidos todos o un subconjunto de objetos de negocio o servicios de negocios con los parámetros de operación respectiva. Presenta las entidades en el sistema Siebel como nombres de elemento XML. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes del adaptador recuperar metadatos para el sistema de Siebel, incluidas características de los metadatos detallada:  
  
- Para los componentes empresariales, la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] recupera elementos tales como el nombre de objeto de negocios, nombre del componente empresarial, los nombres de campo, tipos de datos, longitudes de campo, campo obligatorio, campo opcional y campo de lista desplegable. El adaptador también recupera las operaciones posibles en el componente empresarial, como INSERT, UPDATE, DELETE y consulta.  
  
- Para los métodos de servicio empresarial, la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] recupera elementos tales como el nombre del servicio de negocio, el nombre del método (igual que la operación), parámetros de método y los tipos de datos de parámetro.  
  
  Para obtener más información acerca de cómo recuperar los metadatos, vea [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general del adaptador de BizTalk para las aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)