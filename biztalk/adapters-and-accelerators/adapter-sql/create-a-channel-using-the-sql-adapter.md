---
title: Crear un canal con el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e86398f6-c835-46f8-814f-31e43b18970e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c31146310b8c8b559fcd93d19362679b060cb42
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962810"
---
# <a name="create-a-channel-using-the-sql-adapter"></a>Crear un canal con el adaptador de SQL
En el modelo de canal WCF, invocar las operaciones en la base de datos de SQL Server y recibir los resultados mediante el intercambio de mensajes SOAP con el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] sobre un canal WCF.  
  
-   Invocar operaciones de salida utilizando un **IRequestChannel** o un **IOutputChannel** para enviar mensajes al adaptador.  
  
-   Recibir mensajes para operaciones de entrada por recibir mensajes a través de un **IInputChannel** para **sondeo**, **TypedPolling**, o **notificación** operaciones.  
  
 Los procedimientos descritos en este tema proporcionan información acerca de cómo crear y configurar formas del canal que se utilizan para las operaciones de entrada y salidas.  
  
## <a name="creating-outbound-client-channels"></a>Crear los canales de salida (cliente)  
 Puede usar un **IRequestChannel** o un **IOutputChannel** para invocar operaciones en la base de datos de SQL Server. En cualquier caso, cree primero un **System.ServiceModel.ChannelFactory** mediante la interfaz adecuada. A continuación, utilice el generador para crear el canal. Después de haber creado el canal se puede usar para invocar operaciones en el adaptador.  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>Para crear y abrir un canal de salida  
  
1.  Crear e inicializar una instancia de **ChannelFactory** para la forma del canal deseado mediante un punto de conexión y un enlace. El punto de conexión especifica un URI de conexión de SQL Server y el enlace es una instancia de **sqlBinding**.  
  
2.  Proporcionar credenciales de SQL Server para el generador de canales mediante la **credenciales** propiedad.  
  
3.  Abra el generador de canales.  
  
4.  Obtener una instancia del canal invocando la **CreateChannel** método en el generador de canales.  
  
5.  Abrir el canal.  
  
 Puede especificar la dirección de enlace y el punto de conexión en el código o de configuración.  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>Especificar el enlace y la dirección del extremo en el código  
 En el ejemplo de código siguiente se muestra cómo crear un **IRequestChannel** especificando la dirección de enlace y el punto de conexión en el código. El código para crear un **IOutputChannel** es el mismo, salvo que debe especificar un **IOutputChannel** interfaz para la **ChannelFactory** y tipo de canal.  
  
```  
// Create binding -- set binding properties before you open the factory.  
SqlAdapterBinding sdbBinding = new SqlAdapterBinding();  
  
// Create address.  
EndpointAddress sdbAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(sdbBinding, sdbAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a>Especificar el enlace y la dirección del extremo en la configuración  
 En el ejemplo de código siguiente se muestra cómo crear un generador de canales de un punto de conexión de cliente especificado en la configuración.  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a>Los valores de configuración  
 El código siguiente muestra los valores de configuración que se usa para el ejemplo anterior. El contrato para el extremo de cliente debe ser "System.ServiceModel.Channels.IRequestChannel" o "System.ServiceModel.Channels.IOutputChannel" según el tipo de forma del canal que se va a crear.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <sqlBinding>  
                <binding name="SqlAdapterBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" maxConnectionPoolSize="100"  
                    encrypt="false" useAmbientTransaction="true" batchSize="20"  
                    polledDataAvailableStatement="" pollingStatement="" pollingIntervalInSeconds="30"  
                    pollWhileDataFound="false" notificationStatement="" notifyOnListenerStart="true"  
                    enableBizTalkCompatibilityMode="true" chunkSize="4194304"  
                    inboundOperationType="Polling" useDatabaseNameInXsdNamespace="false"  
                    allowIdentityInsert="false" enablePerformanceCounters="false"  
                    xmlStoredProcedureRootNodeName="" xmlStoredProcedureRootNodeNamespace="" />  
            </sqlBinding>  
        </bindings>  
        <client>  
            <endpoint address="mssql://mysqlserver//mydatabase?" binding="sqlBinding"  
                bindingConfiguration="SqlAdapterBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="creating-inbound-service-channels"></a>Crear los canales de entrada (servicio)  
 Configurar la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear las vistas y tablas de base de datos de SQL Server mediante el establecimiento de propiedades de enlace en una instancia de **sqlBinding**. A continuación, utilice este enlace para compilar un agente de escucha de canal desde el que se puede obtener un **IInputChannel** canal para recibir la **sondeo**, **TypedPolling**, o  **Notificación** operación desde el adaptador.  
  
#### <a name="to-create-and-open-an-iinputchannel-to-receive-inbound-operations"></a>Para crear y abrir un IInputChannel para recibir operaciones entrantes  
  
1.  Cree una instancia de **SQLBinding**.  
  
2.  Establecer las propiedades de enlace necesarias para la operación de entrada. Por ejemplo, para un **sondeo** operación, como mínimo, debe establecer el **InboundOperationType**, **PolledDataAvailableStatement**, y  **PollingStatement** enlace Propiedades para configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear la base de datos de SQL Server.  
  
3.  Crear un agente de escucha de canal invocando **BuildChannelListener\<IInputChannel\>**  método en el **SQLBinding**. Especifique el URI de conexión de SQL Server como uno de los parámetros a este método.  
  
4.  Abra el agente de escucha.  
  
5.  Obtener un **IInputChannel** canal invocando la **AcceptChannel** método en el agente de escucha.  
  
6.  Abrir el canal.  
  
 El código siguiente muestra cómo crear un agente de escucha de canal y obtener un **IInputChannel** para recibir mensajes de cambio de datos desde el adaptador.  
  
> [!IMPORTANT]
>  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] de recepción unidireccional solo admite. Por lo tanto, debe usar **IInputChannel** para recibir mensajes para operaciones de entrada de SQL Server.  
  
```  
// Create a binding: specify the InboundOperationType, the PolledDataAvailableStatement, and   
// the PollingStatement binding properties.  
SqlAdapterBinding binding = new SqlAdapterBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "myuser";  
credentials.UserName.Password = "mypassword";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
IInputChannel channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de canal WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)