---
title: Adaptador transaccional (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31a13377-cc89-4763-ad1b-508a16fc9708
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f934857103952a035159cc08678c8ce8c8e51a56
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "26009893"
---
# <a name="transactional-adapter-biztalk-server-sample"></a>Adaptador transaccional (ejemplo de BizTalk Server)
En el ejemplo de adaptador transaccional se muestra cómo crear y usar una transacción explícita de Microsoft DTC (Coordinador de transacciones distribuidas) para una base de datos durante el procesamiento de un mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo contiene un adaptador de recepción que ejecuta una instrucción SQL en un intervalo especificado por el usuario para obtener datos de una base de datos de SQL Server mediante una transacción de MSDTC. Los datos se envían posteriormente a la base de datos de cuadro de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en forma de mensaje en el contexto de la misma transacción.  
  
 El adaptador de envío correspondiente ejecuta un procedimiento almacenado de SQL especificado por el usuario y para ello utiliza los datos de un mensaje de BizTalk en el contexto de una transacción. Usa datos específicos de ese mensaje para encontrar el mensaje correspondiente y eliminarlo de la base de datos de cuadro de mensajes de la misma transacción.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 La solución de este ejemplo incluye dos proyectos. El primero es el proyecto administrativo (Admin) que se utiliza antes del tiempo de ejecución para permitir que un usuario configure las ubicaciones de recepción y los puertos de envío que usan el adaptador. El segundo es el proyecto de tiempo de ejecución (Runtime) que se ejecuta cuando los adaptadores de recepción y envío están en ejecución.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  
  
 \<*Ejemplos de ruta de acceso*\>\Samples\AdaptersDevelopment\TransactionalAdapter. El proyecto de configuración administrativa se encuentra en la carpeta \Admin, y el de tiempo de ejecución, en la carpeta \Runtime.  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Nombre del archivo del proyecto Admin|Descripción del archivo del proyecto Admin|  
|----------------------------|------------------------------------|  
|TransactionalAdmin.csproj|Archivo del proyecto administrativo del adaptador utilizado para la configuración anterior al tiempo de ejecución.|  
|TransactionalReceiveHandler.xsd|XSD de las propiedades del controlador de recepción.|  
|TransactionalReceiveLocation.xsd|XSD de las propiedades de la ubicación de recepción.|  
|TransactionalTransmitLocation.xsd|XSD de las propiedades de la ubicación de transmisión.|  
|TransactionalTransmitHandler.xsd|XSD de las propiedades del controlador de transmisión.|  
|TransactionalAdapterManagement.cs|Administración de la configuración del adaptador. Contiene GetConfigSchema, que invoca el marco de trabajo de adaptadores de BizTalk para devolver un esquema de configuración XSD para cada uno de los (cuatro) tipos posibles de configuración compatibles.|  
  
|Nombre del archivo del proyecto de tiempo de ejecución|Descripción del archivo del proyecto de tiempo de ejecución|  
|------------------------------|--------------------------------------|  
|Transactional.csproj|Archivo del proyecto de tiempo de ejecución del adaptador.|  
|TransactionalAsyncBatch.cs|Realiza la implementación asíncrona de la parte de envío del adaptador.|  
|TransactionalDeleteBatch.cs|Elimina un lote de mensajes y votos para confirmar o anular una transacción.|  
|TransactionalProperties.cs|Extrae y establece las propiedades de configuración.|  
|TransactionalReceiver.cs|Crea y administra los extremos de recepción.|  
|TransactionalReceiverEndpoint.cs|Realiza la escucha o sondeo real de cada una de las ubicaciones de recepción.|  
|TransactionalTransmitter.cs|Acepta un lote de mensajes del motor de mensajería que se va a transmitir.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 El propósito de este ejemplo es constituir un marco de trabajo que pueda utilizarse para la creación de adaptadores de recepción y envío personalizados mediante transacciones explícitas.  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
> [!IMPORTANT]
>  Si la instalación de BizTalk es de 64 bits o se modifica la ubicación de la instalación, OutboundAssemblyPath, InboundAssemblyPath y AdapterMgmtAssemblyPath deben cambiarse según corresponda.  
  
#### <a name="create-a-strong-name-key-for-the-transactional-adapter-sample"></a>Crear una clave de nombre seguro para el ejemplo de adaptador transaccional  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
2.  En el símbolo del sistema, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
    ```  
    cd \Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Runtime  
    ```  
  
3.  En el símbolo del sistema, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
    ```  
    sn –k TransactionalAdapter.snk  
    ```  
  
4.  En el símbolo del sistema, escriba **salir**, y, a continuación, presione ENTRAR para cerrar la ventana de símbolo del sistema.  
  
#### <a name="build-the-transactional-adapter-solution"></a>Compile la solución de adaptador transaccional  
  
1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.  
  
2.  Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter y haga doble clic en **TransactionalAdapter.sln** para abrir esta solución en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
3.  Para compilar tanto de los proyectos de adaptador transaccional (Admin y Runtime) en el Explorador de soluciones, haga clic en **solución TransactionalAdapter**y, a continuación, haga clic en **volver a generar**.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="register-the-transactional-adapter"></a>Registrar el adaptador transaccional  
  
1.  En el Explorador de Windows, vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Admin.  
  
2.  Para agregar los datos del adaptador transaccional al registro, haga doble clic en **TransactionalAdmin.reg**.  
  
    > [!NOTE]
    >  **TransactionalAdmin.reg** incluye rutas codificadas de forma rígida a C:\Program Files\Microsoft BizTalk Server\\. Si no instaló BizTalk Server en la ubicación predeterminada o si actualizó la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a partir de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], deberá modificar el archivo TransactionalAdmin.reg con las rutas apropiadas. Actualice las rutas asociadas a los valores "InboundAssemblyPath", "OutboundAssemblyPath" y "AdapterMgmtAssemblyPath" para que señalen a la ubicación correcta de los archivos especificados.  
  
    > [!IMPORTANT]
    >  Si instala BizTalk en un equipo de 64 bits, cambie todas las instancias de la entrada de registro HKEY_CLASSES_ROOT\CLSID\ a HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ en el **TransactionalAdmin.reg** archivo de registro.  
  
3.  En el **Editor del registro** cuadro de diálogo, haga clic en **Sí** para agregar el adaptador de ejemplo en el registro y, a continuación, haga clic en **Aceptar**.  
  
4.  Para cerrar el Explorador de Windows, haga clic en **archivo**y, a continuación, haga clic en **cerrar**.  
  
#### <a name="add-the-transactional-adapter-to-biztalk-server"></a>Agregar el adaptador transaccional a BizTalk Server  
  
1.  Haga clic en el **iniciar** menú, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, seleccione **administración de BizTalk Server**.  
  
2.  En el [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda la **administración de BizTalk Server** de árbol, expanda el **grupo de BizTalk** del árbol y, a continuación, expanda el **configuración de plataforma** árbol.  
  
3.  Haga clic en **adaptadores**, haga clic en **New**y, a continuación, haga clic en **adaptador**.  
  
4.  En el **propiedades del adaptador** diálogo cuadro, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Nombre|Tipo de **TransactionalAdapter**.|  
    |Adaptador|Seleccione **Txn** en la lista desplegable. Esta entrada aparece como resultado de ejecutar el **TransactionalAdmin.reg** archivo anteriormente.|  
    |Description|Tipo de **adaptador transaccional de ejemplo**.|  
  
5.  Haga clic en **Aceptar.** El adaptador aparece en la lista de adaptadores de la ventana derecha de la consola de administración de BizTalk Server.  
  
#### <a name="create-a-receive-port-and-location-that-uses-the-adapter"></a>Crear un puerto y una ubicación de recepción que utilicen el adaptador  
  
1.  Expanda el **grupo de BizTalk [nombre del servidor]** nodo [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **aplicaciones** nodo, expanda **BizTalk Application 1** nodo.  
  
2.  Haga clic en **puertos de recepción**y, a continuación, haga clic en **New**, seleccione **puerto de recepción unidireccional.**  
  
3.  Para **nombre**, escriba **TxnReceivePort1**y, a continuación, haga clic en **Aceptar**.  
  
4.  Haga clic en el **ubicaciones de recepción** nodo, haga clic en **New**y, a continuación, seleccione **ubicación de recepción unidireccional**.  
  
5.  En el**seleccionar un puerto de recepción** cuadro de diálogo, seleccione **TxnReceivePort1**y, a continuación, haga clic en **Aceptar**.  
  
6.  En el **propiedades de ubicación de recepción** cuadro de diálogo, en la **General** , escriba **TxnReceiveLocation1** para **nombre**. Asegúrese del **puerto de recepción** etiqueta muestra **TxnReceivePort1**.  
  
7.  En el**tipo** cuadro de lista desplegable en el **transporte** marco, seleccione **TransactionalAdapter.**  
  
8.  En el **recepción *** canalización** cuadro, asegúrese de **PassThruReceive** está seleccionada. Deje el resto de las propiedades con los valores de configuración predeterminados.  
  
9. Haga clic en el **configurar** situado junto a la **tipo** cuadro de lista desplegable. Con ello, se muestra un cuadro de diálogo específico para este adaptador. Especifique lo siguiente según sea necesario, a continuación, haga clic en **Aceptar**.  
  
    |Propiedad|Configuración|  
    |--------------|-------------|  
    |Cadena de conexión|La cadena de conexión de base de datos de SQL utilizada para efectuar la conexión con la base de datos Northwind y la autenticación correspondiente. Posteriormente, se ejecutará un script de SQL que usará esta base de datos.|  
    |Texto de comando|Las instrucciones SQL que se ejecutan para la base de datos Northwind para obtener datos que se colocarán en el mensaje de BizTalk.|  
    |Cookie|Forma parte del URI, por lo que es preciso especificar un valor único, como el nombre de la ubicación de recepción; por ejemplo: TxnReceiveLocation1.|  
    |Unidad de intervalo de sondeo|El número de unidades de medida de tiempo para el sondeo de los datos. Establezca este valor como segundos.|  
    |Intervalo de sondeo|La unidad de medida de tiempo para el sondeo de los datos. Establezca este valor como 15 segundos.|  
  
10. Haga clic en **Aceptar** para cerrar el cuadro de diálogo Configurar, a continuación, **Aceptar** otra vez para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo para volver a la [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  
  
#### <a name="create-a-send-port-and-send-handler-that-use-the-adapter"></a>Crear un puerto y un controlador de envío que utilicen el adaptador  
  
1.  Con el **BizTalk Application 1** nodo expandido, haga clic en **puertos de envío**y, a continuación, haga clic en **New**y seleccione **enviar Puerto unidireccional**.  
  
2.  En el **nombre** , escriba **TxnSendPort1**.  
  
3.  En el **transporte** marco, en la **tipo** lista desplegable, seleccione**TransactionalAdapter**`.`  
  
4.  En el **canalización de envío** cuadro, asegúrese de **PassThruTransmit** está seleccionada.  
  
5.  Haga clic en el **configurar** situado junto a la **transporte** lista desplegable. En el cuadro de diálogo que aparece, especifique lo siguiente según sea necesario, a continuación, haga clic en **Aceptar**.  
  
    |Propiedad|Configuración|  
    |--------------|-------------|  
    |Cookie|Forma parte del URI: especificar un valor único, como el nombre de la ubicación de recepción, por ejemplo: **TxnSendPort1**.|  
    |Cadena de conexión|La cadena de conexión de base de datos de SQL utilizada para efectuar la conexión con la base de datos Northwind y la autenticación correspondiente. Lo más probable es que sea el mismo que se utiliza para configurar el **TxnReceiveLocation1** ubicación de recepción.|  
    |Procedimiento almacenado|El nombre del procedimiento almacenado que se ejecuta para sondear la base de datos - **sp_txnProc**. El cuerpo del mensaje se entrega a la que BizTalk el procedimiento almacenado como un parámetro de cadena denominado @Data. Por ejemplo, el usuario en este caso más adelante configurará el procedimiento almacenado con el nombre **sp_txnProc**. El tiempo de ejecución del adaptador ejecutará el equivalente de esta llamada en la base de datos.<br /><br /> exec sp_txnProc @Data = "el contenido del mensaje de BizTalk"|  
  
6.  En el panel de navegación izquierdo, haga clic en **filtro**.  
  
7.  En el editor de expresiones de filtro, especifique la siguiente expresión con el fin de configurar una suscripción para este puerto de envío de modo que pueda recibir cualquier mensaje que reciba el puerto de recepción TxnReceivePort1.  
  
     Especifique estos valores:**BTS. ReceivePortName == TxnReceivePort1**  
  
    1.  `(property)`  **BTS.ReceivePortName**  
  
    2.  `(operator)`  **==**  
  
    3.  `(value)`  **TxnReceivePort1**  
  
8.  Use los valores predeterminados para el resto de las propiedades del adaptador y seleccione **Aceptar**.  
  
## <a name="run-the-sample"></a>Ejecutar el ejemplo  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**, seleccione **SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** diálogo cuadro, asegúrese de que **tipo de servidor** está establecido en **motor de base de datos**y escriba las credenciales para autenticarse en el servidor de base de datos, a continuación, seleccione  **Conectar**.  
  
3.  Seleccione el **nueva consulta** botón de barra de herramientas y pegue lo siguiente en la nueva ventana de consulta para insertar una tabla de prueba, datos de prueba y una prueba de procedimiento almacenan en la base de datos Northwind. Seleccione el **Execute** botón de barra de herramientas.  
  
    ```  
    use [Northwind]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[scratch]') and OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    drop table [dbo].[scratch]  
    GO  
    CREATE TABLE [dbo].[scratch] (  
         [id] [int] IDENTITY (1, 1) NOT NULL ,  
         [msg] [nvarchar] (4000) NOT NULL   
    ) ON [PRIMARY]  
    GO  
    GRANT SELECT , UPDATE , INSERT ON [dbo].[scratch] TO [public]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[sp_txnProc]') and OBJECTPROPERTY(id, N'IsProcedure') = 1)  
    drop procedure [dbo].[sp_txnProc]  
    GO  
    CREATE PROCEDURE [dbo].[sp_txnProc] @Data nvarchar (4000)  
    AS   
    INSERT scratch ( msg ) values ( @Data )  
    GO  
    GRANT EXECUTE ON [dbo].[sp_txnProc] TO [public]  
    GO  
    ```  
  
4.  En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda la **puertos de envío** nodo, seleccione el **TxnSendPort1** puerto de envío y seleccione **iniciar**.  
  
5.  En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda la **ReceiveLocations** nodo, seleccione el **TxnRecieveLocation1** ubicación de recepción y, a continuación, seleccione **habilitar**.  
  
6.  Una vez habilitada la ubicación de recepción, se efectuará automáticamente un sondeo de los datos de la base de datos en los intervalos designados.  
  
## <a name="classes-or-methods-used-in-the-sample"></a>Las clases o métodos utilizados en el ejemplo  
* IBTTransmitterBatch (interfaz) (COM)
  
* IBTTransportProxy (interfaz) (COM)

Estos métodos se describen [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptador: desarrollo](../core/adapter-samples-development.md)   
 [Registro de un adaptador](../core/registering-an-adapter.md)