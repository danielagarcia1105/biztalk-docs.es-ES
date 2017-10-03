---
title: Recibir mensajes de cambio de datos basado en sondeo de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbcb23d0-508d-4601-91b4-c674d76cd063
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aed2e9b42be9aaa44f1f79bf11da03d737dac4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-from-oracle-e-business-suite"></a>Recibir mensajes de cambio de datos basado en sondeo de Oracle E-Business Suite
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] admite la recepción de mensajes de cambio de datos basados en el sondeo por sondeo en las tablas de interfaz, vistas de interfaz, tablas y vistas. El adaptador entrega los mensajes a la aplicación por:  
  
-   Ejecutar una consulta SELECT de SQL para determinar si los datos están disponibles para el sondeo. Puede configurar el adaptador para ejecutar la consulta SELECT de SQL periódicamente o de forma continua.  
  
-   Ejecutar una consulta SELECT de SQL en una tabla de Oracle o la vista o ejecutar procedimientos, funciones, o empaquetados procedimientos almacenados y funciones.  
  
-   Ejecuta un bloque de código de PL/SQL posterior a la encuesta opcional en Oracle E-Business Suite. Este bloque de código se utiliza a menudo para actualizar un campo en los registros consultados en el destino o para mover los registros consultados a otra tabla o vista.  
  
-   Devolver los resultados de consulta en un resultado de establece mediante la invocación de la operación de sondeo o los procedimientos almacenados, funciones, o empaquetados procedimientos y funciones que se exponen como las operaciones de sondeo.  
  
 El adaptador ejecuta todas estas operaciones dentro de una transacción de Oracle.  
  
## <a name="how-do-i-configure-the-oracle-e-business-adapter-for-receiving-data-changed-messages-using-binding-properties"></a>¿Cómo se puede configurar el adaptador de Oracle E-Business para recibir los mensajes de cambio de datos mediante propiedades de enlace?  
 Configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de cambio de datos mediante el establecimiento de algunas o todas las siguientes propiedades de enlace.  
  
|Propiedad de enlace|Valor|Predeterminado|Opcional/Requerido|  
|----------------------|-----------|-------------|------------------------|  
|**InboundOperationType**|Asegúrese de que el valor se establece en **sondeo**.|Sondeo|Requerido. Si no es explícitamente conjunto, el valor predeterminado se aplicará.|  
|**PolledDataAvailableStatement**|Especifique la instrucción SELECT que se ejecuta para determinar si los datos están disponibles para el sondeo para una tabla específica. La instrucción especificada debe devolver un conjunto que consta de filas y columnas de resultados. El valor de la primera celda del conjunto de resultados indica si el adaptador ejecuta el valor especificado para la **PollingInput** propiedad de enlace. Si la primera celda del resultado contiene un valor positivo, el adaptador ejecuta la instrucción de sondeo. Por ejemplo, una instrucción válida para esta propiedad de enlace será:<br /><br /> `Select * from <table_name>`<br /><br /> **Nota:** no se deben especificar los procedimientos almacenados para esta propiedad de enlace. Además, esta instrucción no debe modificar los datos de Oracle E-Business Suite o la base de datos de Oracle subyacente.|null|Requerido.|  
|**PollingAction**|Especifica la acción para la operación de sondeo. Puede determinar la acción de sondeo para una operación específica de los metadatos que se ha generado para la operación con el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].|null|Es opcional para las operaciones de sondeo en tablas y vistas mediante la instrucción SELECT.|  
|**PollingInput**|Especificar cualquiera de las siguientes acciones:<br /><br /> -Instrucción SQL SELECT que se debe ejecutar en Oracle E-Business Suite. Esta instrucción debe incluir una cláusula FOR UPDATE. Para obtener información acerca de la cláusula FOR UPDATE, consulte [especificar una cláusula FOR UPDATE en la instrucción de sondeo](#ForUpdate) más adelante en este tema.<br /><br /> -Mensaje de solicitud para un procedimiento almacenado, función o procedimiento o función dentro de un paquete que desea que se sondea.|null|Requerido. Establecer **PollingInput** con un valor distinto de null permite el sondeo.|  
|**PollingInterval**|Establecer el intervalo, en segundos, en el que desea que el adaptador de consulta de Oracle E-Business Suite. Esta propiedad especifica el intervalo de sondeo y el tiempo de espera de transacción de sondeo. El valor debe ser mayor que la cantidad de tiempo necesario para ejecutar la consulta y el sondeo posterior a la instrucción (si se especifica alguna) en Oracle E-Business Suite más la cantidad de tiempo que tarda el cliente procesar los datos de la consulta y devolver el mensaje de respuesta de sondeo.|30|Requerido. Si no es explícitamente conjunto, el valor predeterminado se aplicará.|  
|**PollWhileDataFound**|Especifica si el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa por alto el intervalo de sondeo y sondea continuamente de Oracle E-Business Suite, si los datos están disponibles en la tabla que se va a sondear. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado|False|Requerido. Si no es explícitamente conjunto, el valor predeterminado se aplicará.|  
|**PostPollStatement**|Se establece en un bloque de código de PL/SQL opcional que se ejecuta el adaptador cuando se realiza la consulta, pero antes de la consulta los datos se devuelven al cliente.|null|Opcional. Si no se especifica ningún valor, no se ejecuta una instrucción de sondeo de envío.|  
  
> [!NOTE]
>  Si está utilizando el modelo de servicio WCF o el modelo de canal WCF, también debe establecer el **AcceptCredentialsInUri** propiedad de enlace.  
  
##  <a name="ForUpdate"></a>Especificar FOR UPDATE cláusula en la instrucción de sondeo  
 Si se usa una instrucción SELECT como la instrucción de sondeo y ejecutar una instrucción de sondeo posterior a la que afecta a las filas especificadas en la instrucción SELECT, debe utilizar la cláusula FOR UPDATE en la instrucción de sondeo. Especifica una cláusula FOR UPDATE, se garantiza que los registros seleccionados por la instrucción de sondeo se bloquean durante la transacción y que la instrucción de sondeo posterior a la puede realizar todas las actualizaciones necesarias en ellos.  
  
> [!CAUTION]
>  Puede haber escenarios cuando, en la ventana de tiempo entre las instrucciones de sondeos y posteriores a la encuesta, más registros se agregan a la tabla que cumplen la condición de la instrucción de sondeo posterior a la. En estas situaciones, la instrucción de sondeo posterior a la actualizaría todos los registros que satisfacen la condición y no solo los registros seleccionados como parte de la instrucción de sondeo.  
  
 Si se especifica una instrucción posterior a la de sondeo y la instrucción de sondeo no contiene una cláusula FOR UPDATE, experimentará una de las dos condiciones siguientes:  
  
-   Si **TransactionIsolationLevel** está establecido en **ReadCommitted**, la consulta de sondeo posterior no actualizará las filas seleccionadas.  
  
-   Si **TransactionIsolationLevel** está establecido en **Serializable**, la siguiente excepción del sistema de destino (**Microsoft.ServiceModel.Channels.Common.TargetSystemException**) se producirá cuando se ejecuta la instrucción posterior a la encuesta: "no puede serializar el acceso para esta transacción ORA-08177". En tal caso, debe establecer el **PollingRetryCount** enlace de propiedad para definir el número de veces que desea que el adaptador para volver a intentar la misma transacción.  
  
 Para obtener instrucciones sobre cómo establecer el nivel de aislamiento de transacción, vea [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).  
  
 Las instrucciones de sondeos y posteriores a la encuesta se ejecutan en una transacción si los clientes de adaptador que han configurado para utilizar las transacciones y el valor de la **UseAmbientTransaction** enlaza la propiedad se establece en **True**en el adaptador.  
  
 Es un ejemplo de una consulta de sondeo con la opción de actualización:  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE  
```  
  
### <a name="specifying-a-nowait-clause-in-the-polling-statement"></a>Especificar una cláusula NOWAIT en la instrucción de sondeo  
 Es posible que tenga escenarios donde los subprocesos simultáneos que tienen acceso a la tabla que se han sondeado, dando lugar a demasiados contenciones en la tabla. Esto puede provocar que la consulta de sondeo para bloquearse para obtener un bloqueo en filas de la tabla. Si se usa una instrucción SELECT que la instrucción de sondeo, puede que desee especificar una palabra clave NOWAIT junto con la palabra clave FOR UPDATE en la instrucción SELECT. Esto hará que la ejecución de la consulta de sondeo en el adaptador para devolver inmediatamente si hay bloqueos en filas que la consulta de sondeo es intentar seleccionar. Normalmente se produce una excepción por Oracle en dichas condiciones. Una vez más, pueden usar los clientes de adaptador el **PollingInterval** propiedad para especificar el intervalo de tiempo después del cual deben reintentar la clientes de adaptador para el sondeo de los datos de enlace.  
  
 Un ejemplo de una consulta de sondeo con la opción de NOWAIT es:  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE NOWAIT  
```  
  
### <a name="specifying-a-skip-locked-clause-in-the-polling-statement"></a>Especificar una SKIP (cláusula) bloqueada en la instrucción de sondeo  
 Puede que tenga escenarios donde debido a subprocesos simultáneos que tienen acceso a la tabla se sondean, algunas filas del conjunto de resultados de la cláusula WHERE especifica en la consulta de sondeo se bloquean. Por ejemplo, la consulta de sondeo devuelve 6 filas de una tabla; 4 fuera de estos 6 filas ya están bloqueados debido a alguna otra transacción. En este caso, puede especificar una palabra clave SKIP bloqueado junto con la palabra clave FOR UPDATE que se indica a la base de datos al intentar bloquear las filas especificadas mediante la cláusula WHERE y para omitir todas las filas que se encuentran ya se bloquee. Las filas desbloqueadas en la cláusula WHERE se bloquean durante la transacción y la instrucción de sondeo posterior a la puede realizar todas las actualizaciones necesarias en ellas para que estas filas no se sondean nuevo. Esto garantiza que no tiene que esperar para recibir los mensajes de sondeo hasta que todas las filas especifica mediante la cláusula WHERE se desbloquean.  
  
 La palabra clave SKIP bloqueado es útil en un escenario donde haya clientes de adaptador en varios equipos que realizan un sondeo la misma tabla en una base de datos. Puede equilibrarse entre los clientes de adaptador mediante la configuración de la operación de sondeo de tal manera que se reciben mensajes de cambio de datos basado en sondeo para las filas especificadas mediante la cláusula WHERE que se desbloquean en ese momento del tiempo y, a continuación, actualizar la fila para asegurarse de que si se recibe un mensaje de cambio de datos basado en sondeo por un cliente de adaptador, los demás clientes no obtienen el mismo mensaje.  
  
 Es un ejemplo de una consulta de sondeo con la opción SKIP bloqueado:  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE SKIP LOCKED  
```  
  
## <a name="support-for-ordered-delivery-fifo"></a>Soporte técnico para la entrega ordenada (FIFO)  
 En un entorno de producción, el sondeo puede utilizarse para supervisar los cambios de datos de Oracle E-Business Suite. Estos mensajes de cambio de datos son recibidos por el cliente de adaptador con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. En función de los escenarios empresariales, puede ser crítica que se reciben los mensajes de datos cambiado por el cliente de adaptador en el orden correcto.  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite ordenada entrega o primero en el primero en salir (FIFO) para mantener el orden en el que se reciben mensajes de Oracle E-Business Suite. Estas son algunas consideraciones relacionadas con la compatibilidad para FIFO en escenarios de entrada para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
-   Si el mensaje se ha consumido una orquestación, la orquestación debe tener la entrega ordenada establecida para los mensajes procedentes de la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] el puerto de recepción.  
  
-   Si un escenario de puerto (en un enrutamiento por contenidos) de envío se ha consumido el mensaje, el puerto de envío debe han pedido de entrega para los mensajes procedentes de la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] el puerto de recepción.  
  
 El adaptador de WCF-Custom o WCF-OracleEBS tiene una propiedad **suspender el mensaje de solicitud en caso de error** que especifica si se debe suspender el mensaje de solicitud que se produce un error de procesamiento de entrada. Esta propiedad puede establecerse en el **mensajes** puerto en la ficha de recepción de la ficha de WCF-Custom o WCF-OracleEBS la **control de errores** sección. En la tabla siguiente se enumera los escenarios que describen cómo se procesan los mensajes entrantes en función de si se establece esta propiedad y el estado del suscriptor de mensaje (orquestación o puerto).  
  
|Propiedad de puerto personalizado de WCF|Suscriptor en estado dado de baja|Suscriptor en dado de alta, pero el estado detenido|  
|-------------------------------|------------------------------------|----------------------------------------------|  
|**Suspender mensaje de solicitud en caso de error** no establece la propiedad|-Informe de error enrutamiento se genera como suspendido (no reanudable mensaje)<br /><br /> -No se suspende el mensaje real<br /><br /> -Post no se ejecuta la consulta de sondeo tal y como se anula la transacción. Por lo tanto, de sondeo se repite y captura las filas de nuevo.<br /><br /> -Los errores notificados en caso de registro para describir lo que se ha producido.|-No se considera un "error". No hay ningún mensaje de error en el registro de eventos.<br /><br /> -Real del mensaje se coloca en la cola suspendida (reanudable).<br /><br /> -Cuando se inicia la orquestación o puerto de suscripción, se reanudan automáticamente los mensajes. Si entrega ordenada se establece en el suscriptor, se respetará.<br /><br /> -Los mensajes también se pueden reanudar manualmente.|  
|**Suspender mensaje de solicitud en caso de error** se establece la propiedad|-Informe de error enrutamiento se genera como suspendido (no reanudable mensaje)<br /><br /> -También se suspenderá el mensaje real<br /><br /> -Post no se ejecuta la consulta de sondeo tal y como se anula la transacción. Por lo tanto, de sondeo se repite y captura las filas de nuevo.<br /><br /> -Los errores notificados en caso de registro para describir lo que se ha producido.|-No se considera un "error". No hay ningún mensaje de error en el registro de eventos.<br /><br /> -Real del mensaje se coloca en la cola suspendida (reanudable).<br /><br /> -Cuando se inicia la orquestación o puerto de suscripción, se reanudan automáticamente los mensajes. Si entrega ordenada se establece en el suscriptor, se respetará.<br /><br /> -Los mensajes también se pueden reanudar manualmente.|  
  
## <a name="see-also"></a>Vea también  
 [Actividades de desarrollo](../../esb-toolkit/development-activities.md)   
 [Sondeo Oracle E-Business Suite con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)