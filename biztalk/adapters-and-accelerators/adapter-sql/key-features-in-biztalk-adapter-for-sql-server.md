---
title: La clave de características en el adaptador de BizTalk para SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6beab8d-c2c4-4add-860c-054b9aed8d70
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af3177e3004c81d368eab8738a201e90c95d1b69
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967826"
---
# <a name="key-features-in-biztalk-adapter-for-sql-server"></a>Características clave en el adaptador de BizTalk para SQL Server
Esta sección enumeran las características de [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].  
  
> [!NOTE]
>  En este tema se ha utilizado desde la versión anterior de [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] ayuda.  
  
## <a name="features-in-the-sql-adapter"></a>Características en el adaptador de SQL  
 Siguientes son las características introducidas en las versiones anteriores de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
### <a name="technology-related-features"></a>Características relacionadas con la tecnología  
  
|Característica|Comentario|  
|-------------|-------------|  
|Uso de Windows Communication Foundation (WCF)|El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] ([!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]). A su vez, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se basa en WCF. El adaptador se expone como un canal WCF a los clientes de adaptador. Esto permite la conectividad, el intercambio de metadatos y el intercambio de datos de negocio con sistemas externos.|  
|Compatibilidad con el modelo de canal WCF y el modelo de servicio WCF|En el modelo de canal WCF, pueden consumir los clientes de adaptador el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] directamente enviando y recibiendo mensajes XML. En el modelo de servicio WCF, los clientes de adaptador pueden generar una clase de proxy de .NET desde el lenguaje de descripción de servicios de Web (WSDL) obtenido mediante el uso de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].|  
|Compatibilidad con plataformas de 64 bits|El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ahora está disponible para plataformas de 64 bits.|  
  
### <a name="metadata-related-features"></a>Características relacionadas con metadatos  
  
|Característica|Comentario|  
|-------------|-------------|  
|Examinar, buscar y recuperar metadatos|Los clientes de adaptador pueden examinar y buscar metadatos en lotes mediante la especificación de un tamaño de lote. Esta característica está disponible sólo cuando la programación en el adaptador y no mediante el complemento de consumir un proyecto de BizTalk de servicio de adaptador. Se admite la búsqueda de metadatos en los niveles de tablas, vistas, procedimientos, funciones escalares y funciones con valores de tabla. La cadena de búsqueda se utiliza directamente dentro de una instrucción SQL.|  
|Soporte técnico para invocar los artefactos con el mismo nombre en diferentes bases de datos|En el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], los espacios de nombres en el archivo de definición de esquemas XML (XSD) que contiene solo el esquema de nombre y en algunos casos, el nombre del objeto. Sin embargo, si una aplicación desea ejecutar operaciones en los artefactos con el mismo nombre con metadatos diferentes en distintas bases de datos, los metadatos generados estará en conflicto. La única manera de distinguir los metadatos es utilizar el nombre de la base de datos en los espacios de nombres XSD.<br /><br /> La versión actual de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] le permite especificar el nombre de la base de datos en los espacios de nombres XSD estableciendo el valor de la **UseDatabaseNameInXsdNamespace** enlaza la propiedad en TRUE. El valor predeterminado de la propiedad de enlace es false, lo cual implica que los espacios de nombres XSD no contendrá el nombre de base de datos. Para obtener más información sobre la **UseDatabaseNameInXsdNamespace** enlace de propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).|  
  
### <a name="performance-related-features"></a>Características relacionadas con el rendimiento  
  
|Característica|Comentario|  
|-------------|-------------|  
|Compatibilidad con contadores de rendimiento|El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es compatible con los contadores de rendimiento basados en WCF para los clientes de adaptador. Para obtener más información sobre los contadores de rendimiento, consulte [utilizar contadores de rendimiento con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md).|  
  
### <a name="operations-related-features"></a>Características relacionadas con las operaciones  
  
|Característica|Comentario|  
|-------------|-------------|  
|Compatibilidad con los tipos de datos de SQL Server 2005 y SQL Server 2008|El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite los siguientes tipos de datos que se introdujo en:<br /><br /> -   **SQL Server 2005**: XML, varchar (max) y varbinary (max).<br />-   **SQL Server 2008**: fecha, hora, Datetimeoffset, Datetime2, Hierarchyid, Geography, Geometry y FILESTREAM.|  
|Compatibilidad con tipos definidos por el usuario (UDT)|El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la realización de operaciones en tablas y vistas que contienen UDT. Para obtener información sobre la compatibilidad con UDT, vea [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md).|  
|Soporte técnico para la ejecución de Transact-SQL y CLR procedimientos almacenados y funciones|Los clientes de adaptador pueden ejecutar Transact-SQL y CLR:<br /><br /> -Los procedimientos almacenados en una base de datos de SQL Server.<br />-Escalares y funciones con valores de tabla en una base de datos de SQL Server.<br /><br /> Para obtener más información sobre esto, consulte [qué operaciones puede realizar mediante el adaptador de?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx).|  
|Compatibilidad para ejecutar procedimientos almacenados con o sin la cláusula FOR XML|El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite ejecutar procedimientos almacenados que tienen una instrucción SELECT con o sin una cláusula FOR XML. La versión anterior del adaptador admite solo los procedimientos almacenados que tenían una cláusula FOR XML en la instrucción SELECT. Para obtener información acerca de cómo ejecutar los procedimientos almacenados, vea [ejecutar los procedimientos almacenados de SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-the-sql-adapter.md).|  
|Compatibilidad con el streaming de objetos grandes|Los clientes de adaptador pueden transmitir caracteres de gran tamaño y campos binarios en la base de datos de SQL Server con el conjunto de\<nombre de la columna\> operación, donde < column_name > es el nombre de la columna de tipo varchar (max), nvarchar (max) o varbinary (max) . El conjunto de\<nombre de la columna\> operación también le permite insertar o actualizar los datos FILESTREAM en una base de datos de SQL Server 2008. Para obtener más información sobre esto, consulte [operaciones en tablas y vistas que contienen tipos de datos grandes con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md). **Nota:** para leer caracteres y campos binarios en vistas y tablas de SQL Server, los clientes de adaptador utilizan la operación de selección.|  
|Compatibilidad con las notificaciones de consulta|Los clientes de adaptador pueden recibir las notificaciones de consulta de SQL Server en función de una instrucción SELECT desencadenador o un procedimiento almacenado. La notificación se envía por SQL Server a los clientes de adaptador como y cuando el conjunto de resultados de la instrucción SELECT o el procedimiento almacenado cambia. Para obtener más información acerca de las notificaciones de consulta, vea [recibir las notificaciones de consulta mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md).|  
|Compatibilidad para ejecutar instrucciones SQL arbitrarias|El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes de adaptador ejecutar instrucciones SQL arbitrarias mediante las operaciones ExecuteNonQuery y ExecuteReader, ExecuteScalar. Para obtener más información acerca de estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).|  
|Compatibilidad con operaciones compuestas|El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes de adaptador realizar operaciones compuestas en la base de datos de SQL Server. Una operación compuesta puede incluir cualquier número de las siguientes operaciones y en cualquier orden:<br /><br /> -Las operaciones Insert, Update y Delete en las tablas y vistas.<br />-Procedimientos que aparecen como operaciones en el adaptador.<br /><br /> Para obtener más información sobre operaciones compuestas, consulte [esquemas de mensaje para operaciones compuestas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).|  
|Sondeo mejorada|El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ahora admite dos tipos adicionales de sondeo: **TypedPolling** y **XmlPolling**. Para obtener información acerca de estos tipos de sondeos, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).|  
|Compatibilidad para realizar operaciones en artefactos en varios esquemas|Además del esquema predeterminado (dbo), los clientes de adaptador pueden realizar operaciones en artefactos en otros esquemas de la base de datos de SQL Server siempre que las credenciales de usuario se utilizan para conectar con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] tiene acceso a los esquemas de SQL Server base de datos. Para obtener información acerca de un esquema de base de datos de SQL Server, vea [http://go.microsoft.com/fwlink/?LinkId=130148](http://go.microsoft.com/fwlink/?LinkId=130148).|  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)