---
title: Crear un canal mediante SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- channel programming, creating a channel
- how to, create a channel
- creating a channel
- WCF channel model, creating a channel
ms.assetid: 24af1465-bb60-41d7-98bd-e501a981f82a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8f42d21fe70a3058a9d92384c6a2853b0e35c84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981413"
---
# <a name="create-a-channel-using-sap"></a>Crear un canal con SAP
En el modelo de canal WCF, invocar operaciones en el sistema SAP o recibir mensajes desde el sistema SAP mediante el intercambio de mensajes SOAP con el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] a través de un canal WCF.  
  
- Invocar operaciones (operaciones de salida) mediante el uso un **IRequestChannel** o un **IOutputChannel** para enviar mensajes al adaptador  
  
- Recibir mensajes (desencadenados desde el sistema SAP) a través de un **IReplyChannel**.  
  
  Los temas de esta sección proporcionan información acerca de cómo crear y configurar las formas del canal que se usan para las operaciones de entrada y salidas.  
  
## <a name="creating-outbound-client-channels"></a>Crear canales salientes (cliente)  
 Puede usar un **IRequestChannel** o un **IOutputChannel** para invocar operaciones en el sistema SAP. En cualquier caso, cree primero un **System.ServiceModel.ChannelFactory** mediante la interfaz adecuada. Utilizamos el generador para crear el canal. Después de haber creado el canal se puede usar para invocar operaciones en el adaptador.  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>Para crear y abrir un canal de salida  
  
1. Crear e inicializar una instancia de **ChannelFactory** para la forma del canal deseado mediante el uso de un punto de conexión y un enlace. El punto de conexión especifica un URI de conexión de SAP y el enlace es una instancia de **SAPDBBinding**. (Establecer las propiedades de enlace necesarias antes de abrir el generador de canales).  
  
2. Proporcionar credenciales de SAP para el generador de canales mediante la **ClientCredentials** propiedad.  
  
3. Abra el generador de canales.  
  
4. Obtener una instancia del canal invocando el **CreateChannel** método en el generador de canales.  
  
5. Abrir el canal.  
  
   Puede especificar la dirección de enlace y el punto de conexión en el código o de configuración.  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>Especifica el enlace y dirección de punto de conexión en el código  
 En el ejemplo de código siguiente se muestra cómo crear un **IRequestChannel** especificando la dirección de enlace y el punto de conexión en el código. El código para crear un **IOutputChannel** es el mismo, salvo que debe especificar un **IOutputChannel** interfaz para el **ChannelFactory** y tipo de canal.  
  
```  
// Create binding -- set binding properties before you open the factory.  
SAPBinding sapBinding = new SAPBinding();  
  
// Create address.  
EndpointAddress sapAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(sapBinding, sapAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
// Open the factory  
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
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
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
            <sapBinding>  
                <binding name="SAPBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" enableBizTalkCompatibilityMode="false"  
                    receiveIdocFormat="Typed" enableSafeTyping="false" generateFlatFileCompatibleIdocSchema="true"  
                    maxConnectionsPerSystem="50" enableConnectionPooling="true"  
                    idleConnectionTimeout="00:15:00" flatFileSegmentIndicator="SegmentDefinition"  
                    enablePerformanceCounters="false" autoConfirmSentIdocs="false"  
                    acceptCredentialsInUri="false"  
                    padReceivedIdocWithSpaces="false" sncLibrary="" sncPartnerName="" />  
            </sapBinding>  
        </bindings>  
        <client>  
            <endpoint address="sap://CLIENT=800;LANG=EN;@a/ADAPSAP47/00?RfcSdkTrace=False&AbapDebug=False"  
                binding="sapBinding" bindingConfiguration="SAPBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a>Creación de canales de entrada (servicio)  
 Configurar el adaptador para recibir los mensajes entrantes de un sistema SAP estableciendo las propiedades de enlace en una instancia de **SAPBinding**. A continuación, se usan este enlace para compilar un agente de escucha del canal desde el que puede obtener un **IReplyChannel** canal para operaciones de recepción del adaptador.  
  
##### <a name="to-create-and-open-an-ireplychannel-to-receive-data-changed-notifications"></a>Para crear y abrir un IReplyChannel a las notificaciones de cambio de datos de recepción  
  
1. Cree una instancia de **SAPBinding**.  
  
2. Establezca las propiedades de enlace necesarias para las operaciones que desea recibir. Asegúrese de establecer el **AcceptCredentialsInUri** enlaza la propiedad.  
  
3. Crear un **BindingParameterCollection** y agregue un **InboundActionCollection** que contiene las acciones de las operaciones que desea recibir. El adaptador devolverá una excepción al sistema SAP para todas las demás operaciones. Este paso es opcional. Para obtener más información, consulte [recibir operaciones de entrada desde el sistema SAP mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).  
  
4. Crear un agente de escucha del canal invocando **BuildChannelListener\<IReplyChannel\>**  método en el **SAPBinding**. Especifique el URI de conexión de SAP como uno de los parámetros a este método. El URI de conexión debe contener los parámetros para un destino de RFC en el sistema SAP. Para obtener más información sobre el URI de conexión de SAP, consulte la [cree el URI de conexión del sistema SAP](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md). Si ha creado un **BindingParameterCollection** en el paso 3, especificarlo al crear la escucha del canal.  
  
5. Abra el agente de escucha.  
  
6. Obtener un **IReplyChannel** canal invocando el **AcceptChannel** método en el agente de escucha.  
  
7. Abrir el canal.  
  
   El código siguiente muestra cómo crear un agente de escucha del canal y obtener un **IReplyChannel** para operaciones de recepción del adaptador.  
  
```  
// Create a binding and specify any binding properties required  
// for the opreations you want to receive  
SAPBinding binding = new SAPBinding();  
  
// Set AcceptCredentialsInUri because the URI must contain credentials.  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying  
// the binding parameter collection (to filter for the Z_RFC_MKD_ADD action) and   
// a connection URI that contains listener parameters.  
Uri listeneraddress =  
new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, new BindingParameterCollection());  
listener.Open();  
  
// Get a channel from the listener and open it.  
channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)