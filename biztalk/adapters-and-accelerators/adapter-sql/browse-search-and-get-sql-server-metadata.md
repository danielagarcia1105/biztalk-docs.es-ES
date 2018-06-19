---
title: Explorar, buscar y obtener los metadatos de SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 368dd5ca-456c-4cae-9e85-bcf504c4e7ed
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba7a1b7644cc3a2e3e00b7a931250932359ab7b7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963946"
---
# <a name="browse-search-and-get-sql-server-metadata"></a>Explorar, buscar y obtener los metadatos de SQL Server
Los metadatos que [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] superficies de la base de datos de SQL Server se describe la estructura del mensaje para la comunicación con la base de datos de SQL Server mediante el adaptador. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es compatible con dos interfaces para recuperar los metadatos.  
  
-   MetadataExchange proporcionada por [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. WCF proporciona un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes obtener metadatos de la base de datos de SQL Server.  
  
-   IMetadataRetrievalContract proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], que es compatible con los metadatos de exploración y búsqueda capacidades del adaptador.  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] artefactos y operaciones respectivas que los clientes de adaptador pueden invocar la base de datos superficies de SQL Server. El adaptador también expone las operaciones (como ExecuteNonQuery, ExecuteReader y ExecuteScalar) que pueden utilizarse para realizar operaciones específicas en la base de datos de SQL Server. Estas operaciones se describen más adelante en este tema.  
  
> [!NOTE]
>  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] superficies de artefactos en todos los esquemas en la base de datos de SQL Server que tiene acceso para el usuario conectado actualmente. Esto implica que además el esquema predeterminado (dbo), los clientes de adaptador pueden también realizar operaciones en artefactos en otros esquemas de la base de datos de SQL Server siempre que las credenciales de usuario se utilizan para conectar con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] tiene acceso a los esquemas la base de datos de SQL Server. Para obtener información acerca de un esquema de base de datos de SQL Server, vea [http://go.microsoft.com/fwlink/?LinkId=130148](http://go.microsoft.com/fwlink/?LinkId=130148).  
  
 Puede usar a los clientes de adaptador para examinar, buscar y recuperar los metadatos por:  
  
-   Crear un proyecto de BizTalk en Visual Studio  
  
-   Mediante el modelo de servicio WCF  
  
-   Mediante el modelo de canal WCF  
  
 Al utilizar un proyecto de BizTalk, debe utilizar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar metadatos para las operaciones que desea realizar en la base de datos de SQL Server. Al utilizar el modelo de servicio WCF, debe utilizar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar las clases de proxy para realizar operaciones en la base de datos de SQL Server. Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [obtener los metadatos de las operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="browsing-metadata"></a>Examinar los metadatos  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes de adaptador examinar las tablas de base de datos, vistas, procedimientos almacenados y funciones que están disponibles en la base de datos de SQL Server. Como parte de la operación de exploración de metadatos, el adaptador también expone las operaciones que se pueden realizar en la base de datos de SQL Server, incluidas algunas operaciones personalizadas compatibles con los adaptadores. Estas operaciones están disponibles en [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. La [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone las operaciones siguientes:  
  
-   Las operaciones en tablas, vistas, procedimientos, funciones escalares y funciones con valores de tabla. Por ejemplo, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede expuesta Insert, Update, Select y eliminar operaciones para la tabla EMPLOYEE.  
  
-   El conjunto de\<nombre de la columna\> operación para tablas y vistas que permite a los clientes de adaptador escribir valores de datos grandes en un modo de transmisión por secuencias. La operación de configuración solo se devuelve para las tablas y vistas que contienen columnas con ninguno de los siguientes tipos de datos: varchar (max), nvarchar (max) o varbinary (max). Para obtener más información, consulte [operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md).  
  
-   Las operaciones ExecuteNonQuery y ExecuteReader, ExecuteScalar que permiten a los clientes de adaptador ejecutar instrucciones SQL arbitrarias en SQL Server. Para obtener más información acerca de estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
-   Las operaciones de sondeo y la notificación para recibir mensajes de entrada de SQL Server. Para obtener información sobre la operación de sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md); para obtener información sobre la operación de notificación, consulte [consideraciones para recibir las notificaciones de consulta mediante la instrucción SQL adaptador](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md).  
  
 Para obtener más información acerca de cómo se clasifica por categorías de los metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).  
  
## <a name="searching-metadata"></a>Buscar metadatos  
 Con la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], es posible realizar una consulta de búsqueda en la base de datos de SQL Server mediante las expresiones de búsqueda de SQL Server que son compatibles con el operador LIKE. Por ejemplo, los clientes de adaptador pueden usar una expresión de búsqueda como "EMP %" para obtener tablas que empiezan con EMP. El adaptador lo convierte en la siguiente consulta SQL:  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%'  
```  
  
 En la tabla siguiente se enumera los caracteres especiales que se pueden usar para buscar y su interpretación por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|_ (carácter de subrayado)|Coincide exactamente con un carácter.<br /><br /> Por ejemplo, "A_" coincide con "AB", "AC", "AD".|  
|% (porcentaje)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, "%" coincide con "A", "AB", "ABC".|  
|[ ]|-Antepone el significado especial de _ y %.<br />-Especifica un intervalo o un conjunto de caracteres que se va a estar presente.<br /><br /> Por ejemplo:<br /><br /> -% [%] coincide con todos los nombres que incluyen un símbolo %.<br />-[a-f] coincide con todos los nombres que tienen caracteres entre la 'a' y 'f'.<br />-[abc] coincide con todos los nombres que tienen caracteres 'a', 'b' y 'c'.|  
|[^]|Especifica un intervalo o un conjunto de caracteres que no se esté presente.<br /><br /> Por ejemplo:<br /><br /> -[^ a-f] coincide con todos los nombres que no tienen caracteres entre la 'a' y 'f'.<br />-[^ abc] coincide con todos los nombres que no tienen caracteres 'a', 'b' y 'c'.|  
  
> [!IMPORTANT]
>  El ámbito de búsqueda de metadatos está restringido al nivel inmediatamente debajo del nodo en el que se realiza la operación de búsqueda. Por ejemplo, para buscar una función escalar, debe ser función de búsqueda en/escalar / [esquema]. No se admite la búsqueda de varios nivel.  
  
## <a name="retrieving-metadata"></a>Recuperar metadatos  
 Al recuperar los metadatos, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede extraer metadatos en un esquema, incluidos todos o un subconjunto de la base de datos de objetos con los parámetros de objeto y la operación correspondientes. El adaptador presenta las entidades de la base de datos de SQL Server como nombres de elementos en XML. Como caracteres de subrayado son los caracteres especiales permitidos únicamente que se pueden incluidos, todos los demás caracteres especiales en los nombres de elemento se codifican con caracteres de subrayado. Por ejemplo, `emp$name` se codifica como `emp_x0024_name`.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [Comprender el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)   
 [Obtiene los metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)