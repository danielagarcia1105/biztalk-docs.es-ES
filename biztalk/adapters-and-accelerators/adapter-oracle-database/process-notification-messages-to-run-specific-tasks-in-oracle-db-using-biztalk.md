---
title: "Procesar mensajes de notificación para completar tareas específicas en la base de datos de Oracle mediante BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 376055a7-98a6-4055-b6cd-2f5971349a6a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fa5f9d0eebeeaf7a7dcb264feb33373e48484d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="process-notification-messages-to-complete-specific-tasks-in-oracle-database-using-biztalk-server"></a>Procesar los mensajes de notificación para completar tareas específicas en la base de datos de Oracle mediante BizTalk Server
Puede usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir notificaciones de cambios en las tablas de base de datos de Oracle. Sin embargo, el adaptador sólo envía una notificación de que algunos registros se insertarlos, actualizarlos o eliminan en una tabla de base de datos determinada. Cualquier procesamiento posterior en esos registros debe controlarse las propias aplicaciones de cliente. En este tema se presenta una descripción basada en escenario sobre cómo procesar los registros de la tabla en función del tipo de notificación recibida de la base de datos de Oracle.  
  
## <a name="scenarios-for-performing-subsequent-actions-after-receiving-notification"></a>Escenarios para llevar a cabo las acciones posteriores tras recibir la notificación  
 Los siguientes son un par de escenarios en los que los clientes de adaptador deben realizar ciertas tareas posteriores a la notificación.  
  
-   **Escenario 1.** Considere un escenario donde el cliente de adaptador debe realizar determinadas tareas en función del tipo de notificación que se recibe de la base de datos de Oracle. Por ejemplo, la aplicación cliente debe actualizar los registros en la tabla "A" si se insertan registros en la tabla "B". De forma similar, la aplicación cliente debe eliminar los registros de la tabla "A" si se eliminan registros de la tabla "B".  
  
     En este escenario, desde el mensaje de notificación recibido, los clientes de adaptador deben extraer el tipo de notificación para decidir si la notificación era durante una operación de inserción o una operación de eliminación. Una vez que se determina el tipo de notificación, los clientes de adaptador deben realizar las acciones posteriores para insertar o actualizar las tablas pertinentes.  
  
-   **Escenario 2.** Considere un escenario donde la ubicación de recepción que recibe los mensajes de notificación de cambios en una tabla deja de funcionar. Aunque la ubicación de recepción está inactivo, algunos registros se agregan a la tabla. Sin embargo, para estos registros de cliente de adaptador no recibirá ninguna notificación. Cuando la ubicación de recepción es realizar copias de seguridad, el adaptador notifica al cliente mediante el envío de un mensaje concreto y, a continuación, la aplicación cliente debe buscar todos los registros que se insertaron en la tabla de base de datos mientras la ubicación de recepción no estaba disponible.  
  
     En este escenario, desde el mensaje de notificación recibido, los clientes de adaptador deben extraer la información sobre si la notificación es para un cambio en una tabla de base de datos o para el inicio de la ubicación de recepción. Si la notificación es para el inicio de la ubicación de recepción, los clientes de adaptador deben implementar la lógica para procesar los registros que se han insertado, actualizados o eliminar mientras la ubicación de recepción no estaba disponible.  
  
> [!NOTE]
>  Estos son solo algunos escenarios de ejemplo que se muestran para una mejor comprensión de cómo usar la característica de notificación en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Sin embargo, el conjunto básico de las tareas necesarias para extraer el tipo de notificación recibida será similar para todos los escenarios. Este tema proporciona instrucciones sobre cómo extraer el tipo de notificación de un mensaje de notificación.  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>Cómo en este tema se muestra cómo recibir mensajes de notificación  
 En este tema, para demostrar cómo procesar mensajes de notificación para realizar las tareas siguientes, se considere un escenario básico donde un cliente de adaptador utiliza la aplicación de BizTalk para recibir mensajes de notificación de cambios en la tabla ACCOUNTACTIVITY. Tras recibe la notificación, el cliente filtra el tipo de notificación recibida y lleva a cabo la acción posterior. Para mostrar un escenario muy básico, consideremos que el cliente de adaptador copia los mensajes de notificación en carpetas diferentes en función del tipo de notificación recibida. Por lo tanto:  
  
-   Si el mensaje de notificación es para una operación Insert o Update, el cliente de adaptador copia el mensaje en la carpeta C:\TestLocation\UpsertNotification.  
  
-   Si el mensaje de notificación es para cualquier otra operación, como eliminar, el cliente de adaptador copia el mensaje en la carpeta C:\TestLocation\OtherNotificaiton.  
  
 Para lograr esto como parte de una aplicación de BizTalk, la orquestación debe contener lo siguiente:  
  
-   Un unidireccional puerto de recepción para recibir mensajes de notificación.  
  
-   Una forma de expresión que contiene una consulta de xpath para extraer la información sobre el tipo de mensaje de notificación recibido.  
  
-   Una forma decidir debe incluir un bloque de decisión en la orquestación. En este bloque de decisión, la aplicación decide qué debe realizar las operaciones subsiguientes según el mensaje de notificación recibido.  
  
-   Unidireccional dos puertos de envío que finalmente reciban los mensajes de notificación.  
  
## <a name="configuring-notifications-with-the-oracle-database-binding-properties"></a>Configuración de notificaciones con la base de datos de Oracle propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] propiedades de enlace que se utiliza para configurar la recepción de notificaciones de la base de datos de Oracle. Debe especificar estas propiedades de enlace al configurar el puerto de recepción en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!NOTE]
>  Puede especificar estas propiedades de enlace al generar el esquema para el **notificación** operación, aunque no es obligatorio. Si lo hace, el enlace de puerto de archivos que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera como parte de la generación de metadatos también contiene los valores especificados para las propiedades de enlace. Más adelante puede importar este archivo de enlace en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puerto de recepción de la consola de administración para crear el WCF-custom o WCF-OracleDB con el enlace de propiedades ya establecidas. Para obtener más información acerca de cómo crear un puerto de WCF-custom o WCF-OracleDB mediante el archivo de enlace, vea [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
|Propiedad de enlace|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|Especifica la operación de entrada que se desea realizar. Para recibir mensajes de notificación, establezca esta propiedad en **notificación**.|  
|**NotificationPort**|Especifica el número de puerto que debe abrir ODP.NET para realizar escuchas de notificación de cambio de base de datos de base de datos de Oracle.|  
|**NotificationStatement**|Especifica la instrucción SELECT que se usa para registrar las notificaciones de consulta. El adaptador obtiene un mensaje de notificación solo cuando el conjunto de resultados para que los cambios de la instrucción SELECT especificada.|  
|**NotifyOnListenerStart**|Especifica si el adaptador envía una notificación a los clientes de adaptador cuando se inicia el agente de escucha.|  
  
 Para obtener una descripción más completa de estas propiedades, vea [trabajar con propiedades de enlace](https://msdn.microsoft.com/library/dd788467.aspx). Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir notificaciones de la base de datos de Oracle, seguir leyendo.  
  
## <a name="how-to-receive-notification-messages-from-oracle-database"></a>Cómo recibir mensajes de notificación de base de datos de Oracle  
 Realizar una operación en la base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] conlleva las tareas de procedimientos descritas en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md). Para configurar el adaptador para recibir mensajes de notificación, estas tareas son:  
  
1.  Crear un proyecto de BizTalk y, a continuación, genere el esquema para el **notificación** operación entrante. Si lo desea, puede especificar valores para la **InboundOperationType**, **NotificationPort**, y **NotificationStatement** propiedades de enlace.  
  
2.  Cree un mensaje en el proyecto de BizTalk para recibir notificaciones de la base de datos de Oracle.  
  
3.  Crear una orquestación como se describe en la sección anterior.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
    > [!NOTE]
    >  Para las operaciones de entrada, como recibir mensajes de notificación, solo se debe configurar un unidireccional WCF-Custom o WCF-OracleDB puerto de recepción. Bidireccional de recepción no se admiten los puertos para las operaciones de entrada.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generating-schema"></a>Generar el esquema  
 Debe generar el esquema para el **notificación** operación entrante. Vea [recuperar metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) para obtener más información acerca de cómo generar el esquema. Realice las tareas siguientes al generar el esquema. Omitir el primer paso si no desea especificar las propiedades de enlace en tiempo de diseño.  
  
1.  Especifique un valor para **InboundOperationType**, **NotificationPort**, y **NotificationStatement** propiedades de enlace al generar el esquema. Para obtener más información acerca de esta propiedad de enlace, vea [trabajar con propiedades de enlace](https://msdn.microsoft.com/library/dd788467.aspx). Para obtener instrucciones sobre cómo especificar las propiedades de enlace, consulte [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
2.  Seleccione el tipo de contrato **(operaciones de entrada) de servicio**.  
  
3.  Genere el esquema para el **notificación** operación.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Una vez que se genera el esquema, debe vincular a los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 De este tema, debe crear un mensaje para recibir notificaciones de la base de datos de Oracle.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas a esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana de vista de orquestación de BizTalk del proyecto, si no está ya abierto. Haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Type `NotifyReceive`.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *Process_Notification.OracleDBBinding.Notification*, donde *Process_Notification* es el nombre de su Proyecto de BizTalk. *OracleDBBinding* es el esquema generado para el **notificación** operación.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes de notificación de la base de datos de Oracle y, a continuación, realizar tareas según el tipo de notificación recibida. En esta orquestación, el adaptador recibe el mensaje de notificación basado en la instrucción SELECT especificada para la **NotificationStatement** propiedad de enlace. La consulta xpath especificada dentro de la forma de expresión extrae el tipo de notificación en una variable, digamos **NotificationType**. La forma decidir utiliza el valor de esta variable para decidir cuál es el tipo de notificación recibida y toma el "path" adecuado para realizar las operaciones posteriores. Como se mencionó en la sección anterior, la orquestación llevará a cabo las siguientes operaciones según el tipo de mensaje de notificación recibido.  
  
-   Si el mensaje de notificación es para una operación Insert o Update, el cliente de adaptador copia el mensaje en la carpeta C:\TestLocation\UpsertNotification.  
  
-   Si el mensaje de notificación es para cualquier otra operación, como eliminar, el cliente de adaptador copia el mensaje en la carpeta C:\TestLocation\OtherNotificaiton.  
  
 Por lo tanto, la orquestación debe contener lo siguiente:  
  
-   Un unidireccional puerto de recepción para recibir mensajes de notificación.  
  
-   Una forma de expresión que contiene una consulta de xpath para extraer el tipo de notificación recibida.  
  
-   Una forma decidir debe incluir un bloque de decisión en la orquestación. En este bloque de decisión, la aplicación decide qué debe realizar las operaciones subsiguientes según el mensaje de notificación recibido.  
  
-   Unidireccional dos puertos de envío que finalmente reciban los mensajes de notificación.  
  
-   Forma recepción.  
  
 Una orquestación de ejemplo es similar al siguiente.  
  
 ![Orquestación para realizar post &#45; la tarea de notificación](../../adapters-and-accelerators/adapter-oracle-database/media/40c637ea-dbec-47a8-b53b-58d6820093b4.gif "40c637ea-dbec-47a8-b53b-58d6820093b4")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación just-mencionado.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-Establecer **nombre** a *ReceiveNotification*<br /><br /> -Establecer **activar** a *es True*|  
  
### <a name="adding-an-expression-shape"></a>Agregar una forma expresión  
 El propósito de inclusión de una forma expresión en la orquestación es que una consulta de xpath para extraer el tipo de mensaje de notificación recibido. Antes de crear una consulta xpath, echemos un vistazo en el formato de un mensaje de notificación. Un mensaje de notificación típico es similar al siguiente:  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
  <Details>  
    <NotificationDetails>  
      <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
      <Info>1</Info>   
      <QueryId>0</QueryId>   
    </NotificationDetails>  
  </Details>  
  <Info>Insert</Info>   
  <ResourceNames>  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
  </ResourceNames>  
  <Source>Data</Source>   
  <Type>Change</Type>   
</Notification>  
```  
  
 Como verá, la información sobre el tipo de la notificación está disponible dentro de la `<info>` etiqueta dentro del elemento primario `<Notification>` etiqueta. Por lo tanto, como parte de esta forma de expresión debe:  
  
-   Cree una variable que contiene el valor dentro de la `<Info>` etiqueta y establezca su tipo en el objeto System.String. Para obtener más información acerca de cómo crear variables, consulte [usar Variables en orquestaciones](../../core/using-variables-in-orchestrations.md).  
  
     Para este tema, nombre de la variable como **NotificationType**.  
  
-   Crear una consulta de xpath para extraer el valor de la \<información > etiqueta. La consulta xpath asemejará a lo siguiente:  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     En esta consulta xpath, **NotifyReceive** es el mensaje que se ha creado para recibir mensajes de notificación. El extracto de la `string` función indica que la consulta debe extraer el valor dentro de la `<Info>` etiqueta, que a su vez está dentro de la `<Notification>` etiqueta. Por último, el valor extraído por la consulta se asigna a la **NotificaitonType** variable.  
  
### <a name="adding-a-decide-shape"></a>Agregar una forma decidir  
 Es el propósito de agregar una forma decidir debe incluir un bloque de decisión en la orquestación para decidir qué debe realizar las operaciones siguientes en función del tipo de mensaje de notificación recibido. La Decisión se toma en función del valor de la **NotificationType** variable. En este tema, la orquestación toma una decisión en función del tipo de mensaje de notificación recibido. Por lo tanto, la condición en la forma de regla se especifica como sigue:  
  
```  
NotificationType.Equals("Insert") | NotificationType.Equals("Update")  
```  
  
 Esta condición sugiere que if el valor de **NotificaitonType** variable es Insert o Update, la orquestación llevará a cabo un conjunto de tareas. Si el valor de **NotificationType** variable es algo más, la orquestación llevará a cabo otro conjunto de tareas.  
  
 Como se mencionó en las secciones anteriores, para mostrar de un método sencillo, la orquestación copiará mensajes en carpetas diferentes en función del tipo de mensaje de notificación. Por lo tanto, dentro de la regla y bloques de Else, debe agregar formas de envío para enviar los mensajes a distintos puertos. Para este tema, nombre de la forma de envío en el bloque de regla que **SendUpsertNotification** y la forma de envío en el bloque Else como **SendOtherNotification**.  
  
### <a name="adding-ports"></a>Agregar puertos  
 Ahora debe agregar los siguientes puertos lógicos a la orquestación:  
  
-   Unidireccional puerto de recepción para recibir mensajes de notificación de la base de datos de Oracle.  
  
-   Puerto de envío unidireccional para enviar mensajes de notificación para las operaciones Insert y Update a una carpeta específica.  
  
-   Puerto de envío unidireccional para enviar mensajes de notificación para todas las demás operaciones en una carpeta específica.  
  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna de puerto son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|OracleNotifyPort|-Establecer **identificador** a *OracleNotifyPort*<br /><br /> -Establecer **tipo** a *OracleNotifyPortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *de recepción*|  
|NotificationUpsertPort|-Establecer **identificador** a *NotificationUpsertPort*<br /><br /> -Establecer **tipo** a *NotificationUpsertPortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*|  
|OtherNotificationPort|-Establecer **identificador** a *OtherNotificationPort*<br /><br /> -Establecer **tipo** a *OtherNotificationPortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveNotification|-Establecer **mensaje** a *NotifyReceive*<br /><br /> -Establecer **operación** a *OracleNotifyPort.Notify.Request*|  
|SendUpsertNotification|-Establecer **mensaje** a *NotifyReceive*<br /><br /> -Establecer **operación** a *NotificationUpsertPort.Upsert.Request*|  
|SendOtherNotification|-Establecer **mensaje** a *seleccionar*<br /><br /> -Establecer **operación** a *OtherNotificationPort.Other.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe utilizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para que esta orquestación debe:  
  
    -   Definir un WCF-Custom físico o puerto de recepción unidireccionales de WCF-OracleDB. Este puerto de escucha notificaciones procedentes de la base de datos de Oracle. Para obtener información sobre cómo crear puertos de recepción, vea [configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md). Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  
  
        > [!IMPORTANT]
        >  No es necesario realizar este paso si especifica las propiedades de enlace en tiempo de diseño. En tal caso, puede crear un WCF-custom o WCF-OracleDB puerto de recepción, en el conjunto de propiedades de enlace necesaria, importando el archivo de enlace creado por la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Para obtener más información, consulte Configurar un físico puerto de enlace con un archivo de enlace de puerto.  
  
        |Propiedad de enlace|Valor|  
        |----------------------|-----------|  
        |**InboundOperationType**|Establezca esta propiedad en **notificación**.|  
        |**NotificationPort**|Especifica el número de puerto que debe abrir ODP.NET para realizar escuchas de notificación de cambio de base de datos de base de datos de Oracle. Establecer esto en el mismo número de puerto que debe haber agregado a la lista de excepciones de Firewall de Windows. Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, vea [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).<br /><br /> **Importante:** si se establece en el valor predeterminado de -1, tendrá que deshabilitar completamente el Firewall de Windows para recibir mensajes de notificación.|  
        |**NotificationStatement**|Establezca esta propiedad en:<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **Nota:** debe especificar el nombre de la tabla junto con el nombre del esquema. Por ejemplo, `SCOTT.ACCOUNTACTIVITY`.|  
        |**NotifyOnListenerStart**|Establezca esta propiedad en **True**.|  
  
         Para obtener más información acerca de las propiedades de enlace diferente, consulte [trabajar con propiedades de enlace](https://msdn.microsoft.com/library/dd788467.aspx).  
  
        > [!NOTE]
        >  Se recomienda configurar el nivel de aislamiento de transacción y el tiempo de espera de transacciones al realizar operaciones de entrada mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Puede hacerlo agregando el servicio de comportamiento al configurar el WCF-Custom o WCF-OracleDB puerto de recepción. Para obtener instrucciones sobre cómo agregar el comportamiento del servicio, consulte [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md).  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk colocará los mensajes de notificación de la base de datos de Oracle para operaciones Insert y Update. Configurar este puerto para colocar mensajes de notificación a la carpeta C:\TestLocation\UpsertNotification.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk colocará los mensajes de notificación de la base de datos de Oracle para todas las demás operaciones. Configurar este puerto para colocar mensajes de notificación a la carpeta C:\TestLocation\OtherNotification.  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para recibir mensajes de notificación de la base de datos de Oracle y para llevar a cabo las operaciones subsiguientes de Select y Update. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta fase, asegúrese de que:  
  
-   El WCF-Custom o WCF-OracleDB unidireccional puerto de recepción, que recibe los mensajes de notificación de la base de datos se ejecuta de Oracle.  
  
-   Los dos puertos de envío de archivo, que reciben mensajes de base de datos de Oracle, se están ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de iniciar la orquestación de BizTalk, el siguiente conjunto de acciones tienen lugar:  
  
-   Dado que la **NotifyOnListenerStart** enlaza la propiedad se establece en **True**, recibirá el mensaje siguiente:  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleDBBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta que el valor de la `<Info>` etiqueta es "ListnerStarted". Por lo tanto, se recibe este mensaje en la carpeta C:\TestLocation\OtherNotification.  
  
-   Insertar un registro en la tabla ACCOUNTACTIVITY. Recibirá un mensaje de notificación similar a lo siguiente:  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>1</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Insert</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta que el valor de la `<Info>` etiqueta es "Insertar". Por lo tanto, se recibe este mensaje en la carpeta C:\TestLocation\UpsertNotification.  
  
-   Actualizar un registro en la tabla ACCOUNTACTIVITY. Recibirá un mensaje de notificación similar a lo siguiente:  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>32</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Update</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta que el valor de la `<Info>` etiqueta es "Actualización". Por lo tanto, se recibe este mensaje en la carpeta C:\TestLocation\UpsertNotification.  
  
-   Eliminar un registro de la tabla ACCOUNTACTIVITY. Recibirá un mensaje de notificación similar a lo siguiente:  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>16</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Delete</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta que el valor de la `<Info>` etiqueta es "Eliminar". Por lo tanto, se recibe este mensaje en la carpeta C:\TestLocation\OtherNotification.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  
  
## <a name="performing-complex-operations-after-receiving-notification-messages"></a>Realizar operaciones complejas después de recibir mensajes de notificación  
 Para mayor simplicidad y una mejor comprensión, la orquestación en este tema copia mensajes en carpetas diferentes en función del tipo de notificación. Sin embargo, en situaciones del mundo real puede realizar operaciones más complejas. Puede realizar procesos similares como se indica en este tema y la compilación en ellos para realizar las operaciones que desee. Por ejemplo, puede cambiar la orquestación para insertar registros en otra tabla si recibe un mensaje de notificación para una operación de inserción en la tabla ACCOUNTACTIVITY. En tal caso, puede hacer los cambios correspondientes dentro de la forma decidir.  
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de cambio de base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)