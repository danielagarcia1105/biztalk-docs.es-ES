---
title: Invocar funciones escalares en SQL Server mediante BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70bb7be9-ae31-4505-9406-f9d4744b65e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa7ad0d193f3445fd751c7893277588348342802
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979053"
---
# <a name="invoke-scalar-functions-in-sql-server-using-biztalk-server"></a>Invocar funciones escalares en SQL Server mediante BizTalk Server
Puede usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para invocar funciones escalares en SQL Server. El adaptador expone las funciones escalares como operaciones que se pueden invocar directamente en SQL Server. Para obtener más información acerca de cómo el adaptador admite funciones escalares, vea [ejecutar funciones escalares en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md). Para obtener información acerca de la estructura del mensaje SOAP para invocar funciones escalares, vea [esquemas de mensaje para procedimientos y funciones](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
- Crear un [clave de nombre seguro de archivos y obtenga información sobre las herramientas](prerequisites-to-create-sql-applications-using-the-sql-adapter.md)
  
- [Configurar MSDTC](configure-msdtc-on-sql-server-and-adapter-client.md) en equipos que ejecutan el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y SQL Server.
  
## <a name="invoke-scalar-functions-on-sql-server-database"></a>Invocar funciones escalares en la base de datos SQL Server  
 Realizar una operación en la base de datos de SQL Server mediante el uso de [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md). Para invocar funciones escalares en SQL Server, estas tareas son:  
  
1. Cree un proyecto de BizTalk y genere el esquema para la función escalar que desea invocar en SQL Server.  
  
2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de SQL Server.  
  
3. Crear una orquestación para invocar la operación en SQL Server.  
  
4. Compile e implemente el proyecto de BizTalk.  
  
5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generate-schema"></a>Generar el esquema  
 En este tema se muestra cómo invocar funciones escalares en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para demostrar esta operación, en este tema se ejecuta la función GET_EMP_ID. Esta función toma la designación de un empleado como parámetro y devuelve el identificador de empleado de la tabla EMPLOYEE. En la tabla y la función se crean mediante la ejecución de los scripts proporcionados con los ejemplos. Para obtener más información acerca de la secuencia de comandos, consulte [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).  
  
 Para demostrar cómo invocar funciones escalares, se genera el esquema para la función escalar GET_EMP_ID. Debe crear un proyecto de BizTalk y utilice el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Consulte [recuperación de metadatos para operaciones de SQL Server en Visual Studio](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para obtener más información acerca de cómo generar esquemas.  
  
## <a name="define-messages-and-message-types"></a>Definir los mensajes y el mensaje de tipos  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Ahora, crear mensajes para la orquestación y vincularlos a los esquemas que generó en el paso anterior.    
 
1.  Agregar una orquestación al proyecto de BizTalk. Desde el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para el **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Request`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *ScalarFunction.ScalarFunction_dbo. GET_EMP_ID*, donde ScalarFunction es el nombre de su proyecto de BizTalk. ScalarFunction_dbo es el esquema generado para la función GET_EMP_ID.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Response`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *ScalarFunction.ScalarFunction_dbo. GET_EMP_IDResponse*.|  
  
## <a name="set-up-the-orchestration"></a>Configurar la orquestación  
 Crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para llevar a cabo una operación en SQL Server. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] consume este mensaje y lo pasa a SQL Server. La respuesta de SQL Server se guarda en otra ubicación. Debe incluir el envío y recepción de formas para enviar mensajes a SQL Server y recibir respuestas, respectivamente. Una orquestación para invocar una función escalar de ejemplo es similar al siguiente:  
  
 ![Orquestación para invocar funciones escalares](../../adapters-and-accelerators/adapter-sql/media/9f69c9b9-2466-46d5-8423-1ccdc37a93fb.gif "9f69c9b9-2466-46d5-8423-1ccdc37a93fb")  
  
### <a name="add-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación simplemente mencionadas.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="add-ports"></a>Agregar puertos  
 Especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna puerto son los nombres de los puertos tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *MessageIn*<br />-Establecer **tipo** a *MessageInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|ResponseOut|-Establecer **identificador** a *ResponseOut*<br />-Establecer **tipo** a *ResponseOutType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especifique los mensajes para las formas Acción y conectarlos a puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas Acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.ScalarFunction.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.ScalarFunction.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.ScalarFunction.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.ScalarFunction.Request*|  
  
 Después de escribir estas propiedades, están conectados a los puertos y formas de mensaje y la orquestación completada.  
  
 Ahora, compile la solución de BizTalk e implementarlo en BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configure-the-biztalk-application"></a>Configurar la aplicación de BizTalk  
 Después de implementar el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el panel orquestaciones, en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe usar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
   
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para esta orquestación, debe:  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a la base de datos de SQL Server.  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de SQL Server.  
  
  - Definir un puerto de envío físico de WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico al adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).
  
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).
  
## <a name="start-the-application"></a>Iniciar la aplicación  
 Inicie la aplicación de BizTalk para invocar funciones escalares de base de datos de SQL Server. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta etapa, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="execute-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe cumplir el esquema para la función GET_EMP_ID generado anteriormente. Por ejemplo, el mensaje de solicitud para invocar la función GET_EMP_ID es:  
  
```  
<GET_EMP_ID xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/dbo">  
  <emp_desig>Manager</emp_desig>  
</GET_EMP_ID>  
```  
  
 Este mensaje de solicitud invoca la función GET_EMP_ID para recuperar el identificador para los empleados con la designación "Administrador". Consulte [esquemas de mensaje para procedimientos y funciones](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md) para obtener más información sobre el esquema de mensaje de solicitud para invocar funciones escalares en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 La orquestación consume el mensaje y lo envía a la base de datos de SQL Server. La respuesta de la base de datos de SQL Server se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta de la base de datos de SQL Server para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<GET_EMP_IDResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/dbo">  
  <GET_EMP_IDResult>10072</GET_EMP_IDResult>  
</GET_EMP_IDResponse>  
```  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlace. Cuando genere un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos como los puertos de envío y recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar los enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)