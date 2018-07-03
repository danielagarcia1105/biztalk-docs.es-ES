---
title: Procesar mensajes de notificación para completar tareas específicas en SQL BizTalk Server, con | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8538cb89-1cca-45ad-b6f4-041e117963ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34e8cf9c1453b7a40f749e091d7ecdcef843d4e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000533"
---
# <a name="process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk-server"></a>Procesar los mensajes de notificación para completar tareas específicas en SQL con BizTalk Server
Puede usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir notificaciones de los cambios en tablas de base de datos de SQL Server. Sin embargo, el adaptador sólo le envía una notificación que algunos registros se inserta, actualiza o elimina en una tabla de base de datos determinados. Cualquier procesamiento posterior en esos registros debe controlarse las propias aplicaciones cliente. Este tema presenta una descripción basada en escenario sobre cómo procesar los registros en la tabla según el tipo de notificación recibida de la base de datos de SQL Server.  
  
## <a name="scenarios-for-performing-subsequent-actions-after-receiving-notification"></a>Escenarios para llevar a cabo las acciones posteriores tras recibir la notificación  
 Estos son algunos escenarios en los que los clientes del adaptador deben realizar determinadas tareas posteriores a la notificación.  
  
-   **Escenario 1**. Considere un escenario donde el cliente del adaptador debe realizar determinadas tareas según el tipo de notificación que se recibe desde SQL Server. Por ejemplo, la aplicación cliente debe actualizar los registros de la tabla "A" si se insertan registros en la tabla "B". De forma similar, la aplicación cliente debe eliminar los registros de la tabla "A" si se eliminan registros de la tabla "B".  
  
     En este escenario, desde el mensaje de notificación que recibe, los clientes del adaptador deben extraer el tipo de notificación para decidir si la notificación era durante una operación de inserción o una operación de eliminación. Una vez que se determina el tipo de notificación, los clientes del adaptador deben realizar las acciones posteriores para insertar o actualizar las tablas pertinentes.  
  
-   **Escenario 2**. Considere un escenario donde la ubicación de recepción que recibe los mensajes de notificación de cambios en una tabla deja de funcionar. Mientras que la ubicación de recepción está inactivo, algunos registros se agregan a la tabla. Sin embargo, para estos registros del cliente del adaptador no recibirá ninguna notificación. Cuando la ubicación de recepción es copia de seguridad, el adaptador notifica al cliente mediante el envío de un mensaje concreto y, a continuación, la aplicación cliente debe buscar todos los registros que se insertaron en la tabla de base de datos, mientras que la ubicación de recepción estaba inactivo.  
  
     En este escenario, desde el mensaje de notificación que recibe, los clientes del adaptador deben extraer la información relativa a si la notificación es para un cambio en una tabla de base de datos o para el inicio de la ubicación de recepción. Si la notificación es para el inicio de la ubicación de recepción, los clientes del adaptador deben implementar la lógica para procesar los registros que es posible que se han insertado, actualizados o puede eliminar mientras la ubicación de recepción estaba inactivo.  
  
> [!NOTE]
>  Estos son solo algunos escenarios de ejemplo que se enumeran para una mejor comprensión de cómo usar la característica de notificación en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Sin embargo, el conjunto básico de las tareas necesarias para extraer el tipo de notificación recibida será similar para todos los escenarios. Este tema proporciona instrucciones sobre cómo extraer el tipo de notificación de un mensaje de notificación.  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages-and-extracting-notification-type"></a>Cómo en este tema se muestra cómo recibir mensajes de notificación y extraer el tipo de notificación  
 En este tema, para demostrar cómo procesar mensajes de notificación para realizar las tareas siguientes, se considere un escenario básico donde un cliente de adaptador utiliza la aplicación de BizTalk para recibir mensajes de notificación de cambios en la tabla Employee. Después de recibe la notificación, el cliente filtra el tipo de notificación recibida y realiza la acción posterior. Para demostrar un escenario muy básico, centrémonos en la que el cliente de adaptador copia los mensajes de notificación en carpetas diferentes en función del tipo de notificación recibida. Por lo que:  
  
- Si el mensaje de notificación es para una operación Insert o Update, el cliente de adaptador copia el mensaje en la carpeta C:\TestLocation\UpsertNotification.  
  
- Si el mensaje de notificación es para cualquier otra operación, por ejemplo eliminar, el cliente de adaptador copia el mensaje en la carpeta C:\TestLocation\OtherNotificaiton.  
  
  Para lograr esto como parte de una aplicación de BizTalk, la orquestación debe contener lo siguiente:  
  
- Puerto para recibir mensajes de notificación de recepción unidireccional.  
  
- Una forma de expresión que contiene una consulta xpath para extraer la información sobre el tipo de mensaje de notificación recibido.  
  
- Una forma decidir debe incluir un bloque de decisiones en la orquestación. En este bloque de decisiones, decide qué para realizar las operaciones posteriores según el mensaje de notificación que recibe la aplicación.  
  
- Unidireccional dos puertos de envío que, por último, reciben los mensajes de notificación.  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a>Configuración de notificaciones con el adaptador SQL, las propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades de enlace que se utiliza para configurar la recepción de notificaciones de SQL Server. Debe especificar estas propiedades de enlace al configurar el puerto de recepción en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!NOTE]
>  Puede especificar estas propiedades de enlace al generar el esquema para el **notificación** operación, incluso aunque no es obligatorio. Si lo hace, el enlace de puerto de archivos que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera como parte de la generación de metadatos también contiene los valores especificados para las propiedades de enlace. Más adelante puede importar este archivo de enlace en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puerto de recepción de la consola de administración para crear el WCF-custom o WCF-SQL con el enlace de propiedades ya establecidas. Para obtener más información acerca de cómo crear un puerto mediante el archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).  
  
|Propiedad de enlace|Descripción|  
|----------------------|-----------------|  
|**InboundOperationType**|Especifica la operación de entrada que desea realizar. Para recibir mensajes de notificación, establezca esta opción en **notificación**.|  
|**NotificationStatement**|Especifica la instrucción SQL (SELECT o EXEC \<procedimiento almacenado\>) usa para registrar las notificaciones de consulta. El adaptador obtiene un mensaje de notificación de SQL Server solo cuando el conjunto de resultados para que los cambios de instrucción SQL especificados.|  
|**NotifyOnListenerStart**|Especifica si en el adaptador envía una notificación a los clientes del adaptador cuando se inicia el agente de escucha.|  
  
 Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir notificaciones de SQL Server, siga leyendo.  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a>Cómo recibir mensajes de notificación de la base de datos SQL Server  
 Realizar una operación en la base de datos de SQL Server mediante [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] conlleva las tareas de procedimientos se describe en [bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md). Para configurar el adaptador para recibir mensajes de notificación, estas tareas son:  
  
1. Crear un proyecto de BizTalk y, a continuación, genere el esquema para el **notificación** operación entrante. Si lo desea, puede especificar valores para el **InboundOperationType** y **NotificationStatement** propiedades de enlace.  
  
2. Cree un mensaje en el proyecto de BizTalk para recibir notificaciones de la base de datos de SQL Server.  
  
3. Crear una orquestación como se describe en la sección anterior.  
  
4. Compile e implemente el proyecto de BizTalk.  
  
5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
   > [!NOTE]
   >  Para las operaciones de entrada, como recibir mensajes de notificación, sólo debe configurar un unidireccional WCF-Custom o puerto de recepción WCF-SQL. Puertos de recepción bidireccional WCF-Custom o WCF-SQL no se admiten operaciones de entrada.  
  
6. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generating-schema"></a>Generar el esquema  
 Debe generar el esquema para el **notificación** operación entrante. Consulte [recuperación de metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para obtener más información acerca de cómo generar el esquema. Realice las tareas siguientes al generar el esquema. Omitir el primer paso si no desea especificar las propiedades de enlace en tiempo de diseño.  
  
1.  Especifique un valor para **InboundOperationType** y **NotificationStatement** al generar el esquema de propiedades de enlace. Para obtener más información acerca de esta propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener instrucciones sobre cómo especificar las propiedades de enlace, consulte [configurar las propiedades de enlace del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).  
  
2.  Seleccione el tipo de contrato **(operaciones de entrada) de servicio**.  
  
3.  Genere el esquema para el **notificación** operación.  
  
## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Una vez que se genera el esquema, debe vincularlo a los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 Este tema, debe crear un mensaje para recibir notificaciones de la base de datos de SQL Server.  
  
 Realice los pasos siguientes para crear mensajes y vincularlos a esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo `NotifyReceive`.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *Process_Notification.Notification*, donde *Process_Notification* es el nombre de su proyecto de BizTalk. *Notificación* es el esquema generado para el **notificación** operación.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes de notificación de la base de datos de SQL Server y, a continuación, realizar tareas en función del tipo de notificación recibida. En esta orquestación, el adaptador recibe el mensaje de notificación basado en la instrucción SELECT especificada para el **NotificationStatement** enlaza la propiedad. La consulta xpath especificada dentro de la forma de expresión extrae el tipo de notificación en una variable, por ejemplo **NotificationType**. La forma decidir utiliza el valor de esta variable para decidir cuál es el tipo de notificación recibida y toma la "ruta de acceso adecuada" para realizar las operaciones posteriores. Como se mencionó en la sección anterior, llevará a cabo las siguientes operaciones según el tipo de mensaje de notificación que recibe la orquestación.  
  
- Si el mensaje de notificación es para una operación Insert o Update, el cliente de adaptador copia el mensaje en la carpeta C:\TestLocation\UpsertNotification.  
  
- Si el mensaje de notificación es para cualquier otra operación, por ejemplo eliminar, el cliente de adaptador copia el mensaje en la carpeta C:\TestLocation\OtherNotificaiton.  
  
  Por lo tanto, la orquestación debe contener lo siguiente:  
  
- Puerto para recibir mensajes de notificación de recepción unidireccional.  
  
- Una forma de expresión que contiene una consulta xpath para extraer el tipo de notificación recibida.  
  
- Una forma decidir debe incluir un bloque de decisiones en la orquestación. En este bloque de decisiones, decide qué para realizar las operaciones posteriores según el mensaje de notificación que recibe la aplicación.  
  
- Unidireccional dos puertos de envío que, por último, reciben los mensajes de notificación.  
  
- Forma recepción.  
  
  Una orquestación de ejemplo es similar al siguiente.  
  
  ![Orquestación para realizar la publicación&#45;tareas de notificación](../../adapters-and-accelerators/adapter-sql/media/20f62716-603d-4293-84f7-8c8f6d82ccd0.gif "20f62716-603d-4293-84f7-8c8f6d82ccd0")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación simplemente mencionadas.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-Establecer **nombre** a *ReceiveNotification*<br /><br /> -Establecer **activar** a *True*|  
  
### <a name="adding-an-expression-shape"></a>Agregar una forma de expresión  
 El propósito de inclusión de una forma expresión en la orquestación es que una consulta xpath para extraer el tipo de mensaje de notificación recibido. Antes de crear una consulta xpath, examinemos el formato de un mensaje de notificación. Un mensaje de notificación típica se parece a lo siguiente:  
  
```  
<Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
  <Info>Insert</Info>   
  <Source>Data</Source>   
  <Type>Change</Type>   
</Notification>  
```  
  
 Como ve, la información sobre el tipo de la notificación está disponible dentro de la `<info>` etiqueta dentro del elemento primario `<Notification>` etiqueta. Por lo tanto, como parte de esta forma de expresión, debe:  
  
-   Cree una variable que contiene el valor dentro de la `<Info>` etiqueta y establezca su tipo en el objeto System.String. Para obtener más información acerca de cómo crear variables, consulte [utilizar Variables en orquestaciones](../../core/using-variables-in-orchestrations.md).
  
     Este tema, denomine a la variable **NotificationType**.  
  
-   Crear una consulta xpath para extraer el valor de la \<información\> etiqueta. La consulta xpath será similar al siguiente:  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     En esta consulta xpath, **NotifyReceive** es el mensaje que ha creado para recibir mensajes de notificación. El extracto dentro de la `string` función indica que la consulta debe extraer el valor dentro de la `<Info>` etiqueta, que a su vez está dentro de la `<Notification>` etiqueta. Por último, el valor extraído por la consulta se asigna a la **NotificaitonType** variable.  
  
### <a name="adding-a-decide-shape"></a>Agregar una forma decidir  
 Es el fin de agregar una forma decidir debe incluir un bloque de decisiones en la orquestación para decidir qué para realizar las operaciones siguientes en función del tipo de mensaje de notificación recibido. La Decisión se toma en función del valor de la **NotificationType** variable. En este tema, la orquestación toma una decisión en función del tipo de mensaje de notificación recibido. Por lo tanto, la condición en la forma de regla se especifica como sigue:  
  
```  
NotificationType.Equals("Insert") | NotificationType.Equals("Update")  
```  
  
 Esta condición sugiere que if el valor de **NotificaitonType** variable es Insert o Update, la orquestación llevará a cabo un conjunto de tareas. Si el valor de **NotificationType** variable es algo más, la orquestación llevará a cabo otro conjunto de tareas.  
  
 Como se mencionó en las secciones anteriores, para demostrar un enfoque simple, la orquestación copiará los mensajes en carpetas diferentes en función del tipo de mensaje de notificación. Es así, dentro de la regla y bloques de lo contrario, deberá agregar formas de envío para enviar los mensajes a distintos puertos. Este tema, asigne el nombre de la forma de envío en el bloque de regla como **SendUpsertNotification** y la forma de envío en el bloque Else como **SendOtherNotification**.  
  
### <a name="adding-ports"></a>Agregar puertos  
 Ahora debe agregar los siguientes puertos lógicos a la orquestación:  
  
- Unidireccional puerto de recepción para recibir mensajes de notificación de SQL Server.  
  
- Puerto de envío unidireccional para enviar mensajes de notificación para las operaciones Insert y Update en una carpeta específica.  
  
- Puerto de envío unidireccional para enviar mensajes de notificación para las demás operaciones en una carpeta específica.  
  
  Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna puerto son los nombres de los puertos tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|SQLNotifyPort|-Establecer **identificador** a *SQLNotifyPort*<br /><br /> -Establecer **tipo** a *SQLNotifyPortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *de recepción*|  
|NotificationUpsertPort|-Establecer **identificador** a *NotificationUpsertPort*<br /><br /> -Establecer **tipo** a *NotificationUpsertPortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*|  
|OtherNotificationPort|-Establecer **identificador** a *OtherNotificationPort*<br /><br /> -Establecer **tipo** a *OtherNotificationPortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especifique los mensajes para las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas Acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveNotification|-Establecer **mensaje** a *NotifyReceive*<br /><br /> -Establecer **operación** a *SQLNotifyPort.Notify.Request*|  
|SendUpsertNotification|-Establecer **mensaje** a *NotifyReceive*<br /><br /> -Establecer **operación** a *NotificationUpsertPort.Upsert.Request*|  
|SendOtherNotification|-Establecer **mensaje** a *seleccione*<br /><br /> -Establecer **operación** a *OtherNotificationPort.Other.Request*|  
  
 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  
  
 Ahora debe compilar la solución de BizTalk e implementarla en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).  
  
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para esta orquestación, debe:  
  
  - Definir un WCF-Custom físico o puerto de recepción unidireccionales de WCF-SQL. Este puerto de escucha de notificaciones que proceden de la base de datos de SQL Server. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico al adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md). Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  
  
    > [!IMPORTANT]
    >  No es necesario realizar este paso si especifica las propiedades de enlace en tiempo de diseño. En tal caso, puede crear un WCF-custom o WCF-SQL puerto de recepción, con el conjunto de propiedades de enlace necesaria, importando el archivo de enlace creado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).  
  
    |Propiedad de enlace|Valor|  
    |----------------------|-----------|  
    |**InboundOperationType**|Establezca esta opción en **notificación**.|  
    |**NotificationStatement**|Establezca esta opción en:<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **Nota:** específicamente debe especificar los nombres de columna en la instrucción como se muestra en la siguiente instrucción SELECT. Además, siempre debe especificar el nombre de tabla, junto con el nombre del esquema. Por ejemplo, `dbo.Employee`.|  
    |**NotifyOnListenerStart**|Establezca esta opción en **True**.|  
  
     Para obtener más información acerca de las propiedades de enlace diferente, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
    > [!NOTE]
    >  Se recomienda configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción al realizar operaciones de entrada mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Puede hacerlo agregando el servicio de puerto de recepción de comportamiento al configurar el WCF-Custom o WCF-SQL. Para obtener instrucciones sobre cómo agregar el comportamiento del servicio, consulte [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará los mensajes de notificación de la base de datos de SQL Server para las operaciones Insert y Update. Configurar este puerto para quitar mensajes de notificación a la carpeta C:\TestLocation\UpsertNotification.  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará los mensajes de notificación de la base de datos de SQL Server para todas las demás operaciones. Configurar este puerto para quitar mensajes de notificación a la carpeta C:\TestLocation\OtherNotification.  
  
## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para recibir mensajes de notificación de la base de datos de SQL Server y para realizar las operaciones subsiguientes de Select y Update. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta etapa, asegúrese de que:  
  
-   El WCF-Custom o WCF-SQL unidireccional puerto de recepción, que recibe los mensajes de notificación de SQL Server se está ejecutando la base de datos.  
  
-   Los dos puertos de envío de archivo, que recepción los mensajes de SQL Server, se están ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de iniciar la orquestación de BizTalk, el siguiente conjunto de acciones tienen lugar:  
  
-   Dado que el **NotifyOnListenerStart** enlaza la propiedad se establece en **True**, recibirá el mensaje siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>SqlBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta que el valor de la `<Info>` etiqueta es "ListnerStarted". Por lo tanto, este mensaje se recibe en la carpeta C:\TestLocation\OtherNotification.  
  
-   Insertar un registro en la tabla Employee. Recibirá un mensaje de notificación similar al siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta que el valor de la `<Info>` etiqueta es "Insert". Por lo tanto, este mensaje se recibe en la carpeta C:\TestLocation\UpsertNotification.  
  
-   Actualizar un registro en la tabla Employee. Recibirá un mensaje de notificación similar al siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta que el valor de la `<Info>` etiqueta es "Update". Por lo tanto, este mensaje se recibe en la carpeta C:\TestLocation\UpsertNotification.  
  
-   Elimina un registro de la tabla Employee. Recibirá un mensaje de notificación similar al siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Delete</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta que el valor de la `<Info>` etiqueta es "Eliminar". Por lo tanto, este mensaje se recibe en la carpeta C:\TestLocation\OtherNotification.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlace. Cuando genere un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío y recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar los enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="performing-complex-operations-after-receiving-notification-messages"></a>Realizar operaciones complejas después de recibir mensajes de notificación  
 Por simplicidad y una mejor comprensión, la orquestación en este tema copia los mensajes en carpetas diferentes en función del tipo de notificación. Sin embargo, en situaciones del mundo real es posible que desee realizar operaciones más complejas. Puede realizar procedimientos similares que se proporciona en este tema y la compilación en ellos para realizar las operaciones que desee. Por ejemplo, puede cambiar la orquestación para insertar registros en otra tabla si recibe un mensaje de notificación para una operación de inserción en la tabla Employee. En tal caso, puede hacer los cambios correspondientes dentro de la forma decidir.  
  
 Uno de estos escenarios se explica con detalle en [Tutorial 2: empleado: proceso de pedido de compra mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de consulta SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)