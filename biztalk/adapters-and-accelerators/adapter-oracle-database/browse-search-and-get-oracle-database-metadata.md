---
title: Explorar, buscar y obtener los metadatos de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MetadataExchange
- metadata, searching
- metadata, browsing
- POLLINGSTMT
- metadata, retrieving
- IMetadataRetrievalContract
- SQLEXECUTE
ms.assetid: 828d5a8e-f0a3-47b4-8298-5571cff64b52
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765663d51fa1bab4f700aa3aff726085e5464716
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-oracle-database-metadata"></a>Explorar, buscar y obtener los metadatos de la base de datos de Oracle
El[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies de metadatos de la base de datos de Oracle que describe la estructura del mensaje para la comunicación con la base de datos de Oracle mediante el adaptador. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con dos interfaces para recuperar los metadatos.  
  
-   MetadataExchange proporcionada por [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. WCF proporciona un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes obtener metadatos de la base de datos de Oracle.  
  
-   IMetadataRetrievalContract proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], que es compatible con los metadatos de exploración y búsqueda capacidades del adaptador.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] artefactos y operaciones respectivas que los clientes de adaptador pueden invocar la base de datos superficies de Oracle. El adaptador también expone las operaciones de SQLEXECUTE, POLLINGSTMT y notificación que pueden utilizarse para realizar operaciones específicas en la base de datos de Oracle. Estas operaciones se describen más adelante en este tema.  
  
 Los clientes de adaptador pueden examinar, buscar y recuperar metadatos mediante el modelo de canal WCF, mediante el modelo de servicio WCF o mediante la creación de un proyecto de BizTalk en Visual Studio. Al utilizar el modelo de servicio WCF, debe utilizar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar las clases de proxy para realizar operaciones en la base de datos de Oracle. Al utilizar un proyecto de BizTalk, debe utilizar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar metadatos para las operaciones que desea realizar en la base de datos de Oracle. Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos mediante [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], consulte [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md).  
  
## <a name="browsing-metadata"></a>Examinar los metadatos  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los clientes de adaptador examinar las tablas de base de datos, vistas de tablas, procedimientos almacenados, funciones y paquetes que están disponibles en la base de datos de Oracle. Como parte de la operación de exploración de metadatos, el adaptador también expone las operaciones que se pueden realizar en la base de datos de Oracle, incluidas algunas operaciones personalizadas compatibles con los adaptadores. Estas operaciones están disponibles en la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone las operaciones siguientes:  
  
 **Operaciones de salida**  
  
 Contiene una lista de esquemas en la base de datos de Oracle subyacente. Expanda un nodo de esquema para ver los siguientes artefactos:  
  
-   **Tabla**: una lista de todas las tablas en el esquema. Seleccione una tabla para ver el Insert, Select, Update y las operaciones de eliminación.  
  
-   **Procedimiento**: una lista de procedimientos almacenados en el esquema que se exponen como operaciones.  
  
-   **Función**: una lista de funciones en el esquema que se exponen como operaciones.  
  
-   **Paquete**: una lista de todos los paquetes en el esquema. Seleccione un paquete para ver los procedimientos y funciones dentro del paquete que se exponen como operaciones.  
  
-   **Vista**: una lista de todas las vistas en el esquema. Seleccione una vista para ver el Insert, Select, Update y las operaciones de eliminación.  
  
 Aparte de esto, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] también expone la **SQLEXECUTE** operación saliente, lo que permite a los clientes de adaptador ejecutar cualquier lenguaje de manipulación de datos genéricos (DML) o un procedimiento almacenado en una base de datos de Oracle. La operación SQLEXECUTE está disponible cuando se selecciona el nodo raíz (/). Tenga en cuenta que el resultado de SQLEXECUTE es una matriz de los lectores de datos (el resultado como matriz de registros genéricos). Como resultado, cualquier simple los parámetros out no se exponen mediante la operación SQLEXECUTE. Para obtener más información sobre la operación, vea [operación SQLEXECUTE en base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md).  
  
 **Operaciones de entrada**  
  
 Contiene una lista de esquemas en la base de datos de Oracle subyacente. Expanda un nodo de esquema para ver los siguientes artefactos:  
  
-   **Procedimiento**: una lista de procedimientos almacenados en el esquema que se exponen como operaciones de sondeo.  
  
-   **Función**: una lista de funciones en el esquema que se exponen como operaciones de sondeo.  
  
-   **Paquete**: una lista de paquetes en el esquema. Seleccione un paquete para ver los procedimientos empaquetados y funciones que se exponen como operaciones de sondeo.  
  
 Aparte de esto, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] también expone la **POLLINGSTMT** y **notificación** operaciones entrantes. La operación de POLLINGSTMT permite a los clientes de adaptador obtener datos de entrada de la base de datos de Oracle en función de una consulta de sondeo mecanismo compatible con el adaptador. La operación de notificación permite a los clientes de adaptador registrar una instrucción SELECT como las notificaciones de consulta en la base de datos y la base de datos envía una notificación al cliente de adaptador como y cuando el conjunto de resultados de los cambios de la instrucción SELECT. Las operaciones de POLLINGSTMT y notificación están disponibles cuando se selecciona el nodo raíz (/). Para obtener más información acerca de las operaciones, vea [compatibilidad para mensajes de cambio de datos basados en la recepción de sondeo](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)MD) y [consideraciones para la recepción de base de datos el cargador de notificaciones mediante el adaptador de la base de datos de Oracle ](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).  
  
 Para obtener más información acerca de cómo se clasifica por categorías de los metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).  
  
## <a name="searching-metadata"></a>Buscar metadatos  
 Con la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], es posible realizar una consulta de búsqueda en la base de datos de Oracle mediante el uso de las expresiones de búsqueda de Oracle que sean compatibles con el operador LIKE. Por ejemplo, los clientes de adaptador pueden usar una expresión de búsqueda como "EMP %" para obtener tablas que empiezan con EMP. El adaptador lo convierte en la siguiente consulta SQL:  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 WHERE, SCOTT es el esquema con una colección de artefactos de base de datos de Oracle.  
  
 En la tabla siguiente se enumera los caracteres especiales que se pueden usar para buscar y su interpretación por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|_ (carácter de subrayado)|Coincide exactamente con un carácter<br /><br /> Por ejemplo, coincide con A_ AB, CA, AD.|  
|% (porcentaje)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un % coincide con A, AB ABC.|  
|\ (escape)|Convierte el significado especial de % y _<br /><br /> Por ejemplo, un\\_B coincide con A_B.|  
  
> [!IMPORTANT]
>  El ámbito de búsqueda de metadatos está restringido al nivel inmediatamente debajo del nodo en el que se realiza la operación de búsqueda. Por ejemplo, para buscar una función, que debe ser buscando en \\\Functions [esquema]. No se admite una búsqueda recursiva.  
  
## <a name="retrieving-metadata"></a>Recuperar metadatos  
 Al recuperar los metadatos, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] puede extraer metadatos en un esquema, incluidos todos o un subconjunto de la base de datos de objetos con los parámetros de objeto y la operación correspondientes. El adaptador presenta las entidades de la base de datos de Oracle como nombres de elementos en XML. Como caracteres de subrayado son los caracteres especiales permitidos únicamente que se pueden incluidos, todos los demás caracteres especiales en los nombres de elemento se codifican con caracteres de subrayado. Por ejemplo, `emp$name` se codifica como `emp_x0024_name`.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)   
 [Comprender el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)   
[Obtener los metadatos de las operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)