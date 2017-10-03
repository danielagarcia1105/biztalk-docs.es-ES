---
title: Explorar, buscar y obtener metadatos SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40cc1bd6592b38dbda9c9bff3ad01d6cdaf8a707
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-sap-metadata"></a>Explorar, buscar y obtener metadatos SAP
El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies metadatos desde el sistema SAP. Estos metadatos describen la estructura del mensaje para comunicarse con un sistema SAP mediante el adaptador. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con dos interfaces para recuperar los metadatos.  
  
-   **MetadataExchange** proporcionada por [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. WCF proporciona un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes obtener metadatos del sistema SAP.  
  
-   **IMetadataRetrievalContract** proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], que es compatible con los metadatos de exploración y búsqueda capacidades del adaptador.  
  
 Uno de los objetivos de la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] consiste en exponer el sistema SAP como un servicio WCF. El adaptador presenta los artefactos SAP (RFC, BAPI e idoc) como las operaciones que los clientes de adaptador pueden invocar. El adaptador también expone algunas operaciones específicas que pueden usarse para enviar o recibir IDOC desde un sistema SAP. Estas operaciones se enumeran más adelante en este tema.  
  
 Es posible examinar, buscar y recuperar metadatos mediante el modelo de servicio WCF, mediante el modelo de canal WCF o mediante la creación de un BizTalk project en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
 Al utilizar el modelo de servicio WCF, debe utilizar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar las clases de proxy para realizar operaciones en el sistema SAP. Al utilizar un proyecto de BizTalk, debe utilizar el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar metadatos para las operaciones que desea realizar en el sistema SAP.  
  
 Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos mediante [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md).  
  
## <a name="browsing-metadata"></a>Examinar los metadatos  
 El[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] permite a los clientes de adaptador examinar los RFC, tRFCs, BAPI e IDOC expuesto por el sistema SAP. Como parte de la operación de exploración de metadatos, el adaptador emerge la RFC y BAPI como operaciones. Para los IDOC, el adaptador de superficies de operaciones para enviar y recibir IDOC. Estas operaciones están disponibles en [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Los metadatos SAP se clasifica por categorías en los nodos siguientes:  
  
-   **RFC**. Este nodo contiene las RFC expuestas por el sistema SAP y representa un módulo de función en SAP. El adaptador clasifica los documentos RFC en varios niveles lógicos y expone una vista jerárquica a los clientes de adaptador. Una solicitud de cambio está en el nivel más bajo de esta jerarquía y se expone como una operación que se puede invocar con una aplicación externa. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC SDK se utiliza para generar los metadatos para las RFC. El adaptador puede invocar solo esas RFC para los que pueden generar los metadatos.  
  
     Distinto de los documentos RFC como operaciones así como la exposición, el adaptador también expone algunas operaciones específicas como **RfcGetAttributes**. Para obtener más información acerca de estas operaciones, vea [operaciones en RFC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).  
  
-   **TRFC**. Este nodo contiene el tRFCs expuesto por el sistema SAP. tRFCs no son un artefacto convencional en un sistema SAP, pero en su lugar un mecanismo para invocar las solicitudes de cambio. tRFCs se clasifican en un nodo independiente porque sus características de los metadatos son diferentes de las solicitudes de cambio. En concreto, las solicitudes de cambio también incluyen parámetros de exportación. El adaptador clasifica el tRFCs en varios niveles lógicos y expone una vista jerárquica a los clientes de adaptador. Un tRFC está en el nivel más bajo de esta jerarquía y se expone como una operación que se puede invocar con una aplicación externa.  
  
     Que no sea así como la exposición del tRFCs como operaciones, el adaptador también expone algunas operaciones específicas como **RfcConfirmTransID**. Para obtener más información acerca de estas operaciones, vea [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
  
-   **BAPI**. Este nodo contiene la BAPI expuesto por el sistema SAP. El adaptador clasifica el BAPI en varios niveles lógicos y expone una vista jerárquica a los clientes de adaptador. Una BAPI está en el nivel más bajo de esta jerarquía y se expone como una operación que se puede invocar con una aplicación externa.  
  
-   **IDOC**. Este nodo contiene el IDOC expuesto por un sistema SAP. El adaptador clasifica el IDOC en varios niveles lógicos y expone una vista jerárquica a los clientes de adaptador. Las operaciones que expone el adaptador para el IDOC son:  
  
    -   **Enviar** y **recibir**. Los clientes de adaptador pueden usar estas operaciones para enviar y recibir IDOC desde un sistema SAP mediante un esquema fuertemente tipado.  
  
    -   **SendIdoc** y **ReceiveIdoc**. Los clientes de adaptador pueden usar estas operaciones para enviar y recibir IDOC desde un sistema SAP mediante un esquema débilmente tipada.  
  
     Para obtener más información acerca de estas operaciones, vea [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).  
  
 Para obtener más información acerca de cómo se clasifica por categorías de metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).  
  
## <a name="searching-metadata"></a>Buscar metadatos  
 En el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], los clientes de adaptador pueden buscar metadatos en un sistema SAP mediante expresiones de búsqueda que dependen de los documentos de RFC subyacentes que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza. En la tabla siguiente se enumera los artefactos SAP y la jerarquía de metadatos en la que pueden buscar los clientes del adaptador.  
  
|Artefacto|Búsquedas en el nodo en la interfaz gráfica de usuario|  
|--------------|------------------------------------|  
|RFC|-/RFC<br />-/RFC/ [grupo de aplicaciones]|  
|TRFC|-/TRFC<br />-/TRFC/ [grupo de aplicaciones]|  
|BAPI|-/BAPI|  
|IDOC|-/IDOC|  
  
 En la tabla siguiente se enumera los caracteres especiales que se pueden usar para buscar y su interpretación por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|+ (más)|Coincide exactamente con un carácter.<br /><br /> Por ejemplo, A + coincide con AB, CA, AD|  
|* (asterisco)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un * encuentra una, AB, ABC.|  
  
## <a name="retrieving-metadata"></a>Recuperar metadatos  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] permite a los clientes de adaptador recuperar metadatos para el sistema SAP, incluidas las características de metadatos detallados:  
  
-   Para una solicitud de cambio, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera el nombre RFC junto con la importación, exportación, cambiar y parámetros de la tabla. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también recupera los tipos de datos para los parámetros, longitud de campo de los parámetros, además de a los parámetros obligatorios y opcionales.  
  
-   Para un tRFC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera detalles similares a la solicitud de cambio, con la excepción de los parámetros de exportación. Dado que las llamadas de tRFC son asincrónicas, no se recuperan parámetros de salida.  
  
-   Para una BAPI, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera el nombre del objeto de negocios, el nombre de método del objeto de negocios y otra información específica de similar a las solicitudes de cambio.  
  
-   Para un IDOC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera el tipo IDOC, el número de versión, la versión, los registros de control IDOC, registros de datos IDOC y otra información de segmento IDOC.  
  
    > [!NOTE]
    >  Si los metadatos para IDOC contienen valores altos y bajos (intervalo) para un tipo de datos, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] que expone como una cadena. Si los metadatos contienen solamente los valores bajos, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] que expone como una enumeración.  
  
> [!NOTE]
>  La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone los parámetros de función SAP en un orden alfabético, con independencia de cómo se ordenan los parámetros en la definición de función SAP. Esto es debido a las razones siguientes:  
>   
>  -   Diferentes versiones del SDK de RFC de SAP de devuelven los parámetros de función SAP en distintos órdenes. Por lo tanto, para proporcionar una experiencia coherente a los usuarios de adaptador, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone los parámetros en un orden alfabético.  
> -   Mismo RFC en distintos servidores SAP pudieron tener un orden diferente de exponer los parámetros de la función. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] realiza esta diferencia transparente a los usuarios mediante la exposición de los parámetros en un orden alfabético coherente.  
  
> [!NOTE]
>  Al recuperar datos desde el sistema SAP mediante la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] deserializar los mensajes que tienen más de 65536 nodos. Asegúrese de que el mensaje de respuesta tiene nodos menor o igual que 65536. Puede evitar esta limitación si modifica el archivo app.config para la aplicación. Para obtener instrucciones, consulte [solucionar problemas de funcionamiento](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md).  
  
 Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos, vea [obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)