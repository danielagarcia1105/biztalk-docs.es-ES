---
title: 'Paso 4: Configurar la solución de BizTalk Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60e6a82-51af-41e5-a755-5f337492ba2f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e65c3cf64045378b0f69b6980b98cdec88f175d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013885"
---
# <a name="step-4-configure-the-biztalk-server-solution"></a>Paso 4: Configurar la solución de BizTalk Server
En el paso anterior, creó e implementó una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir notificaciones de Salesforce en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e insertar los detalles en una base de datos de SQL Server local. En este paso, configuraremos la aplicación en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. La configuración de la aplicación supone principalmente crear puertos físicos correspondientes a los puertos lógicos que creamos en la orquestación. También implica enlazar el puerto físico a los puertos lógicos. Llevaremos a cabo los siguientes pasos para configurar la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- Configurar una ubicación de recepción WCF-BasicHttpRelay de tipo solicitud-respuesta para recibir las notificaciones de oportunidades de Salesforce.  
  
- Configurar un puerto de envío WCF-WebHttp de tipo petición-respuesta para enviar una consulta a Salesforce para recuperar los detalles de producto relacionados con la notificación de oportunidad recibida. Este puerto de envío recibe también la respuesta de la consulta de Salesforce.  
  
- Configurar un puerto de envío WCF-SQL unidireccional para insertar la respuesta de la consulta de Salesforce en una base de datos de SQL Server local.  
  
- Configurar la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] asociando el puerto lógico de la orquestación con los puertos físicos creados en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-wcf-basichttprelay-receive-location"></a>Para configurar la ubicación de recepción WCF-BasicHttpRelay  
  
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Expanda el nodo Applications y busque el **SalesforceIntegration** aplicación. Esta aplicación se creó cuando implementó el proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde Visual Studio.  
  
2. Expanda el **SalesforceIntegration** aplicación, haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción de solicitud-respuesta**. Especifique el nombre de puerto `ReceiveOppNotification` y en el panel izquierdo, haga clic en **ubicaciones de recepción**.  
  
3. En el cuadro de diálogo Propiedades de la ubicación de recepción, especifique los siguientes valores.  
  
   |||  
   |-|-|  
   |Nombre|Escriba `ReceiveOppNotification`.|  
   |Tipo|Seleccione **WCF-BasicHttpRelay**|  
   |Controlador de recepción|Seleccione **BizTalkServerApplication**|  
   |Canalización de recepción|Seleccione **XMLReceive**|  
   |Canalización de envío|Seleccione **PassThruTransmit**|  
  
    Haga clic en **configurar** para el tipo de puerto.  
  
4. En el cuadro de diálogo "Propiedades de transporte WCF-BasicHttpRelay", especifique los siguientes valores:  
  
   1. En el **General** ficha, para **dirección (URI)**, escriba `https://btssalesforce.servicebus.windows.net/notifications/opportunity`. En este caso, **btssalesforce** es que creó en el espacio de nombres [paso 1: crear un Namespace de Bus de servicio](../core/step-1-create-a-service-bus-namespace.md). La dirección URL que especifique aquí es la misma dirección URL que especificó al crear un flujo de trabajo en Salesforce en [paso 2: configurar el sistema Salesforce](../core/step-2-set-up-the-salesforce-system.md). Configurar un flujo de trabajo en el que cada vez que se establece la etapa de oportunidad en Closed Won, Salesforce envía una notificación a la dirección URL *<https://btssalesforce.servicebus.windows.net/notifications/opportunity>*. Especificamos la misma dirección URL aquí como parte de la configuración de esta ubicación de recepción. Cuando se habilita la ubicación de recepción, se crea en [!INCLUDE[winazure](../includes/winazure-md.md)] el extremo de transmisión especificado por la dirección URL.  
  
   2. En el **seguridad** ficha, especifique lo siguiente:  
  
      -   Para **modo de seguridad**, seleccione **transporte** y **tipo de autenticación de cliente de retransmisión**, seleccione **ninguno**.  
  
      -   Seleccione el **habilitar la detección de servicio** casilla de verificación para publicar el comportamiento del servicio en la [registro del servicio](http://msdn.microsoft.com/library/windowsazure/dd582704.aspx). Especifique el **nombre para mostrar** que denota el nombre con el que el servicio se publica en el registro. Puede establecer el **modo de detección** en público o privado. Para este tutorial, establezca **nombre para mostrar** a `SF Outbound Notification` y **modo de detección** a **pública**.  
  
      -   En el cuadro de servicio de control de acceso, haga clic en **editar**. Para **Uri de STS de Access Control Service**, escriba `https://btssalesforce-sb.accesscontrol.windows.net/`. Para **nombre del emisor** y **clave del emisor**, escriba los valores que guardó en [paso 1: crear un Namespace de Bus de servicio](../core/step-1-create-a-service-bus-namespace.md) para **Default User** y **Clave predeterminada** campos.  
  
   3. Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo abiertos.  
  
### <a name="to-configure-the-wcf-webhttp-send-port"></a>Para configurar el puerto de envío WCF-WebHttp  
  
1. Expanda el **SalesforceIntegration** aplicación, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
2. En el cuadro de diálogo Propiedades de puerto de envío, especifique los siguientes valores:  
  
   |||  
   |-|-|  
   |Nombre|Escriba `SalesforceREST`.|  
   |Tipo|Seleccione **WCF-WebHttp**|  
   |Controlador de envío|Seleccione **BizTalkServerApplication**|  
   |Canalización de envío|Seleccione **PassThruTransmit**|  
   |Canalización de recepción|Seleccione **AddNamespace** y haga clic en el botón de puntos suspensivos en la canalización para configurar la canalización.<br /><br /> -En **fase 1: descodificar**, para **NamespaceBase**, escriba `http://BtsSalesforceIntegration.QueryResult`. Este es el espacio de nombres del esquema QueryResult.xsd que creó en [paso 3b: recuperar detalles de oportunidades de Salesforce con el adaptador WCF-WebHttp](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md). Cuando el **AddNamespace** recibir canalización recibe la respuesta de Salesforce, agrega este espacio de nombres al mensaje de respuesta. De manera predeterminada, el mensaje de respuesta de Salesforce no incluye ningún espacio de nombres.<br />     Para **NamespacePrefix**, escriba `sf`.<br />-En **fase 2: desensamblar**, acepte los valores predeterminados y, a continuación, haga clic en **Aceptar**.|  
  
    En el cuadro de diálogo Propiedades de puerto de envío, haga clic en **configurar** para el tipo de puerto.  
  
3. En el cuadro de diálogo Propiedades de transporte WCF-WebHttp, especifique los siguientes valores:  
  
   1. En la pestaña **General** , haga lo siguiente:  
  
      - para **dirección (URI)**, escriba `https://<Salesforce_instance_name>.salesforce.com/services/data/v24.0`. Puede recuperar el nombre de instancia de Salesforce copiando el texto que aparece entre https:// y Salesforce.com en la barra de dirección donde tiene abierto el portal Salesforce.com. Por ejemplo, si la dirección URL del portal de Salesforce es *https://*<em>na15</em>*.salesforce.com/home/home.jsp*, el nombre de instancia de Salesforce es **na15**.  
  
      - En **método HTTP y asignación de URL** cuadro, especifique lo siguiente:  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/query?q={VAR}" />  
        </BtsHttpUrlMapping>  
        ```  
  
         Aquí es cómo se usa esta configuración, para consultar a Salesforce para recuperar más información acerca de la notificación de oportunidad, debemos realizar una operación GET en el punto de conexión de REST de Salesforce (especificado en el **dirección** campo) y anexe el consulta para recuperar los detalles de oportunidades. Por tanto, la dirección URL debe tener el siguiente aspecto:  
  
        ```  
        https://na15.salesforce.com/services/data/v24.0/query?q=<query_string>  
        ```  
  
         Ya tenemos el punto de conexión de REST de Salesforce como parte de la **dirección (URI)** campo. Por lo tanto, como parte de **método HTTP y asignación de URL** propiedad, se especifican mediante el método GET y anexe la **{VAR}** como una variable.  
  
      - En el **asignaciones de variables** cuadro, haga clic en **editar**. En este cuadro Especifique cómo el valor de la **{VAR}** variable se deduce en tiempo de ejecución.  
  
         En [paso 3b: recuperar detalles de oportunidades de Salesforce con el adaptador WCF-WebHttp](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md), habíamos promovido la propiedad de consulta, lo que resultó de crear un **PropertySchema.xsd**. Vamos a usar el **consulta** elemento de ese esquema para pasar la cadena de consulta asignando ese elemento a la variable {VAR} en la dirección URL.  
  
         En el cuadro de diálogo asignaciones de variables, la **Variable** columna muestra el nombre de la variable que especificó anteriormente, por ejemplo, **VAR**. En el **nombre de la propiedad** columna, especifique el nombre de la propiedad promovida que tiene la cadena de consulta que se pasará a la variable. En este tutorial, es el nombre de la propiedad **consulta**. Por último, para **propiedad Namespace**, especifique el espacio de nombres para el **PropertySchema.xsd**, que es `https://BtsSalesforceIntegration.PropertySchema`. Haga clic en **Aceptar**.  
  
         ![Ficha general de WCF&#45;adaptador WebHttp](../core/media/bts-sf-webhttp-general.jpg "BTS_SF_WebHttp_General")  
  
   2. En el **seguridad** ficha, para **modo de seguridad**, seleccione **transporte**.  
  
   3. En el **comportamiento** , utilice el comportamiento personalizado que creó en [paso 3d: habilitar BizTalk Server para enviar y recibir mensajes desde Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md) se autentiquen en Salesforce. Para usar el comportamiento, proceda como se indica a continuación:  
  
      -   Haga clic en **EndpointBehavior** y, a continuación, seleccione **Agregar extensión**.  
  
      -   En el **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione **Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce**. Habíamos usado este nombre de comportamiento cuando agregamos el comportamiento a machine.config.  
  
      -   Seleccione el comportamiento recién agregado y especifique los siguientes valores:  
  
          |||  
          |-|-|  
          |consumerKey (obligatorio)|Especifique la clave de consumidor para su cuenta de Salesforce. Puede recuperar la clave de consumidor para ello, vaya a la aplicación conectada a Salesforce que creó en [paso 2: configurar el sistema Salesforce](../core/step-2-set-up-the-salesforce-system.md).|  
          |consumerSecret (obligatorio)|Recuperar el secreto del consumidor de la fuerza de ventas conectado de aplicación que creó en [paso 2: configurar el sistema Salesforce](../core/step-2-set-up-the-salesforce-system.md).|  
          |Password (obligatorio)|Especifique la contraseña para la cuenta de Salesforce. Para conectarse a Salesforce desde una aplicación de terceros, debe especificar la contraseña con el formato que permite el token de seguridad. Por ejemplo, si la contraseña es **contraseña** y el token es **XXXXXX**, debe escribir `passwordXXXXXX`.|  
          |sessionTimeout|Tiene un valor predeterminado de 300.|  
          |Username (obligatorio)|Especifique la cuenta de inicio de sesión de desarrollador de Salesforce.|  
  
           ![La ficha comportamiento de WCF&#45;adaptador WebHttp](../core/media/bts-sf-webhttp-behavior.jpg "BTS_SF_WebHttp_Behavior")  
  
   4. En el **mensajes** ficha **mensaje saliente** cuadro, para **suprimir el cuerpo para verbos**, escriba `GET`. Esto garantiza que, para el método GET, no haya carga de mensajes en la solicitud que se envía a Salesforce.  
  
   5. Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo abiertos.  
  
### <a name="to-configure-the-wcf-sql-send-port"></a>Para configurar el puerto de envío WCF-SQL  
  
1.  Expanda el **SalesforceIntegration** aplicación, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **unidireccional puerto de envío**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, especifique los siguientes valores:  
  
    |||  
    |-|-|  
    |Nombre|Escriba `SendToSQL`.|  
    |Tipo|Seleccione **WCF-SQL**|  
    |Controlador de envío|Seleccione **BizTalkServerApplication**|  
    |Canalización de envío|Seleccione **XMLTransmit**|  
  
     En el cuadro de diálogo Propiedades de puerto de envío, haga clic en **configurar** para el tipo de puerto.  
  
3.  En el cuadro de diálogo Propiedades de transporte WCF-SQL, especifique los siguientes valores:  
  
    1.  En la pestaña **General** , haga lo siguiente:  
  
        -   En `Endpoint Address`, haga clic en **configurar**. Para el **InitialCatalog** propiedad, especifique el nombre de base de datos que contiene la tabla donde se deben especificar los datos de respuesta de Salesforce. En este tutorial, especifique este valor como `Orders`. Para **Server** propiedad, escriba el nombre del servidor donde está instalada la base de datos de SQL Server.  
  
        -   En **encabezado Action de SOAP**, especifique la acción que se usará para insertar en el **OrderDetails** tabla. Debe escribir `TableOp/Insert/dbo/OrderDetails`.  
  
    2.  En la pestaña Credenciales, si deja todo en blanco, el adaptador usará autenticación de Windows para conectarse a la base de datos de SQL Server. Si desea usar alguna otra forma de autenticación, puede especificar los valores relevantes.  
  
    3.  Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo abiertos.  
  
### <a name="to-configure-the-biztalk-server-application"></a>Para configurar la aplicación de BizTalk Server  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **SalesforceIntegration** aplicación y, a continuación, haga clic en **configurar**.  
  
2. En el cuadro de diálogo Configurar aplicación, seleccione la **NotificationServiceClient** orquestación, y en el panel derecho, haga lo siguiente:  
  
   1. Para Host, seleccione **BizTalkServerApplication**.  
  
   2. La lógica de asignación de puerto de recepción **SalesforceNotificationPort** , puerto de recepción físico **ReceiveOppNotification**.  
  
   3. Asigne el puerto de envío lógico **SalesforceRESTInterface** el físico de envío, **SalesforceREST**.  
  
   4. Asigne el puerto de envío lógico **SendToSQL** el físico de envío, **SendToSQL**.  
  
      Haga clic en **Aceptar**.  
  
3. Haga clic en el **SalesforceIntegration** aplicación y, a continuación, haga clic en **iniciar**. Esto inicia el **NotificationServiceClient** orquestación, habilita la ubicación de recepción e inicia el puerto de envío.  
  
   En este tema, terminamos configurando la solución en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] asociando los puertos lógicos de la orquestación con los puertos físicos.