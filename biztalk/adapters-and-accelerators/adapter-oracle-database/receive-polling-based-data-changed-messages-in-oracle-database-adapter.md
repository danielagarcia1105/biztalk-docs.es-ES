---
title: Recibir mensajes de cambio de datos basados en sondeos en el adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- polling-base notification, support for
ms.assetid: 043afb88-701c-41d8-8b8e-84702bd0d984
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f8ee32a7907cc37daf4a6b6b7d3971a28cf1b94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968941"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-adapter"></a>Recibir mensajes de cambio de datos basados en sondeos en el adaptador de base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] admite la recepción de mensajes de cambio de datos basados en sondeos por sondeo en la base de datos de Oracle. El adaptador entrega los mensajes a la aplicación por:  

- Ejecutar una consulta SELECT de SQL para determinar si los datos están disponibles para el sondeo. Puede configurar el adaptador para ejecutar la consulta SELECT de SQL periódicamente o de forma continua.  

- Ejecutar una consulta SELECT de SQL en una tabla de Oracle o una vista o ejecutar procedimientos, funciones, o empaquetados procedimientos almacenados y funciones.  

- Ejecutar un bloque de código de PL/SQL posterior a la encuesta opcional en la base de datos de Oracle. Este bloque de código a menudo se usa para actualizar un campo en los registros consultados en el destino o para mover los registros consultados a otra tabla o vista.  

- Devolver los resultados de consulta en un resultado de establece mediante la invocación de la operación POLLINGSTMT o los procedimientos almacenados, funciones, o empaquetados procedimientos y funciones que se exponen como operaciones de sondeo.  

  El adaptador ejecuta todas estas operaciones dentro de una transacción de Oracle.  

  El adaptador también le permite recibir los mensajes de cambios de datos de varios artefactos de Oracle en la misma aplicación mediante la exposición de un `PollingId` parámetro en el URI de conexión. Este parámetro modifica el espacio de nombres de destino de la operación POLLINGSTMT.  

## <a name="change-the-target-namespace-of-pollingstmt"></a>Cambiar el espacio de nombres de destino de POLLINGSTMT  
 Puede modificar el espacio de nombres de destino de la operación POLLINGSTMT estableciendo el `PollingId` parámetro de cadena en el URI de conexión de consulta. Si un `PollingId` se especifica en la conexión URI, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] anexa la cadena especificada en el `PollingId` parámetro para el espacio de nombres de destino predeterminado para la operación POLLINGSTMT: `http://microsoft.lobservices.oracledb/2007/03/POLLINGSTMT`. No se modifica la acción del mensaje de la operación POLLINGSTMT.  

 Por ejemplo, si se especifica el URI de conexión siguiente: `OracleDb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity`, será el espacio de nombres de destino `http:/microsoft.lobservices.oracledb/2007/03/POLLINGSTMTAcctActivity`.  

 Al proporcionar un espacio de nombres único para cada operación POLLINGSTMT, puede recibir mensajes de cambio de datos de varias tablas de Oracle y las vistas en la aplicación.  

 Para obtener más información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conexión URI, consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  

## <a name="receive-data-changed-messages-using-binding-properties"></a>Recibir mensajes de cambio de datos mediante las propiedades de enlace
 Configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir mensajes de cambio de datos estableciendo algunas o todas las siguientes propiedades de enlace.  


|         Propiedad de enlace         |                                                                                                                                                                                                                                                                                                                                                                   Valor                                                                                                                                                                                                                                                                                                                                                                    |      Valor predeterminado       |                                                                                  Opcional/Requerido                                                                                  |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                                                                                                                                                                              Asegúrese de que el valor se establece en **sondeo**.                                                                                                                                                                                                                                                                                                                                               |      Sondeo       |                                                           Requerido. Si no es explícitamente el conjunto, el valor predeterminado se aplicará.                                                            |
| **PolledDataAvailableStatement** | Especifique la instrucción SELECT ejecutada para determinar si los datos están disponibles para el sondeo para una tabla específica. La instrucción especificada debe devolver un conjunto que consta de filas y columnas de resultados. El valor de la primera celda del conjunto de resultados indica si el adaptador ejecuta el valor especificado para el **PollingStatement** enlaza la propiedad. Si la primera celda de resultado contiene un valor positivo, el adaptador ejecuta la instrucción de sondeo. Por ejemplo, una instrucción válida para esta propiedad de enlace será:<br /><br /> `Select * from <table_name>`<br /><br /> **Nota:** no debe especificar los procedimientos almacenados para esta propiedad de enlace. Además, esta instrucción no debe modificar la base de datos de Oracle subyacente. | SELECCIONE 1 DE DOBLE | Requerido. Si no es explícitamente el conjunto, el valor predeterminado se aplicará, lo cual implica que el adaptador debe continuar sondeo con independencia de si la tabla que se sondea tiene datos o no. |
|        **PollingAction**         |                                                                                                                                                                                                                                        Especifica la acción para la operación de sondeo. Puede determinar la acción de sondeo para una operación específica de los metadatos que se genera para la operación mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].                                                                                                                                                                                                                                         |        null        |                                                   Opcional para las operaciones de sondeo en las tablas y vistas mediante la instrucción SELECT.                                                   |
|       **PollingInterval**        |                                                                                                                                         Se establece en el intervalo, en segundos, en el que desea que el adaptador para consultar la base de datos de Oracle. Esta propiedad especifica el intervalo de sondeo y el tiempo de espera de transacción de sondeo. El valor debe ser mayor que la cantidad de tiempo que tarda en ejecutar la consulta y el sondeo posterior a la instrucción (si se especifica alguna) en la base de datos de Oracle más la cantidad de tiempo que tarda el cliente procesar los datos de consulta y devolver el mensaje de respuesta de sondeo.                                                                                                                                          |        500         |                                                           Requerido. Si no es explícitamente el conjunto, el valor predeterminado se aplicará.                                                            |
|       **PollingStatement**       |                                                                                                                                       Especifique cualquiera de las siguientes acciones:<br /><br /> -Instrucción SELECT SQL que se debe ejecutar en la base de datos de Oracle. Esta instrucción debe incluir una cláusula FOR UPDATE. Para obtener información acerca de la cláusula FOR UPDATE, consulte [especificar una cláusula FOR UPDATE en la instrucción de sondeo](#ForUpdate) más adelante en este tema.<br /><br /> -Mensaje de solicitud para un procedimiento almacenado, función o procedimiento o función dentro de un paquete que desea que se sondea.                                                                                                                                        |        null        |                                                     Requerido. Establecer **PollingStatement** en un valor distinto de null permite el sondeo.                                                     |
|      **PollWhileDataFound**      |                                                                                                                                                                                             Especifica si el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] pasa por alto el intervalo de sondeo y sondea continuamente la base de datos de Oracle, si hay datos disponibles en la tabla que se sondea. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado                                                                                                                                                                                              |       False        |                                                           Requerido. Si no es explícitamente el conjunto, el valor predeterminado se aplicará.                                                            |
|      **PostPollStatement**       |                                                                                                                                                                                                                                                                                          Se establece en un bloque de código PL/SQL opcional que se ejecuta el adaptador después de que se realiza la consulta, pero antes de la consulta se devuelven datos al cliente.                                                                                                                                                                                                                                                                                           |        null        |                                                     Opcional. Si se especifica ningún valor, no se ejecuta una instrucción de sondeo de envío.                                                      |

> [!NOTE]
>  Si usa el modelo de servicio WCF o el modelo de canal WCF, también debe establecer el **AcceptCredentialsInUri** enlaza la propiedad.  

##  <a name="ForUpdate"></a> Especificar FOR UPDATE en la instrucción de sondeo  
 Si usa una instrucción SELECT como la instrucción de sondeo y ejecutar una instrucción de sondeo posterior a la que afecta a las filas especificadas en la instrucción SELECT, debe usar la cláusula FOR UPDATE en la instrucción de sondeo. Especificar una cláusula FOR UPDATE garantiza que los registros seleccionados por la instrucción de sondeo se bloquean durante la transacción y que la instrucción de sondeo posterior puedan realizar todas las actualizaciones necesarias en ellos.  

> [!CAUTION]
>  Puede tener escenarios donde se encuentra en la ventana de tiempo entre las instrucciones de sondeos y posteriores a la encuesta, se agregan más registros a la tabla que cumplen la condición de la instrucción posterior a la encuesta. En tales situaciones, la instrucción de sondeo posterior actualizaría todos los registros que cumplen la condición y no solo los registros seleccionados como parte de la instrucción de sondeo.  

 Si se especifica una instrucción posterior a la encuesta y la instrucción de sondeo no contiene una cláusula FOR UPDATE, experimentará una de las dos condiciones siguientes:  

- Si **TransactionIsolationLevel** está establecido en **ReadCommitted**, la consulta de sondeo posterior no actualizará las filas seleccionadas.  

- Si **TransactionIsolationLevel** está establecido en **Serializable**, la siguiente excepción del sistema de destino (**Microsoft.ServiceModel.Channels.Common.TargetSystemException**) se producirá cuando se ejecuta la instrucción posterior a la encuesta: "no puede serializar el acceso para esta transacción ORA-08177". En tal caso, debe establecer el **PollingRetryCount** enlace de propiedad para definir el número de veces que desea que el adaptador para volver a intentar la misma transacción.  

  Para obtener instrucciones sobre cómo establecer el nivel de aislamiento de transacción, vea [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md).  

  Las instrucciones de sondeos y posteriores a la encuesta se ejecutan en una transacción si los clientes del adaptador se han configurado para utilizar las transacciones y el valor de la **UseAmbientTransaction** enlaza la propiedad se establece en **True**en el adaptador.  

  Es un ejemplo de una consulta de sondeo con la opción de actualización:  

```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE  
```  

### <a name="enter-a-nowait-clause-in-the-polling-statement"></a>Especifique una cláusula NOWAIT en la instrucción de sondeo  
 Puede que existan escenarios donde los subprocesos simultáneos que tienen acceso a la tabla que se sondea, dando lugar a demasiados contenciones en la tabla. Esto puede provocar que la consulta de sondeo para bloquearse para obtener un bloqueo en las filas de tabla. Si usa una instrucción SELECT que la instrucción de sondeo, desea especificar una palabra clave NOWAIT junto con la palabra clave FOR UPDATE en la instrucción SELECT. Esto hará que la ejecución de consultas de sondeo del adaptador para devolver inmediatamente si hay bloqueos en filas que se intenta seleccionar la consulta de sondeo. Normalmente, se produce una excepción por Oracle en dichas condiciones. De nuevo, pueden usar los clientes del adaptador el **PollingInterval** enlaza la propiedad para especificar el intervalo de tiempo después del cual deben reintentar la clientes del adaptador para el sondeo de los datos.  

 Un ejemplo de una consulta de sondeo con la opción de NOWAIT es:  

```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE NOWAIT  
```  

### <a name="enter-a-skip-locked-clause-in-the-polling-statement"></a>Especifique una cláusula SKIP bloqueado en la instrucción de sondeo  
 Puede que existan escenarios donde debido a subprocesos simultáneos que se accede a la tabla que se sondea, algunas filas del conjunto de resultados de la cláusula WHERE especifica en la consulta de sondeo se bloquean. Por ejemplo, la consulta de sondeo devuelve 6 filas de una tabla; 4 de 6 estas filas ya están bloqueados debido a alguna otra transacción. En este caso, puede especificar una palabra clave SKIP bloqueado junto con la palabra clave FOR UPDATE que se indica a la base de datos para intentar bloquear las filas especificadas por la cláusula WHERE y para omitir todas las filas que no se encuentran ya se ha bloqueado. Las filas desbloqueadas en la cláusula WHERE se bloquean durante la transacción y la instrucción de sondeo posterior a la puede realizar todas las actualizaciones necesarias en ellos para que estas filas no se sondean nuevo. Esto garantiza que no es necesario esperar para recibir los mensajes de sondeo hasta que todas las filas especificado por la cláusula WHERE se desbloqueen.  

 La palabra clave SKIP bloqueado es útil en un escenario donde tiene los clientes del adaptador en varios equipos que sondean la misma tabla en una base de datos. Puede equilibrarse entre los clientes del adaptador mediante la configuración de la operación de sondeo de tal manera que recibe mensajes de cambio de datos basados en sondeos para las filas especificadas por la cláusula WHERE que están bloqueadas en ese momento del tiempo y, a continuación, actualizar la fila para asegurarse de que si se recibe un mensaje de cambio de datos basados en sondeos por un cliente del adaptador, los demás clientes no obtener el mismo mensaje.  

 Es un ejemplo de una consulta de sondeo con la opción SKIP bloqueado:  

```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE SKIP LOCKED  
```  

## <a name="support-for-ordered-delivery-fifo"></a>Soporte técnico para la entrega ordenada (FIFO)  
 En un entorno de producción, el sondeo puede utilizarse para supervisar los cambios de datos en la base de datos de Oracle. Estos mensajes de cambio de datos son recibidos por el cliente del adaptador mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. En función de los escenarios empresariales, puede ser crítico que se reciben los mensajes de cambio de datos por el cliente de adaptador en el orden correcto.  

 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite ordenados de entrega o primero en el primero en salir (FIFO) para mantener el orden en el que se reciben mensajes de la base de datos de Oracle. Estas son algunas consideraciones relacionadas con la compatibilidad de FIFO en escenarios de entrada para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  

- Si el mensaje es consumido por una orquestación, la orquestación debe tener la entrega ordenada establecida para los mensajes procedentes de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] puerto de recepción.  

- Si el mensaje es consumido por un escenario de envío puerto (en un enrutamiento por contenidos), el puerto de envío debe haber pedido de entrega para los mensajes procedentes de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] puerto de recepción.  

  El adaptador de WCF-Custom o WCF-OracleDB tiene una propiedad **suspender mensaje de solicitud en caso de error** que especifica si se debe suspender el mensaje de solicitud que se produce un error de procesamiento de entrada. Esta propiedad puede establecerse en el **mensajes** ficha de WCF-Custom o WCF-OracleDB reciba el puerto en el **control de errores** sección. En la tabla siguiente se enumera los escenarios que describen cómo se procesan los mensajes entrantes en función de si se establece esta propiedad y el estado del suscriptor de mensaje (orquestación o puerto).  

|Port, propiedad|Suscriptor en un estado dado de baja|Suscriptor de dado de alta, pero el estado detenido|  
|-------------------|------------------------------------|----------------------------------------------|  
|**Suspender el mensaje de solicitud en caso de error** no establece la propiedad|-Se genera el informe de error enrutamiento como suspendido (no reanudable mensaje)<br /><br /> -No se suspende el mensaje real<br /><br /> -Post no se ejecuta la consulta de sondeo tal como se anula la transacción. Sondeo por lo tanto, se repite y captura las filas de nuevo.<br /><br /> -Los errores notificados en el caso de que el registro para describir lo que ha sucedido.|-No se considera un "error". No hay ningún mensaje de error en el registro de eventos.<br /><br /> -Real del mensaje se coloca en la cola suspendida (reanudable).<br /><br /> -Cuando se inicia la orquestación o puerto de suscripción, se reanudan automáticamente los mensajes. Si se establece la entrega ordenada en el suscriptor, se respetará.<br /><br /> -Los mensajes también se pueden reanudar manualmente.|  
|**Suspender el mensaje de solicitud en caso de error** se establece la propiedad|-Se genera el informe de error enrutamiento como suspendido (no reanudable mensaje)<br /><br /> -También se suspenderá el mensaje real<br /><br /> -Post no se ejecuta la consulta de sondeo tal como se anula la transacción. Sondeo por lo tanto, se repite y captura las filas de nuevo.<br /><br /> -Los errores notificados en el caso de que el registro para describir lo que ha sucedido.|-No se considera un "error". No hay ningún mensaje de error en el registro de eventos.<br /><br /> -Real del mensaje se coloca en la cola suspendida (reanudable).<br /><br /> -Cuando se inicia la orquestación o puerto de suscripción, se reanudan automáticamente los mensajes. Si se establece la entrega ordenada en el suscriptor, se respetará.<br /><br /> -Los mensajes también se pueden reanudar manualmente.|  

## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)  
 [Sondeo de base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)   
 [Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)   
 [Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)