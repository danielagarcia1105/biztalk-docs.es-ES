---
title: Insertar, actualizar, eliminar o seleccionar las operaciones mediante BizTalk Server con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d411b1a-a36d-4e3e-a56a-91804a5d69b9
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f3e81cf843473a544b915d185e4609d0748fc2e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982029"
---
# <a name="insert-update-delete-or-select-operations-using-biztalk-server-with-the-sql-adapter"></a>Insertar, actualizar, eliminar o seleccionar las operaciones mediante BizTalk Server con el adaptador de SQL
La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone un conjunto de operaciones estándar en las vistas y tablas de base de datos de SQL Server. Se denominan operaciones (DML) de lenguaje de manipulación de datos. Mediante el uso de las operaciones DML, puede realizar Select simple de Insert, Update y eliminar operaciones en tablas y vistas. Para obtener más información sobre cómo el adaptador es compatible con estas operaciones, consulte [Insert, Update, Delete y seleccione las operaciones en tablas y vistas con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md). Para obtener información acerca de la estructura del mensaje SOAP para estas operaciones, vea [esquemas de mensaje para Insert, Update, Delete y seleccione las operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).  
  
> [!NOTE]
>  Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que se hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) antes de empezar a desarrollar su aplicación.  
  
## <a name="how-to-perform-basic-operations-on-a-sql-server-database"></a>Cómo realizar operaciones básicas en una base de datos SQL Server  
 Realizar una operación en una base de datos de SQL Server mediante el uso de [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md). Para llevar a cabo Insert, Update, Delete o las operaciones Select en las tablas y vistas en SQL Server, estas tareas son:  
  
1. Cree un proyecto de BizTalk y genere el esquema para la operación que desea que se invocará en una tabla de base de datos de SQL Server o la vista.  
  
2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de la base de datos de SQL Server.  
  
3. Crear una orquestación para invocar la operación en la tabla de base de datos de SQL Server o la vista.  
  
4. Compile e implemente el proyecto de BizTalk.  
  
5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, SelectTable, basado en este tema se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema se muestra cómo realizar operaciones DML básicas mediante la selección de registros de la tabla EMPLOYEE en la base de datos de SQL Server. Ejecute los scripts proporcionados con los ejemplos para crear la tabla de empleados. Para obtener más información acerca de los ejemplos, vea [ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).  
  
 Para demostrar cómo seleccionar los registros, se genera el esquema para la operación de selección para la tabla EMPLOYEE. Debe crear un proyecto de BizTalk y utilice el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Consulte [recuperación de metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para obtener más información acerca de cómo generar esquemas.  
  
> [!IMPORTANT]
>  Si va a generar los metadatos para operaciones en una tabla con columnas de tipos definidos por el usuario (UDT), asegúrese de que los ensamblados correspondientes de los UDT están disponibles en la misma ubicación que el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] ejecutable devenv.exe. El archivo ejecutable es suele estar disponible en `<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`. En este ejemplo, la tabla EMPLOYEE tiene una columna UDT (punto). Asegúrese de copiar el ensamblado correspondiente en la misma ubicación que el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] ejecutable.  
> 
>  Para obtener información sobre cómo crear un UDT, vea [crear un tipo definido por el usuario](https://msdn.microsoft.com/library/ms131106.aspx). Para obtener información sobre cómo registrar un UDT en SQL Server, vea [Registering User-Defined tipos en SQL Server](https://msdn.microsoft.com/library/eybzcxe6(v=vs.85).aspx).  
  
## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Normalmente, un mensaje es una variable cuyo tipo está definido por el esquema correspondiente. Ahora debe crear mensajes para la orquestación y vincularlos a los esquemas que generó en el paso anterior.  
  
1.  Agregar una orquestación al proyecto de BizTalk. Desde el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para el **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Request`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *SelectTable.TableOperation_dbo_Employee.Select*, donde SelectTable es el nombre de su proyecto de BizTalk. TableOperation_dbo_Employee es el esquema generado para la operación Select en la tabla EMPLOYEE.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Response`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *SelectTable.TableOperation_dbo_Employee.SelectResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para llevar a cabo una operación en SQL Server. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] consume este mensaje y lo pasa a SQL Server. La respuesta de SQL Server se guarda en otra ubicación. Debe incluir el envío y recepción de formas para enviar mensajes a SQL Server y recibir respuestas, respectivamente. Una orquestación de ejemplo para la operación de selección es similar al siguiente:  
  
 ![Orquestación para seleccionar operación en SQL Server](../../adapters-and-accelerators/adapter-sql/media/e74e342f-ba66-41fe-bd34-d45cd8767ef8.gif "e74e342f-ba66-41fe-bd34-d45cd8767ef8")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación simplemente mencionadas.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna puerto son los nombres de los puertos tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *MessageIn*<br />-Establecer **tipo** a *MessageInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|ResponseOut|-Establecer **identificador** a *ResponseOut*<br />-Establecer **tipo** a *ResponseOutType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especifique los mensajes para las formas Acción y conectarlos a puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas Acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.Select.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.Select.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.Select.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.Select.Request*|  
  
 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y la orquestación completada.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el panel orquestaciones, en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe usar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para esta orquestación, debe:  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a la base de datos de SQL Server.  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de SQL Server.  
  
  - Definir un puerto de envío físico de WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico al adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).
  
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).
  
## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para seleccionar registros de una tabla de base de datos de SQL Server. Para que conocer los pasos iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta etapa, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
> [!IMPORTANT]
>  Si va a realizar operaciones en una tabla con columnas de tipos definidos por el usuario (UDT), asegúrese de que los ensamblados correspondientes de los UDT están disponibles en la misma ubicación que el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ejecutable, btsntsvc.exe. El archivo ejecutable es suele estar disponible en `<installation drive>:\Program Files\Microsoft BizTalk Server <version>`. En este ejemplo, la tabla EMPLOYEE tiene una columna UDT (punto). Asegúrese de copiar el ensamblado correspondiente en la misma ubicación que el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ejecutable.  
> 
>  Para obtener información sobre cómo crear un UDT, vea [crear un tipo definido por el usuario](https://msdn.microsoft.com/library/ms131106.aspx). Para obtener información sobre cómo registrar un UDT en SQL Server, vea [Register User-Defined tipos en SQL Server](https://msdn.microsoft.com/library/ms131079.aspx).  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe cumplir el esquema para la operación de selección que ha generado anteriormente. Por ejemplo, el mensaje de solicitud para seleccionar todos los registros de la tabla de empleados es:  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>*</Columns>  
  <Query>where Employee_ID=10001</Query>  
</Select>  
```  
  
 Este mensaje de solicitud recuperará los registros de la tabla de empleados que satisfacen la condición especificada en el `<Query>` elemento. Si desea recuperar columnas específicas de la tabla, deberá especificarlos en el < columnas\> elemento, separado por comas, en la misma secuencia en que aparecen en la definición de tabla. Si no desea especificar una condición para recuperar datos, deje el `<Query>` elemento en blanco. Consulte [esquemas de mensaje para Insert, Update, Delete y seleccione las operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md) para obtener más información acerca del esquema de mensaje de solicitud para realizar operaciones básicas de DML en SQL Server database, tablas y vistas mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 La orquestación consume el mensaje y lo envía a la base de datos de SQL Server. La respuesta de la base de datos de SQL Server se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta de la base de datos de SQL Server para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<SelectResponse xmlns="mssql://Microsoft.LobServices.Sql/2008/01/TVOp/dbo/Employee">  
  <SelectResult>  
    <Employee xmlns="mssql://Microsoft.LobServices.Sql/2008/01/Types/Tables/dbo">  
      <Employee_ID>10001</Employee_ID>  
      <Name>John</Name>  
      <DOJ>1983-12-31T00:00:00Z</DOJ>  
      <Designation>Manager</Designation>  
      <Job_Description>Management</Job_Description>  
      <Photo>EjRVYzRFVQ==</Photo>  
      <Rating>1,2</Rating>  
      <Salary>100000.00</Salary>  
      <Last_Modified>AAAAAAAAD6I=</Last_Modified>  
    </Employee>  
  </SelectResult>  
</SelectResponse>  
```  
  
## <a name="best-practices"></a>Procedimientos recomendados  
  
-   Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlace. Cuando genere un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos como los puertos de envío y recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [enlaces del adaptador SQL reutilizar](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
-   Si va a insertar, actualizar, o asegúrese de eliminar grandes volúmenes de datos que se establecen los valores de tiempo de espera adecuado para el adaptador de WCF y de la transacción MSDTC. Para obtener más información, consulte el problema "el adaptador no puede insertar, actualizar o eliminar grandes volúmenes de datos en una sola operación mediante BizTalk Server" en [solucionar problemas de funcionamiento con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/troubleshoot-operational-issues-with-the-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)