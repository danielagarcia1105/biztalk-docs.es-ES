---
title: Solucionar problemas de funcionamiento con el adaptador SQL en BizTalk | Documentos de Microsoft
description: Problemas comunes y soluciones para el adaptador de SQL en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6850a1b8c3b0cb5d1356078fce8dc8f50c6963
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010989"
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a>Solucionar problemas de funcionamiento con el adaptador de SQL
Esta sección describe el uso de técnicas de solución de problemas para resolver errores de operaciones que pueden surgir al usar [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].  
  
## <a name="enabling-tracing"></a>La habilitación del seguimiento  
 Debe habilitar el seguimiento entre el adaptador, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], y SQL Server para obtener más información sobre todos los aspectos que tener al usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para obtener más información acerca del seguimiento de soporte técnico en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [el seguimiento de diagnóstico y registro de mensajes en el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md).  
  
## <a name="known-issues"></a>Problemas conocidos  
 Éstos son los errores más comunes que pueden surgir al usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], junto con sus causa probable y la resolución.  
  
  
  
###  <a name="BKMK_SQLLoadBinding"></a>Error al cargar los enlaces del adaptador  
 **Problema**  
  
 Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], obtendrá el error siguiente:  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **Causa**  
  
 Al intentar iniciar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF carga los enlaces del adaptador para todos los adaptadores instalados. En cambio, los enlaces del adaptador están depende del software de cliente específico para la aplicación de empresa. Es posible que tenga este problema si ya realizó una instalación típica o completo del adaptador, que se instala todos los adaptadores incluidos en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Sin embargo, podrían instalarse las bibliotecas de cliente LOB para solo una aplicación empresarial. Como resultado, la interfaz gráfica de usuario produce un error al cargar los enlaces para los demás adaptadores.  
  
 **Resolución**  
  
 Asegúrese de que se realiza una instalación personalizada de los adaptadores para instalar a sólo el adaptador que necesita.  
  
###  <a name="BKMK_SQLDisplay"></a>El adaptador de SQL no se muestra en la lista de adaptadores en la consola de administración de BizTalk Server  
 **Problema**  
  
 A diferencia de la versión anterior de los adaptadores incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparecen en la lista de adaptadores en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 **Causa**  
  
 La versión más reciente [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un enlace personalizado de WCF. Por lo tanto, aunque la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra de la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no se mostrarán basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 **Resolución**  
  
 Puede agregar explícitamente la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregar el adaptador de SQL a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).  
  
###  <a name="BKMK_MissingAction"></a>Error al realizar operaciones en una base de datos de SQL Server  
 **Problema**  
  
 El adaptador produce el siguiente error al realizar cualquier operación en una base de datos de SQL Server mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
-   **Para que BizTalk Server**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **Causa**  
  
 No se especifica la acción de WCF para el mensaje. WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador acerca de la operación se realizará en la aplicación de LOB.  
  
 **Resolución**  
  
 Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk. Para obtener instrucciones, consulte [configurar la acción SOAP para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md). Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) para ver una lista de acciones para cada operación.  
  
###  <a name="BKMK_SQLInvalidOp"></a>Excepción InvalidOperationException con ErrorCode = 5 al realizar operaciones de FILESTREAM  
 **Problema**  
  
 Obtiene el siguiente error mientras usa el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para realizar operaciones de FILESTREAM.  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 **Causa**  
  
 Se pueden especificar credenciales de base de datos para conectarse a la base de datos de SQL Server. Para llevar a cabo operaciones de FILESTREAM, siempre debe utilizar la autenticación de Windows. El código de error "5" indica que se deniega el acceso debido a credenciales incorrectas. Para obtener más información acerca de los códigos de error diferentes, consulte [códigos de Error de sistema (0-499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx).
  
 **Resolución**  
  
 Utilice la autenticación de Windows para conectarse a la base de datos de SQL Server. En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, puede hacerlo por dejar al usuario los campos de nombre y una contraseña en blanco en el cuadro de diálogo de configuración de puerto WCF-Custom o WCF-SQL.  
  
###  <a name="BKMK_SQLPolling"></a>Sondear la operación no devuelve ningún mensaje incluso si se especifican las instrucciones válidas para PollingStatement y PolledDataAvailableStatement  
 **Problema**  
  
 Incluso si se especifican los valores válidos para las propiedades de enlace PollingStatement y PolledDataAvailableStatement, el adaptador no recibe un mensaje de sondeo de SQL Server.  
  
 **Causa**  
  
 Compruebe si otra transacción ha tomado un bloqueo en la tabla que se está sondeando el adaptador.  
  
 **Resolución**  
  
 Si desea sondear una tabla que se está actualizando como parte de otra transacción, puede considerar el uso de parámetro "con (nolock)" como parte de la consulta especificada para la propiedad de enlace de PolledDataAvailableStatement para asegurarse de que se devuelvan datos incluso si se impone un bloqueo la otra transacción. Para obtener más información, consulte [el bloqueo de SQL en el motor de base de datos](https://msdn.microsoft.com/library/ms190615.aspx).
  
###  <a name="BKMK_SQLSingleOp"></a>Se produce un error en el adaptador Insertar, actualizar o eliminar grandes volúmenes de datos en una sola operación mediante BizTalk Server  
 **Problema**  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no se puede insertar, actualizar o eliminar grandes volúmenes de datos en una única operación utilizando [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 **Causa**  
  
 Insertar, actualizar o eliminar grandes volúmenes de datos puede tardar tiempo y la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] o la transacción en la que se realiza la operación, puede agotar el tiempo.  
  
 **Resolución**  
  
-   **Para que BizTalk Server**  
  
    1.  Especifique el tiempo de espera para el adaptador de WCF en el archivo machine.config. Navegue hasta el archivo machine.config en \<unidad del sistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG y agregue el extracto que tiene el siguiente aspecto.  
  
        ```  
        <configuration>  
         <system.transactions>  
          <machineSettings maxTimeout="02:00:00" />  
         </system.transactions>  
        </configuration>  
        ```  
  
         Con esta configuración, el tiempo de espera del adaptador WCF se establece en 2 horas.  
  
    2.  Especifique la configuración de tiempo de espera para las transacciones de MSDTC en el archivo machine.config. Navegue hasta el archivo machine.config en \<unidad del sistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG y agregue el extracto que tiene el siguiente aspecto.  
  
        ```  
        <system.transactions>   
                <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
            </system.transactions>  
  
        ```  
  
         Con esta configuración, el tiempo de espera MSDTC se establece en 2 horas. El valor predeterminado de tiempo de espera MSDTC es 10 minutos.  
  
        > [!IMPORTANT]
        >  Debe realizar este cambio en los equipos que ejecutan el cliente de adaptador y SQL Server. En el extracto, reemplace < nombre_equipo > por el nombre del equipo que ejecuta el cliente de adaptador y SQL Server.  
  
    3.  Establecer el **SendTimeout** enlace de propiedad para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en un valor bastante grande. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).  
  
###  <a name="BKMK_SQLFullSchemaValidate"></a>Se produce un error de validación de esquemas completo en el servidor BizTalk Server para los mensajes de respuesta que contiene el conjunto de datos  
 **Problema**  
  
 Para las operaciones que devuelven un mensaje de respuesta que contiene un conjunto de datos, por ejemplo ExecuteReader, la validación del esquema completa se produce un error en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 **Resolución**  
  
 Se recomienda no realizar una validación del esquema completo para los mensajes de respuesta que contiene un conjunto de datos. En su lugar, podría hacer lo siguiente:  
  
1.  Ejecuta la operación una vez que devuelve el mensaje de respuesta con el esquema.  
  
2.  Copie el esquema del mensaje de respuesta en un archivo .xsd y agregue este archivo al proyecto de BizTalk.  
  
3.  Usar una consulta xpath en la orquestación para extraer los datos del mensaje de respuesta.  
  
###  <a name="BKMK_SQLRootNode"></a>Error con RootNode TypeName en proyectos de BizTalk  
 **Problema**  
  
 En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **Resolución**  
  
1.  Haga clic en el nodo rood hace referencia en el error y seleccione **propiedades**.  
  
2.  Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o reservados palabras, por ejemplo, punto (.).  
  
###  <a name="BKMK_SQLMetadataStronglyTyped"></a>Se produce un error de adaptador generar metadatos de procedimiento almacenado fuertemente tipado con tablas temporales  
 **Problema**  
  
 Se produce un error en el adaptador generar metadatos para procedimientos almacenados fuertemente tipadas que incluyen tablas temporales en su definición. El adaptador proporciona la siguiente excepción.  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 **Resolución**  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no admite la generación de metadatos para procedimientos almacenados fuertemente tipadas que contienen tablas temporales en su definición. En su lugar, debe generar metadatos para el mismo procedimiento en el **procedimientos** nodo durante el uso de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
###  <a name="BKMK_SQLVS2008"></a>Advertencia de enlace no válido al utilizar el adaptador en Visual Studio  
 **Problema**  
  
 Cuando se utiliza el adaptador para crear una aplicación en Visual Studio y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **Causa**  
  
 Esta advertencia aparece porque la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace, `sqlBinding`, se incluye no es un enlace estándar con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].  
  
 **Resolución**  
  
 Puede omitir esta advertencia de forma segura.  
  
###  <a name="BKMK_SQLNotification"></a>BizTalk Server produce una excepción si se utiliza más de un esquema de notificación en la misma aplicación o el esquema de notificación en varias aplicaciones en el mismo host  
 **Problema**  
  
 BizTalk Server produce una excepción de XLANG o una excepción que indica que la aplicación no encuentra la especificación de documento porque varios esquemas coincida con el tipo de mensaje.  
  
 **Causa**  
  
 Esto se debe a alguno de los siguientes:  
  
-   Ha generado más de un esquema de notificación en un proyecto de BizTalk Server, implementado en una aplicación de BizTalk Server y, a continuación, se ejecutó la aplicación para recibir notificaciones de la base de datos de SQL Server. Dado que los esquemas de notificación son comunes, hay un conflicto entre los esquemas que se implementan en la aplicación de BizTalk Server.  
  
-   En el caso de varios proyectos, ha generado un esquema de notificación para cada uno de los proyectos que se implementan cada proyecto a una aplicación de BizTalk Server independiente en el mismo host de BizTalk Server y, a continuación, se ejecutaba una aplicación o aplicaciones reciban notificaciones de la base de datos de SQL Server. Dado que los esquemas y los ensamblados son accesibles a través de las aplicaciones de BizTalk Server, hay un conflicto entre los esquemas comunes implementados en aplicaciones de BizTalk Server y los ensamblados.  
  
 **Resolución**  
  
 Usar un único archivo de esquema de notificación para una aplicación de BizTalk Server. Si tiene que usar el esquema de notificación de varias aplicaciones de BizTalk Server en el mismo host, crear una aplicación que contenga un único esquema de notificación y, a continuación, utilice el esquema de notificación de todas las demás aplicaciones de BizTalk Server.  
  
###  <a name="BKMK_SQLRestoreConn"></a>Adaptador cliente produce una excepción acerca de cómo realizar una operación después de que se restaura la conectividad entre el cliente de adaptador y la base de datos de SQL Server  
 **Problema**  
  
 Cliente de adaptador inicia la siguiente excepción al ejecutar una operación en la base de datos de SQL Server:  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 **Causa**  
  
 Durante la ejecución de una operación, el adaptador utiliza la conexión de la agrupación de conexiones ADO.NET de SQL para conectarse a la base de datos de SQL Server y realizar la operación. Si se produce una interrupción de red breve entre el cliente de adaptador y la base de datos de SQL Server o la base de datos de SQL Server está inactivo temporalmente, todas las conexiones en la agrupación de conexiones ADO.NET de SQL no están válidas. Después de que se restaura la conectividad e intenta realizar una operación en la base de datos de SQL Server, el adaptador usa las mismas conexiones no válidas de la agrupación de conexiones ADO.NET de SQL y, por lo tanto, el cliente de adaptador produce la excepción.  
  
 **Resolución**  
  
 El cliente de adaptador debe implementar la lógica de reintento en la ejecución de su operación donde debe detectar la excepción y especifique el número de reintentos de la operación como "n+1", donde "n" es el valor especificado para la propiedad de enlace de MaxConnectionPoolSize. Esto implica que si hay "n" número de conexiones del grupo de conexiones que se han procesado no válido, teóricamente el adaptador cliente debería reintentar durante un máximo de "n+1" veces para obtener una conexión válida y, por lo tanto, realizar la operación.  
  
 Por ejemplo, para especificar el nuevo número en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], abra el **propiedades** cuadro de diálogo de un puerto de envío en una aplicación, haga clic en **opciones avanzadas de transporte** en el panel izquierdo del cuadro de diálogo y en el **Opciones de transporte** área, especifique un valor en el **número de reintentos** lista.  
  
###  <a name="BKMK_MemUsage"></a>Uso de memoria y subproceso recuento aumenta cuando se usa el adaptador en una operación de entrada de transacción  
 **Problema**  
  
 En una operación de entrada transacción, como el sondeo, **si no hay ningún dato disponible en la tabla se sondean,** y el adaptador while sigue sondeando, durante un período de tiempo experimente un aumento en el uso de memoria y el número de subprocesos.  
  
 **Causa**  
  
 **Si no hay ningún dato disponible en la tabla se sondean**, después cada ciclo de tiempo de espera de recepción [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] genera un nuevo subproceso para continuar con la operación de sondeo. Por lo tanto, el uso de memoria y el número de subprocesos aumenta durante un período de tiempo. Sin embargo, si la tabla se sondean, tiene algunos datos, sigue el mismo subproceso realizar todos los sondeos subsiguientes.  
  
 **Resolución**  
  
 Se recomienda establecer el **ReceiveTimeout** para el valor máximo posible, que es 24.20:31:23.6470000 (24 días) para que se genera un subproceso nuevo solo cada 24 días. Esto garantizará que el recuento de subprocesos y de uso de memoria no aumente demasiado demasiado pronto.  
  
> [!NOTE]
>  Si se ha establecido SqlAdapterInboundTransactionBehavior, asegúrese de que el TransactionTimeout también está configurado para el valor máximo posible, que es 24.20:31:23.6470000 (24 días). Al utilizar esta solución alternativa, podemos agregar la SqlAdapterInboundTransactionBehavior sólo si el nivel de aislamiento de transacción debe estar configurado. En caso contrario, es una práctica recomendada para quitar ese comportamiento.  
  
 Para obtener más información sobre la **ReceiveTimeout** enlace de propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener instrucciones sobre cómo especificar propiedades de enlace, consulte [configurar las propiedades de enlace para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).  
  
> [!NOTE]
>  Al usar el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], establecer el tiempo de espera en un valor grande no afecta a la funcionalidad del adaptador.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador SQL](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)