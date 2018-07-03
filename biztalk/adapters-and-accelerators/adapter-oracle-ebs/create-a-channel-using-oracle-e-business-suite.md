---
title: Crear un canal con Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d18b7c2f-a43e-4499-ba94-4955dd5fe641
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 947dc1a0a2b602d1dbcce032f721998b9fc84a84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984645"
---
# <a name="create-a-channel-using-oracle-e-business-suite"></a>Crear un canal con Oracle E-Business Suite
En el modelo de canal WCF, podrá invocar operaciones en Oracle E-Business Suite y recibir los resultados mediante el intercambio de mensajes SOAP con el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] a través de un canal WCF.  
  
- Invocar operaciones (operaciones de salida) mediante el uso un **IRequestChannel** o un **IOutputChannel** para enviar mensajes al adaptador.  
  
- Recibir mensajes de operaciones de entrada a través de un **IInputChannel**.  
  
  Los temas de esta sección proporcionan información acerca de cómo crear y configurar las formas del canal que se usan para las operaciones de entrada y salidas.  
  
## <a name="creating-outbound-client-channels"></a>Crear canales salientes (cliente)  
 Puede usar un **IRequestChannel** o un **IOutputChannel** para invocar operaciones en Oracle E-Business Suite. En cualquier caso, cree primero un **System.ServiceModel.ChannelFactory** mediante la interfaz adecuada. Utilizamos el generador para crear el canal. Después de haber creado el canal se puede usar para invocar operaciones en el adaptador.  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>Para crear y abrir un canal de salida  
  
1. Crear e inicializar una instancia de **ChannelFactory** para la forma del canal deseado mediante el uso de un punto de conexión y un enlace. El punto de conexión especifica un URI de conexión de Oracle E-Business Suite y el enlace es una instancia de **OracleEBSBinding**.  
  
2. Proporcionar credenciales de Oracle E-Business Suite para el generador de canales mediante la **credenciales** propiedad.  
  
3. Abra el generador de canales.  
  
4. Obtener una instancia del canal invocando el **CreateChannel** método en el generador de canales.  
  
5. Abrir el canal.  
  
   Puede especificar la dirección de enlace y el punto de conexión en el código o de configuración.  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>Especifica el enlace y dirección de punto de conexión en el código  
 En el ejemplo de código siguiente se muestra cómo crear un **IRequestChannel** especificando la dirección de enlace y el punto de conexión en el código. El código para crear un **IOutputChannel** es el mismo, salvo que debe especificar un **IOutputChannel** interfaz para el **ChannelFactory** y tipo de canal.  
  
```  
// Create binding -- set binding properties before you open the factory.  
OracleEBSBinding binding = new OracleEBSBinding();  
  
// Create address  
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(binding, address);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it.  
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
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a>Los valores de configuración  
 El código siguiente muestra las opciones de configuración que se usa en el ejemplo anterior. El contrato para el extremo del cliente debe ser "System.ServiceModel.Channels.IRequestChannel" o "System.ServiceModel.Channels.IOutputChannel" según el tipo de forma del canal que desea crear.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="0"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true" enablePerformanceCounters="false">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://oracle_ebs_instance/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a>Creación de canales de entrada (servicio)  
 Configurar la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear las tablas de base de datos de Oracle y las vistas mediante el establecimiento de propiedades de enlace en una instancia de **OracleEBSBinding**. A continuación, se usan este enlace para compilar un agente de escucha del canal desde el que puede obtener un **IInputChannel** canal para recibir operaciones de entrada desde el adaptador.  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a>Para crear y abrir un IInputChannel para recibir mensajes para operaciones de entrada  
  
1. Cree una instancia de **OracleEBSBinding**.  
  
2. Establecer las propiedades de enlace necesarias para la operación de entrada. Por ejemplo, para una operación de sondeo, como mínimo debe establecer el **InboundOperationType**, **PolledDataAvailableStatement**, **PollingAction**y el **PollingInput** enlace de propiedades para configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear la base de datos de Oracle.  
  
3. Crear una colección de parámetros de enlace mediante la **BindingParameterCollection** clase y establecer las credenciales.  
  
4. Crear un agente de escucha del canal invocando **BuildChannelListener\<IInputChannel\>**  método en el **OracleEBSBinding**. Especifique el URI de conexión de Oracle como uno de los parámetros a este método.  
  
5. Abra el agente de escucha.  
  
6. Obtener un **IInputChannel** canal invocando el **AcceptChannel** método en el agente de escucha.  
  
7. Abrir el canal.  
  
   El código siguiente muestra cómo crear un agente de escucha del canal y obtener un **IInputChannel** para recibir mensajes para operaciones de entrada desde el adaptador.  
  
> [!IMPORTANT]
>  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] de recepción unidireccional solo admite. Por lo tanto, debe usar **IInputChannel** para recibir mensajes para operaciones de entrada de Oracle E-Business Suite.  
  
```  
// Create a binding: specify the InboundOperationType, the PolledDataAvailableStatement, the PollingAction, and   
// the PollingInput binding properties.  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "myuser";  
credentials.UserName.Password = "mypassword";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("oracleebs://oracle_ebs_instance/");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
IInputChannel channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)