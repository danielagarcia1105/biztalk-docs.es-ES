---
title: "La clave de características en el adaptador de BizTalk para base de datos de Oracle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- features, operations-related
- adapters, new and deprecated features
- features, technology-related
- features, new and deprecated
- features, performance-related
- features, metadata-related
ms.assetid: 7e79714c-1472-4721-a693-5be2a9a0cd1f
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4277c5d0691d44bdae26b6b395a91d2ecb8f093
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-biztalk-adapter-for-oracle-database"></a>Características clave en el adaptador de BizTalk para base de datos de Oracle
Esta sección enumeran las características nuevas y en desuso en [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].  

  
## <a name="technology-related-features"></a>Características relacionadas con la tecnología  
  
|Característica|Comentario|  
|-------------|-------------|  
|Nueva manera de conectarse a la base de datos de Oracle|Además de conectarse a la base de datos de Oracle utilizando el nombre de servicio de red en el archivo tnsnames.ora (como en la versión anterior del adaptador), el adaptador de clientes ahora también pueden conectarse a la base de datos de Oracle directamente mediante la especificación de los parámetros de conexión y, por tanto, lo que elimina la necesidad de usar un nombre de servicio de red o en el archivo tnsnames.ora. No se requiere el archivo tnsnames.ora para conectarse a la base de datos de Oracle evita las complicaciones de actualización manual de los parámetros de conexión (nombre de servicio de red) en el archivo tnsnames.ora en cada equipo cliente al agregar o actualizar los servidores de Oracle en el entorno. Para obtener más información, consulte [crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md).|  
|Compatibilidad con la autenticación de Windows|Los clientes de adaptador pueden usar la autenticación de Windows para conectarse a la base de datos de Oracle. Autenticación de Windows le permite determinar la identidad del usuario en función de las credenciales de inicio de sesión de Windows y, por tanto, le ayuda a aprovechar la seguridad integrada del entorno de Windows. Para obtener más información acerca de la autenticación de Windows en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [conectar con la autenticación de Windows de base de datos de Oracle utilizando](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md).|  
  
## <a name="operations-related-features"></a>Características relacionadas con las operaciones 
  
|Característica|Comentario|  
|-------------|-------------|  
|Soporte para especificar valores en línea en la operación de inserción|Puede usar el **InlineValue** atributo en la operación de inserción para insertar valores calculados en tablas o vistas en la base de datos de Oracle. Esto es un atributo opcional y está disponible para todos los registros de datos simple en una operación de insertar varios registro. Si especifica un valor para este atributo, invalida el valor especificado de un registro. Para obtener más información sobre el atributo InlineValue, consulte [Insert, Update, Delete y las operaciones de Select en las tablas de Oracle y vistas](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md).|  
|Sondeo mejorada|El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ahora admite la recepción de mensajes de cambio de datos "basada en sondeo" mediante el uso de funciones o procedimientos almacenados, funciones o procedimientos empaquetados que éstos sondeen periódicamente la base de datos de Oracle. Además de la instrucción SELECT, ahora se puede especificar un procedimiento almacenado, función o procedimiento empaquetada o la función como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear la base de datos de Oracle. Para obtener más información acerca del sondeo, consulte [compatibilidad para mensajes de cambio de datos basados en la recepción de sondeo](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md).|  
|Compatibilidad con tipos definidos por el usuario de Oracle (UDT)|El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la realización de operaciones en artefactos en la base de datos de Oracle que contienen UDT de Oracle. Para obtener información sobre la compatibilidad con UDT, vea [admiten tipos de Oracle User-Defined de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md).|  
|Compatibilidad con operaciones compuestas|El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los clientes de adaptador realizar operaciones compuestas en la base de datos de Oracle. Una operación compuesta puede incluir cualquier número de las siguientes operaciones y en cualquier orden:<br /><br /> -Operaciones en tablas y vistas.<br />-Procedimientos, funciones y procedimientos almacenados o funciones de los paquetes que aparecen como operaciones en el adaptador.<br /><br /> Para obtener más información sobre operaciones compuestas, consulte [esquema de mensajes para operaciones compuestas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).|  
|Compatibilidad para ejecutar procedimientos almacenados en los esquemas que no pertenecen al usuario|El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite ejecutar procedimientos almacenados en un esquema, incluso si el usuario actual no es el propietario del esquema, siempre que el usuario tiene permisos en el esquema de Oracle. Sin embargo, si el procedimiento almacenado utiliza tipos de registros, se debe definir en el mismo esquema que el procedimiento almacenado. Para obtener información acerca de cómo ejecutar procedimientos almacenados mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [operaciones en funciones y procedimientos almacenados](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md).|  
|Compatibilidad con las notificaciones de cambio de base de datos|Los clientes de adaptador pueden recibir notificaciones de cambio de base de datos de base de datos de Oracle en función de una instrucción SELECT desencadenadora. La notificación se envía por base de datos de Oracle a los clientes de adaptador como y cuando el conjunto de resultados para que los cambios de la instrucción SELECT. Para obtener más información acerca de las notificaciones de cambio de base de datos, vea [consideraciones para recibir notificaciones de cambiar de base de datos](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).|  
|Compatibilidad con sinónimos|Los clientes de adaptador pueden realizar operaciones en sinónimos creados para tablas, vistas, procedimientos almacenados, funciones y paquetes. Para obtener información acerca de sinónimos, y cómo se puede utilizar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para llevar a cabo operaciones en sinónimos, vea [operaciones en sinónimos en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md).|  
|Compatibilidad con tipos de tabla de PL/SQL y parámetros booleanos|Los clientes de adaptador pueden realizar operaciones en los procedimientos almacenados y funciones que contienen parámetros booleanos y el tipo de tabla de PL/SQL.|  
  
### <a name="other-features"></a>Otras características  
  
|Característica|Comentario|  
|-------------|-------------|  
|Nueva forma de utilizar el adaptador de BizTalk Server|La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF-OracleDB en BizTalk. Si desea utilizar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a través de un puerto personalizado de WCF, no es necesario agregar el puerto WCF-Custom en la consola de administración de BizTalk Server porque el puerto WCF personalizado se agrega a la consola de administración de BizTalk Server de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a través de un puerto de WCF-OracleDB, primero debe agregar el adaptador de WCF-OracleDB a la consola de administración de BizTalk Server. Para obtener más información, consulte [agregar el adaptador de la base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).|  
  
## <a name="deprecated-features-in-the-oracle-adapter"></a>Características en desuso en el adaptador de Oracle  
 En la tabla siguiente se enumera las características que están en desuso en la versión actual de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
|Característica|Comentario|  
|-------------|-------------|  
|Propiedades de enlace|El **PollingRetryCount**, **TransactionIsolationLevel**, y **LongDataTypeColumnSize** propiedades de enlace están en desuso. <br/><br/>**Tenga en cuenta** para establecer el nivel de aislamiento de transacción para las operaciones de entrada, debe establecer el valor adecuado agregando el comportamiento del servicio al configurar el puerto de recepción. Para obtener instrucciones sobre cómo establecer el nivel de aislamiento de transacción, vea [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).|  
  
## <a name="changes-to-note"></a>Cambios en la nota

### <a name="general"></a>General  
* Para los parámetros de tipo IN OUT REF CURSOR

    -   Si se ha producido ningún cambio en el valor de REF CURSOR dentro del procedimiento almacenado, el valor del resultado es el mismo que el valor de la entrada REF CURSOR.  
  
    -   Los datos de entrada y salidos de REF CURSOR son del mismo tipo.  
  
-   Un comportamiento incorrecto del atributo "nil": para todos los tipos de datos simples, si establece el valor del atributo nil en "true" y un valor para el campo o parámetro está presente, a continuación, el adaptador de la base de datos de Oracle incorrectamente pasa el valor especificado en lugar de NULL. Como alternativa, si desea pasar el valor NULL para un campo o parámetro, debe asegurarse de que se especifica ningún valor para el campo o parámetro. Por ejemplo, para pasar el valor NULL para un campo denominado "name":  
  
    ```  
    <name xsi:nil="true"/>  
    ```  
-   No se truncan Real, Float y tipos de datos largos y adicionales ceros (0) al final del valor en el conjunto de resultados de la operación seleccionada. Además, el conjunto de resultados de la operación seleccionada siempre devuelve un valor con una precisión de 8 para Real, Float y tipos de datos largos.  
  
-   Control de datos para los tipos de registro: el valor pasado para estos nodos dependen del valor de la **SkipNilNodes** propiedad de enlace. Para obtener más información acerca de esta propiedad de enlace, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md). 
  
-   Las operaciones de salida: no se envía ningún valor para los parámetros que no tienen un valor especificado en el archivo XML de entrada. Si se especifica un valor predeterminado en el procedimiento almacenado, la base de datos de Oracle utiliza ese valor porque el adaptador no se envía ningún valor. Si debe enviarse un valor NULL, el usuario debe especificar un nodo NULL del archivo de entrada XML estableciendo el valor del atributo "nil" en "true".  
  
-   Tiempo de espera de comando es compatible.  
  
-   La operación de UpdateLOB debe realizarse como parte de una transacción. Para asegurarse de esto, el valor de la **UseAmbientTransaction** enlaza la propiedad debe establecerse en **True**.  
  
### <a name="biztalk-scenario"></a>Escenario de BizTalk  
  
-   Las operaciones salientes: si la **UseAmbientTransaction** enlaza la propiedad es "True", las operaciones en la base de datos de Oracle y BizTalk MessageBox base de datos se realizan en la misma transacción distribuida. Para obtener más información acerca de las transacciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [controlar las transacciones con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md).  
  
-   Operaciones entrantes: no se puede usar una respuesta de solicitud de puerto de recepción [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para las operaciones de entrada mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Unidireccional solo recibe puertos se pueden utilizar.  
  
### <a name="other-scenarios"></a>Otros escenarios  
  
-   Las operaciones salientes: el adaptador no inicia una transacción. Si el usuario desea insertar en la misma transacción de varias filas, es responsabilidad del usuario para ejecutar la operación dentro de un ámbito de transacción System.Transactions. El usuario también debe establecer el valor de la **UseAmbientTransaction** propiedad **True**. Para obtener más información acerca de las transacciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [controlar las transacciones con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md).  
  
-   Las operaciones salientes: operaciones de Sll realizadas en el mismo objeto IRequestChannel/proxy no pueden realizarse en la misma conexión física a la base de datos de Oracle.  
  
-   Modelo del canal de WCF: La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite IReplyChannel al usar el modelo del canal de WCF. Sin embargo, puede usar IInputChannel para realizar operaciones de entrada. Además, con respecto a las transacciones, el adaptador se basa en la transacción de distribuidor WCF iniciar para ejecutar la instrucción de sondeo y exponer la instrucción de sondeo en la base de datos de Oracle. El nivel de aislamiento de transacción y el tiempo de espera de la transacción de distribuidor de WCF inicia pueden controlarse estableciendo los valores adecuados en el ServiceBehavior.  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de Biztalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)