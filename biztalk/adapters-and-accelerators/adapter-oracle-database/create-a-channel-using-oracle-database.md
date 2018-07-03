---
title: Crear un canal con la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating a channel
- WCF channel model, creating a channel
- how to, create a channel
- channel programming, creating a channel
ms.assetid: a30156a0-5a5a-4418-be17-2e23c3716fc1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18d3964cabfec2b1e33813e3811bfeb696cd4280
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972245"
---
# <a name="create-a-channel-using-oracle-database"></a>Crear un canal con la base de datos de Oracle
En el modelo de canal WCF, podrá invocar operaciones en la base de datos de Oracle y recibir los resultados de una consulta de sondeo mediante el intercambio de mensajes SOAP con el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] a través de un canal WCF.  
  
- Invocar operaciones (operaciones de salida) mediante el uso un **IRequestChannel** o un **IOutputChannel** para enviar mensajes al adaptador.  
  
- Recibir mensajes de cambio de datos basados en sondeos por recibir mensajes POLLINGSTMT a través de un **IInputChannel**.  
  
  Los temas de esta sección proporcionan información acerca de cómo crear y configurar las formas del canal que se usan para las operaciones de entrada y salidas.  
  
## <a name="creating-outbound-client-channels"></a>Crear canales salientes (cliente)  
 Puede usar un **IRequestChannel** o un **IOutputChannel** para invocar operaciones en la base de datos de Oracle. En cualquier caso, cree primero un **System.ServiceModel.ChannelFactory** mediante la interfaz adecuada. Utilizamos el generador para crear el canal. Después de haber creado el canal se puede usar para invocar operaciones en el adaptador.  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>Para crear y abrir un canal de salida  
  
1. Crear e inicializar una instancia de **ChannelFactory** para la forma del canal deseado mediante el uso de un punto de conexión y un enlace. El punto de conexión especifica un URI de conexión de Oracle y el enlace es una instancia de **OracleDBBinding**.  
  
2. Proporcionar credenciales de Oracle para el generador de canales mediante la **credenciales** propiedad.  
  
3. Abra el generador de canales.  
  
4. Obtener una instancia del canal invocando el **CreateChannel** método en el generador de canales.  
  
5. Abrir el canal.  
  
   Puede especificar la dirección de enlace y el punto de conexión en el código o de configuración.  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>Especifica el enlace y dirección de punto de conexión en el código  
 En el ejemplo de código siguiente se muestra cómo crear un **IRequestChannel** especificando la dirección de enlace y el punto de conexión en el código. El código para crear un **IOutputChannel** es el mismo, salvo que debe especificar un **IOutputChannel** interfaz para el **ChannelFactory** y tipo de canal.  
  
```  
// Create binding -- set binding properties before you open the factory.  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
// Create address.  
EndpointAddress odbAddress = new EndpointAddress("oracledb://ADAPTER/");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(odbBinding, odbAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a>Especifica el enlace y dirección de punto de conexión en la configuración  
 El ejemplo de código siguiente muestra cómo crear un generador de canales desde un punto de conexión de cliente especificado en la configuración.  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a>Los valores de configuración  
 El código siguiente muestra las opciones de configuración que se usa en el ejemplo anterior. El contrato para el extremo del cliente debe ser "System.ServiceModel.Channels.IRequestChannel" o "System.ServiceModel.Channels.IRequestChannel" según el tipo de forma del canal que desea crear.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" metadataPooling="true"  
                    statementCachePurge="false" statementCacheSize="10" pollingInterval="500"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" polledDataAvailableStatement="SELECT 1 FROM DUAL"  
                    pollWhileDataFound="false" notifyOnListenerStart="true" notificationPort="-1"  
                    inboundOperationType="Polling" dataFetchSize="65536" longDatatypeColumnSize="0"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="1" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="false" enablePerformanceCounters="false" />  
            </oracleDBBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracledb://adapter/" binding="oracleDBBinding"  
                bindingConfiguration="OracleDBBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a>Creación de canales de entrada (servicio)  
 Configurar la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para sondear las tablas de base de datos de Oracle y las vistas mediante el establecimiento de propiedades de enlace en una instancia de **OracleDBBinding**. A continuación, se usan este enlace para compilar un agente de escucha del canal desde el que puede obtener un **IInputChannel** canal para recibir el mensaje para operaciones de entrada desde el adaptador.  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a>Para crear y abrir un IInputChannel para recibir mensajes para operaciones de entrada  
  
1. Cree una instancia de **OracleDBBinding**.  
  
2. Establecer las propiedades de enlace necesarias para la operación de entrada. Por ejemplo, para la operación POLLINGSTMT, como mínimo debe establecer el **InboundOperationType**, **PollingStatement**, y **PollingInterval** enlazar propiedades a configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para sondear la base de datos de Oracle.  
  
3. Crear una colección de parámetros de enlace mediante la **BindingParameterCollection** clase y establecer las credenciales.  
  
4. Crear un agente de escucha del canal invocando **BuildChannelListener\<IInputChannel\>**  método en el **OracleDBBinding**. Especifique el URI de conexión de Oracle como uno de los parámetros a este método. Para obtener más información sobre el URI de conexión de Oracle, vea [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
5. Abra el agente de escucha.  
  
6. Obtener un **IInputChannel** canal invocando el **AcceptChannel** método en el agente de escucha.  
  
7. Abrir el canal.  
  
   El código siguiente muestra cómo crear un agente de escucha del canal y obtener un **IInputChannel** para mensajes entrantes desde el adaptador mediante la operación POLLINGSTMT.  
  
> [!NOTE]
>  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] de recepción unidireccional solo admite. Por lo tanto, debe usar IInputChannel para recibir mensajes para operaciones de entrada de la base de datos de Oracle.  
  
```  
// Create a binding: specify the InboundOperationType, PollingInterval (in seconds), the PollingStatement, and  
// the PostPollStatement.  
OracleDBBinding binding = new OracleDBBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PollingInterval = 30;  
binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "SCOTT";  
credentials.UserName.Password = "TIGER";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("oracleDB://ADAPTER");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)