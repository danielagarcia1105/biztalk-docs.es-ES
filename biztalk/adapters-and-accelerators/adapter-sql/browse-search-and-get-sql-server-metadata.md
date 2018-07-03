---
title: Examinar, buscar y obtener metadatos de SQL Server | Microsoft Docs
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
ms.openlocfilehash: 37308bf4f5a1d6bedba061337b2352f198354dd7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994157"
---
# <a name="browse-search-and-get-sql-server-metadata"></a>Examinar, buscar y obtener metadatos de SQL Server
Los metadatos que [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] superficies de la base de datos de SQL Server se describe la estructura del mensaje para la comunicación con la base de datos de SQL Server mediante el adaptador. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es compatible con dos interfaces para recuperar los metadatos.  
  
- MetadataExchange proporcionada por [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. WCF ofrece un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes a obtener los metadatos de la base de datos de SQL Server.  
  
- IMetadataRetrievalContract proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], que es compatible con los metadatos de examinar y buscar las capacidades del adaptador.  
  
  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] artefactos y operaciones respectivas que pueden invocar los clientes del adaptador de base de datos las superficies de SQL Server. El adaptador también expone las operaciones (como ExecuteNonQuery, ExecuteReader y ExecuteScalar) que se pueden usar para realizar operaciones concretas en la base de datos de SQL Server. Estas operaciones se describen más adelante en este tema.  
  
> [!NOTE]
>  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] superficies de artefactos en todos los esquemas en la base de datos de SQL Server que el usuario conectado actualmente tiene acceso. Esto implica que el esquema predeterminado (dbo), además de los clientes del adaptador también pueden realizar operaciones en artefactos en otros esquemas en la base de datos de SQL Server siempre que las credenciales de usuario utilizan para conectarse mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] tiene acceso a esos esquemas en la base de datos de SQL Server. Para obtener información acerca de un esquema de base de datos de SQL Server, vea [ http://go.microsoft.com/fwlink/?LinkId=130148 ](http://go.microsoft.com/fwlink/?LinkId=130148).  
  
 Puede usar a los clientes del adaptador para examinar, buscar y recuperar metadatos mediante:  
  
- Crear un proyecto de BizTalk en Visual Studio  
  
- Mediante el modelo de servicio WCF  
  
- Mediante el modelo de canal WCF  
  
  Cuando se usa un proyecto de BizTalk, debe usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar metadatos para las operaciones que desea realizar en la base de datos de SQL Server. Cuando se usa el modelo de servicio WCF, debe usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar las clases de proxy para realizar operaciones en la base de datos de SQL Server. Para obtener más información acerca de la exploración, búsqueda y recuperación de metadatos mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [obtener metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="browsing-metadata"></a>Examinar los metadatos  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes del adaptador examinar las tablas de base de datos, vistas, procedimientos almacenados y funciones que están disponibles en la base de datos de SQL Server. Como parte de la operación de exploración de metadatos, el adaptador también expone las operaciones que se pueden realizar en la base de datos de SQL Server, incluidas algunas operaciones personalizadas compatibles con los adaptadores. Estas operaciones están disponibles en [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] presenta las siguientes operaciones:  
  
- Las operaciones en tablas, vistas, procedimientos, funciones escalares y funciones con valores de tabla. Por ejemplo, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] posible superficie Insert, Update, Select y operaciones de eliminación para la tabla EMPLOYEE.  
  
- El conjunto\<nombre de columna\> operación para las tablas y vistas que permite a los clientes del adaptador escribir los valores de datos de gran tamaño en un modo de transmisión por secuencias. Solo se devuelve la operación de establecimiento de las tablas y vistas que contienen columnas con cualquiera de los siguientes tipos de datos: varchar (max), nvarchar (max) o varbinary (max). Para obtener más información, consulte [operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md).  
  
- Las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar que permiten a los clientes del adaptador ejecutar instrucciones SQL arbitrarias en SQL Server. Para obtener más información acerca de estas operaciones, consulte [compatibilidad con ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
- Las operaciones de sondeo y la notificación para recibir los mensajes de entrada de SQL Server. Para obtener información acerca de la operación de sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md); para obtener información acerca de la operación de notificación, consulte [consideraciones para recibir notificaciones de consulta mediante la instrucción SQL adaptador](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md).  
  
  Para obtener más información acerca de cómo se clasifica por categorías los metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).  
  
## <a name="searching-metadata"></a>Buscar metadatos  
 Con la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], es posible realizar una consulta de búsqueda en la base de datos de SQL Server mediante el uso de las expresiones de búsqueda de SQL Server que son compatibles con el operador LIKE. Por ejemplo, los clientes del adaptador pueden usar una expresión de búsqueda como "EMP %" para obtener las tablas que empiezan con EMP. El adaptador lo convierte en la siguiente consulta SQL:  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%'  
```  
  
 La tabla siguiente enumeran los caracteres especiales que se pueden usar para la búsqueda y su interpretación por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|_ (carácter de subrayado)|Coincide exactamente con un carácter.<br /><br /> Por ejemplo, "A_" coincide con "AB", "CA", "AD".|  
|% (porcentaje)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, "%" coincide con "A", "AB", "ABC".|  
|[ ]|-El significado especial de _ y % de secuencias de escape.<br />-Especifica un intervalo o conjunto de caracteres que se va a estar presente.<br /><br /> Por ejemplo:<br /><br /> -% [%] coincide con todos los nombres que incluyen un símbolo %.<br />-[a-f] coincide con todos los nombres que tienen caracteres entre la 'a' y 'f'.<br />-[abc] coincide con todos los nombres que tienen caracteres 'a', 'b' y 'c'.|  
|[^]|Especifica un intervalo o conjunto de caracteres que no se esté presente.<br /><br /> Por ejemplo:<br /><br /> -[^ a-f] coincide con todos los nombres que no tienen caracteres entre la 'a' y 'f'.<br />-[^ abc] coincide con todos los nombres que no tienen caracteres 'a', 'b' y 'c'.|  
  
> [!IMPORTANT]
>  El ámbito de búsqueda de metadatos está restringido al nivel inmediatamente debajo del nodo en el que se realiza la operación de búsqueda. Por ejemplo, para buscar una función escalar, debe ser escalar o búsqueda en función / [esquema]. No se admite la búsqueda de varios nivel.  
  
## <a name="retrieving-metadata"></a>Recuperar metadatos  
 Al recuperar los metadatos, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede extraer metadatos en un esquema, incluidos todos o un subconjunto de la base de datos de objetos con los parámetros de objeto y la operación correspondientes. El adaptador presenta las entidades de la base de datos de SQL Server como nombres de elemento XML. Como caracteres de subrayado son los únicos caracteres especiales que se pueden incluidos, todos los demás caracteres especiales en los nombres de elemento se codifican con caracteres de subrayado. Por ejemplo, `emp$name` se codifica como `emp_x0024_name`.  
  
## <a name="see-also"></a>Vea también  
 [Información general del adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [Comprender el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)   
 [Obtener metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)