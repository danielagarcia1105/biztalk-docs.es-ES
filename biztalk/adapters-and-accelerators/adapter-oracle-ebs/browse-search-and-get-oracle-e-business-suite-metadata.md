---
title: Explorar, buscar y obtener metadatos de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b516c6e9-dbb3-4977-bb27-aa039e021912
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ce665ef71cbf0849caab334cf62c5f7a659ea96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218300"
---
# <a name="browse-search-and-get-oracle-e-business-suite-metadata"></a>Explorar, buscar y obtener metadatos de Oracle E-Business Suite
Los metadatos que [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] superficies de Oracle E-Business Suite y la base de datos de Oracle subyacente se describe la estructura del mensaje para la comunicación con Oracle E-Business Suite mediante el adaptador. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con dos interfaces para recuperar los metadatos.  
  
-   MetadataExchange proporcionada por [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. WCF proporciona un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes obtener metadatos de Oracle E-Business Suite.  
  
-   IMetadataRetrievalContract proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], que es compatible con los metadatos de exploración y búsqueda capacidades del adaptador.  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] superficies de Oracle E-Business Suite y los artefactos de base de datos subyacente y operaciones respectivas que pueden invocar los clientes de adaptador. Estas operaciones se describen más adelante en este tema.  
  
 Puede usar a los clientes de adaptador para examinar, buscar y recuperar los metadatos por:  
  
-   Crear un proyecto de BizTalk en Visual Studio  
  
-   Mediante el modelo de canal WCF  
  
-   Mediante el modelo de servicio WCF  
  
 Al utilizar un proyecto de BizTalk, debe utilizar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar metadatos para las operaciones que desea realizar en Oracle E-Business Suite. Al utilizar el modelo de servicio WCF, debe utilizar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar las clases de proxy para realizar operaciones en Oracle E-Business Suite. Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [obtener metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).  
  
## <a name="browsing-metadata"></a>Examinar los metadatos  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes de adaptador Examinar tablas de interfaz, vistas de interfaz, programas simultáneos y solicitar conjuntos en Oracle E-Business Suite y tablas, vistas, procedimientos almacenados, funciones y paquetes en la base de datos subyacente. Como parte de la operación de exploración de metadatos, el adaptador también expone las operaciones que se pueden realizar en la base de datos de Oracle, incluidas algunas operaciones personalizadas compatibles con los adaptadores. Estas operaciones están disponibles en [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] presenta la mayoría de las operaciones en los siguientes tres nodos:  
  
1.  **Vista basada en la aplicación**: contiene las operaciones que se agrupan por cada aplicación para los artefactos de Oracle E-Business Suite.  
  
2.  **Vista basada en el artefacto**: contiene las operaciones que se agrupan por tipo de artefacto (por ejemplo, tablas de interfaz, vistas de interfaz etc.) de Oracle E-Business Suite y la base de datos subyacente.  
  
3.  **Vista de esquema**: contiene las operaciones que se agrupan por cada esquema para los artefactos de base de datos subyacente.  
  
 Hay algunas operaciones genéricos expuestos en el nivel raíz que son aplicables para ambos nodos. Además, aparecen según el tipo de operación diferentes operaciones: saliente o entrante.  
  
 En la tabla siguiente se enumera las operaciones de entrada y salidas obtenidas por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
|Operaciones de salida|Operaciones de entrada|  
|-------------------------|------------------------|  
|**Vista basada en la aplicación**:<br /><br /> Contiene una lista de aplicaciones de Oracle en Oracle E-Business Suite subyacente. Expanda un nodo de aplicación de Oracle para ver los siguientes artefactos:<br /><br /> <ul><li>**Tablas de la interfaz**: una lista de todas las tablas de interfaz. Seleccione una tabla de la interfaz para ver el Insert, Select, Update y las operaciones de eliminación.</li><li>**Vistas de la interfaz**: una lista de todas las vistas de interfaz. Seleccione una interfaz para ver la operación de selección.</li><li>**Programas simultáneos**: las siguientes operaciones para los programas simultáneos:<br /><br /> <ul><li>Un conjunto de todos los simultáneos programas específicos de la aplicación de Oracle que se exponen como operaciones.</li><li>La operación de Get_Status para obtener el estado de un programa simultáneo.</li><li>La operación de Wait_For_Request de espera para que una solicitud se complete antes de devolver el estado.</li><li>La operación Submit_Request llamar o ejecutar un programa simultáneo mediante la especificación de los parámetros necesarios para la ejecución del programa simultáneo.</li></ul></li><li>**Solicitar conjuntos**: un conjunto de todas la solicitud establece específico de la aplicación de Oracle que se exponen como operaciones.</li></ul>|**Vista basada en la aplicación**:<br /><br /> Contiene una lista de aplicaciones de Oracle en Oracle E-Business Suite subyacente. Expanda un nodo de aplicación de Oracle para ver los siguientes artefactos:<br /><br /> -   **Tablas de la interfaz**: operación el sondeo para las tablas de interfaz que permite a los clientes de adaptador obtener datos de entrada de Oracle E-Business Suite se basa en un mecanismo de sondeo de consulta admitido por el adaptador.<br />-   **Vistas de la interfaz**: operación el sondeo para las vistas de interfaz que permite a los clientes de adaptador obtener datos de entrada de Oracle E-Business Suite se basa en un mecanismo de sondeo de consulta admitido por el adaptador.|  
|**Vista basada en el artefacto**:<br /><br /> Contiene todos los artefactos de Oracle E-Business Suite y la base de datos subyacente. Expanda un nodo de artefacto para ver una lista de las aplicaciones de Oracle o esquemas según el origen del artefacto (aplicaciones o base de datos). Por ejemplo, el **tablas de interfaz** nodo mostrará una lista de aplicaciones de Oracle, mientras que la **tablas** nodo mostrará una lista de esquemas de base de datos.<br /><br /> El **vista basada en el artefacto** muestra los artefactos que aparecen en **vista basada en aplicaciones** y **vista basada en el esquema**. Cada nodo de artefacto muestra las operaciones pertinentes para una aplicación de Oracle o un esquema de base de datos.|**Vista basada en el artefacto**:<br /><br /> Excepto programas simultáneos y conjuntos de solicitudes, contiene todos los artefactos de Oracle E-Business Suite y todos los artefactos de la base de datos subyacente. Expanda un nodo de artefacto para ver una lista de las aplicaciones de Oracle o esquemas según el origen del artefacto (aplicaciones o base de datos). Por ejemplo, el **tablas de interfaz** nodo mostrará una lista de aplicaciones de Oracle, mientras que la **tablas** nodo mostrará una lista de esquemas de base de datos.<br /><br /> El **vista basada en el artefacto** muestra los artefactos que aparecen en **vista basada en aplicaciones** y **vista basada en el esquema**. Cada nodo de artefacto muestra las operaciones pertinentes para una aplicación de Oracle o un esquema de base de datos.|  
|**Vista de esquema**:<br /><br /> Contiene una lista de esquemas en la base de datos de Oracle subyacente. Expanda el nodo de esquema para ver los siguientes artefactos:<br /><br /> -   **Las API de PL/SQL**: una lista de todas las API de PL/SQL. Seleccione una API de PL/SQL para ver los procedimientos empaquetados y funciones que se exponen como operaciones.<br />-   **Procedimientos**: una lista de procedimientos en el esquema que se exponen como operaciones.<br />-   **Funciones**: una lista de funciones en el esquema que se exponen como operaciones.<br />-   **Tablas**: una lista de todas las tablas. Seleccione una tabla para ver el Insert, Select, Update y las operaciones de eliminación.<br />-   **Vistas**: una lista de todas las vistas. Seleccione una vista para ver la operación de selección.|**Vista de esquema**:<br /><br /> Contiene una lista de esquemas en la base de datos de Oracle subyacente. Expanda el nodo de esquema para ver los siguientes artefactos:<br /><br /> -   **Las API de PL/SQL**: una lista de todas las API de PL/SQL. Seleccione una API de PL/SQL para ver los procedimientos empaquetados y funciones que se exponen como operaciones de sondeo.<br />-   **Procedimientos**: una lista de procedimientos en el esquema que se exponen como operaciones de sondeo.<br />-   **Funciones**: una lista de funciones en el esquema que se exponen como operaciones de sondeo.<br />-   **Tablas**: una lista de todas las tablas. Seleccione una tabla para ver el funcionamiento de sondeo de la tabla.<br />-   **Vistas**: una lista de todas las vistas. Seleccione una vista para ver el funcionamiento de sondeo de la vista.|  
|El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] también expone las siguientes operaciones de salida genéricas en el nivel raíz: ExecuteReader, ExecuteScalar y ExecuteNonQuery. Para obtener información acerca de estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).|El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] también expone la operación de notificación en el nivel de raíz que permite a los clientes de adaptador recibir mensajes de notificación de cambio de base de datos de Oracle E-Business Suite. Para obtener más información sobre la operación de notificación, consulte [consideraciones para recibir notificaciones de cambio de base de datos](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).|  
  
 Para obtener más información acerca de cómo se clasifica por categorías de los metadatos, vea [exploración, búsqueda y recuperar metadatos para las operaciones de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
## <a name="searching-metadata"></a>Buscar metadatos  
 Mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], puede realizar una consulta de búsqueda en Oracle E-Business Suite y en la base de datos de Oracle subyacente utilizando el Oracle buscar expresiones que son compatibles con el operador LIKE. Por ejemplo, los clientes de adaptador pueden usar una expresión de búsqueda como "EMP %" para obtener tablas que empiezan con EMP. El adaptador lo convierte en la siguiente consulta SQL:  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 WHERE, SCOTT es el esquema con una colección de artefactos de base de datos de Oracle.  
  
 En la tabla siguiente se enumera los caracteres especiales que se pueden usar para buscar y su interpretación por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|_ (carácter de subrayado)|Coincide exactamente con un carácter<br /><br /> Por ejemplo, A_ encuentra AB, CA y AD.|  
|% (porcentaje)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un % coincide con A, AB ABC.|  
|\ (escape)|Convierte el significado especial de % y _. El \ (escape) caracteres se utilizan antes de un carácter comodín para indicar que el carácter comodín debe interpretarse como un carácter normal.<br /><br /> Por ejemplo, un\\_B coincide con A_B.|  
  
> [!IMPORTANT]
>  -   La cadena de búsqueda distingue mayúsculas de minúsculas.  
> -   La búsqueda funciona de manera diferente en la vista diferentes (vista basada en la aplicación, vista basada en el artefacto y vista basada en el esquema). Para saber cómo puede buscar artefactos y las operaciones en cada vista, vea "Buscar en distintas vistas" en [búsqueda para las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md).  
> -   Para buscar una aplicación puede especificar el nombre descriptivo o el nombre corto de la aplicación. Por ejemplo, para buscar el **cuentas por cobrar** aplicación puede especificar la cadena de búsqueda como **recepción %** o **AR**. AR es el nombre corto de aplicación.  
> -   Para buscar un programa simultáneo puede especificar el nombre descriptivo o el nombre real del programa simultáneo. Por ejemplo, para buscar el **interfaz cliente** programa simultáneo puede especificar la cadena de búsqueda como **interfaz de cliente %** o **RACUST %**. RACUST es el nombre real del programa simultáneo. Además, el resultado de la búsqueda siempre contendrá los programas simultáneos estándares independientemente de si su nombre coincide con la cadena de búsqueda especificado.  
  
## <a name="retrieving-metadata"></a>Recuperación de metadatos  
 Al recuperar los metadatos, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] puede extraer metadatos en un esquema, incluidos todos o un subconjunto de la base de datos de objetos con los parámetros de objeto y la operación correspondientes. El adaptador presenta las entidades de Oracle E-Business Suite y la base de datos de Oracle subyacente como nombres de elementos en XML. Como caracteres de subrayado son los caracteres especiales permitidos únicamente que se pueden incluidos, todos los demás caracteres especiales en los nombres de elemento se codifican con caracteres de subrayado. Por ejemplo, `emp$name` se codifica como `emp_x0024_name`. Para obtener más información, consulte [obtener metadatos para las operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)   
 [Buscar, búsqueda y recuperar metadatos para las operaciones de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)   
 [Obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)