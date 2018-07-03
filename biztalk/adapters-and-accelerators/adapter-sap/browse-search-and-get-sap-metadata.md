---
title: Examinar, buscar y obtener metadatos de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata
- adapters, surfacing metadata
- TRFC
- RFC
- metadata, browsing, searching, retrieving
- adapters, operations
- BAPI
- IDOC
ms.assetid: 5f0d7c1f-d6e1-4c56-8d8e-1f5d537aa3ce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa942786cda8c5e1070b3fa1c66e3300ffd16d4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984061"
---
# <a name="browse-search-and-get-sap-metadata"></a>Examinar, buscar y obtener metadatos de SAP
El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies metadatos desde el sistema SAP. Estos metadatos describen la estructura del mensaje para la comunicación con un sistema SAP mediante el adaptador. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con dos interfaces para recuperar los metadatos.  
  
- **MetadataExchange** proporcionada por [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. WCF ofrece un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes obtener metadatos del sistema SAP.  
  
- **IMetadataRetrievalContract** proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], que es compatible con los metadatos de examinar y buscar las capacidades del adaptador.  
  
  Uno de los objetivos de la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] consiste en exponer el sistema SAP como un servicio WCF. El adaptador presenta los artefactos SAP (RFC, BAPI e idoc) como las operaciones que pueden invocar a los clientes del adaptador. El adaptador también expone algunas operaciones específicas que pueden usarse para enviar o recibir los IDOC desde un sistema SAP. Estas operaciones se muestran más adelante en este tema.  
  
  Es posible examinar, buscar y recuperar metadatos mediante el modelo de servicio WCF, utilizando el modelo de canal WCF o mediante la creación de un BizTalk project en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
  Cuando se usa el modelo de servicio WCF, debe usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar las clases de proxy para realizar operaciones en el sistema SAP. Cuando se usa un proyecto de BizTalk, debe usar el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar metadatos para las operaciones que desea realizar en el sistema SAP.  
  
  Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos mediante [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md).  
  
## <a name="browsing-metadata"></a>Examinar los metadatos  
 El[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] permite a los clientes del adaptador examinar el RFC, trfc, BAPI e IDOC expuestos por el sistema SAP. Como parte de la operación de exploración de metadatos, el adaptador presenta las RFC y BAPI como operaciones. Para los IDOC, el adaptador expone las operaciones para enviar y recibir los IDOC. Estas operaciones están disponibles en [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Los metadatos SAP se clasifica por categorías en los nodos siguientes:  
  
- **RFC**. Este nodo contiene las especificaciones de RFC expuestos por el sistema SAP y representa un módulo de función en SAP. El adaptador clasifica los RFC en varios niveles lógicos y expone una vista jerárquica a los clientes del adaptador. Una solicitud de cambio está en el nivel más bajo de esta jerarquía y se expone como una operación que se puede invocar una aplicación externa. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa el SDK de RFC para generar metadatos para los documentos RFC. El adaptador puede invocar solo esas especificaciones RFC para el que pueden generar los metadatos.  
  
   Distinto de exponer las RFC como operaciones, el adaptador también expone algunas operaciones específicas como **RfcGetAttributes**. Para obtener más información acerca de estas operaciones, consulte [operaciones en RFC de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).  
  
- **TRFC**. Este nodo contiene las trfc expuestas por el sistema SAP. trfc no es un artefacto convencional en un sistema SAP, pero en su lugar un mecanismo para invocar RFC. trfc se clasifican en un nodo diferente porque sus características de los metadatos son diferentes de las solicitudes de cambio. En concreto, las solicitudes de cambio también incluyen parámetros de exportación. El adaptador clasifica las trfc en varios niveles lógicos y expone una vista jerárquica a los clientes del adaptador. Un tRFC es en el nivel más bajo de esta jerarquía y se expone como una operación que se puede invocar una aplicación externa.  
  
   Distinto de exponer las trfc como operaciones, el adaptador también expone algunas operaciones específicas como **RfcConfirmTransID**. Para obtener más información acerca de estas operaciones, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
  
- **BAPI**. Este nodo contiene las BAPI expuestas por el sistema SAP. El adaptador clasifica las BAPI en varios niveles lógicos y expone una vista jerárquica a los clientes del adaptador. Una BAPI es en el nivel más bajo de esta jerarquía y se expone como una operación que se puede invocar una aplicación externa.  
  
- **IDOC**. Este nodo contiene el IDOC expuesto por un sistema SAP. El adaptador clasifica lo IDOC en varios niveles lógicos y expone una vista jerárquica a los clientes del adaptador. Las operaciones que expone el adaptador para el IDOC son:  
  
  - **Enviar** y **recibir**. Los clientes del adaptador pueden usar estas operaciones para enviar y recibir los IDOC desde un sistema SAP con un esquema fuertemente tipado.  
  
  - **SendIdoc** y **ReceiveIdoc**. Los clientes del adaptador pueden usar estas operaciones para enviar y recibir los IDOC desde un sistema SAP con un esquema débilmente tipada.  
  
    Para obtener más información acerca de estas operaciones, consulte [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).  
  
  Para obtener más información acerca de cómo se clasifica por categorías de metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).  
  
## <a name="searching-metadata"></a>Buscar metadatos  
 En el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], los clientes del adaptador pueden buscar metadatos en un sistema SAP mediante el uso de expresiones de búsqueda que dependen de las especificaciones de RFC subyacentes que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa. En la tabla siguiente se enumera los artefactos SAP y la jerarquía de metadatos en la que pueden buscar los clientes del adaptador.  
  
|Artefacto|Búsquedas en el nodo en la interfaz gráfica de usuario|  
|--------------|------------------------------------|  
|RFC|-/RFC<br />-/RFC/ [grupo de aplicaciones]|  
|tRFC|-/TRFC<br />-/TRFC/ [grupo de aplicaciones]|  
|BAPI|-/BAPI|  
|IDOC|-/IDOC|  
  
 La tabla siguiente enumeran los caracteres especiales que se pueden usar para la búsqueda y su interpretación por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|+ (más)|Coincide exactamente con un carácter.<br /><br /> Por ejemplo, A + coincide con AB, CA, AD|  
|* (asterisco)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un * coincide con A, AB ABC.|  
  
## <a name="retrieving-metadata"></a>Recuperar metadatos  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] permite a los clientes del adaptador recuperar metadatos para el sistema SAP, incluidas características de los metadatos detallada:  
  
- Para una solicitud de cambio, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera el nombre RFC junto con la importación, exportación, cambio y parámetros de la tabla. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también recupera los tipos de datos para los parámetros de longitud de campo de los parámetros, además de los parámetros obligatorios y opcionales.  
  
- Para un tRFC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera detalles similares a la RFC, a excepción de los parámetros de exportación. Dado que las llamadas de tRFC son asincrónicas, no se recuperan parámetros de salida.  
  
- Para una BAPI, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera el nombre de objeto de negocios, el nombre de método del objeto de negocios y otra información específica de similar a las solicitudes de cambio.  
  
- Para un IDOC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera el tipo IDOC, el número de versión, la versión, los registros de control IDOC, registros de datos IDOC y otra información de segmento IDOC.  
  
  > [!NOTE]
  >  Si los metadatos para IDOC contienen valores altos y bajos (intervalo) para un tipo de datos, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] que expone como una cadena. Si los metadatos contienen solo valores bajos, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] que expone como una enumeración.  
  
> [!NOTE]
>  La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone los parámetros de función SAP en un orden alfabético, con independencia de cómo se ordenan los parámetros en la definición de función SAP. Esto es debido a las razones siguientes:  
> 
> - Diferentes versiones del SDK de RFC de SAP de devuelven los parámetros de función SAP en distintos órdenes. Por lo tanto, con el fin de proporcionar una experiencia coherente a los usuarios de adaptador, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone los parámetros en un orden alfabético.  
>   - Mismas RFC en distintos servidores SAP podrían tener un orden diferente de exponer los parámetros de función. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] hace que esta diferencia transparente a los usuarios mediante la exposición de los parámetros en un orden alfabético coherente.  
> 
> [!NOTE]
>  Al recuperar datos desde el sistema SAP mediante la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] deserializar los mensajes que tienen más de 65536 nodos. Asegúrese de que el mensaje de respuesta tiene nodos menor o igual a 65536. Puede evitar esta limitación si modifica el archivo app.config para su aplicación. Para obtener instrucciones, consulte [solucionar problemas de funcionamiento](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md).  
  
 Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos, vea [obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)