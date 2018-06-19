---
title: Ejecutar operaciones en componentes empresariales mediante BizTalk Server y el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business components, performing operations by using BizTalk Server
- how to, perform operations on a business component by using BizTalk Server
ms.assetid: 5bd0f4d7-60ec-42ea-84c0-618aeef9688f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3fc90d0798e3fca420e567d1a50c58607db4ae3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966050"
---
# <a name="run-operations-on-business-components-using-biztalk-server-and-the-siebel-adapter"></a>Ejecutar operaciones en componentes empresariales mediante BizTalk Server y el adaptador de Siebel
La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone las operaciones que se pueden invocar en un componente empresarial. Las operaciones en los componentes empresariales se pueden clasificar como:  
  
-   Operaciones estándar en los componentes empresariales. Estos incluyen la inserción, la consulta, actualización y eliminarán. En este tema se describe cómo realizar estas operaciones mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
-   Operaciones en los componentes empresariales que contiene campos de grupo con varios valores. Estos incluyen la operaciones estándar, así como la asociación, desasociar, Query_ [MVG_Child_Bussiness_Comp]. Para obtener más información acerca de cómo realizar estas operaciones, vea [ejecutar operaciones en los componentes empresariales con MVG campos mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)  
  
-   Operaciones en los componentes empresariales que contiene campos de la lista desplegable. Para obtener más información acerca de cómo realizar estas operaciones, vea [ejecutar operaciones en los componentes empresariales con campos de lista desplegable mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md).  
  
 Para obtener más información acerca de cómo los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite operaciones en componentes empresariales, vea [operaciones en componentes de negocio de Siebel](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md). Para obtener más información acerca de la estructura de SOAP de los mensajes para llevar a cabo estas operaciones, vea [esquemas de mensaje para las operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
## <a name="how-to-perform-operations-on-a-business-component"></a>Cómo realizar operaciones en un componente empresarial  
 Realizar una operación en un sistema Siebel mediante la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md). 
 
 Para completar una operación en un componente empresarial, estas tareas son:  
  
1.  Cree un proyecto de BizTalk y genere el esquema para la operación que desea invocar en el componente empresarial.  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes desde el sistema Siebel.  
  
3.  Crear una orquestación para invocar una operación en el sistema Siebel.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, SiebelAccount, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo invocar las operaciones en un componente empresarial, esquema se generan para la operación de inserción en el componente de empresa de la cuenta. Vea [recuperación de metadatos para las operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md) para obtener más información sobre cómo generar el esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 En este tema, debe crear dos mensajes: uno para enviar una solicitud para el sistema Siebel y otro para recibir una respuesta.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema:  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Abra la vista de orquestación del proyecto de BizTalk, si no está abierto. Haga clic en **vista**, seleccione **otras ventanas**y haga clic en **Vista orquestación**.  
  
2.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el recién crear mensaje y seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *SiebelAccount.SiebelBindingSchema.Insert*, donde *SiebelAccount* es el nombre de su proyecto de BizTalk. *SiebelBindingSchema* es el esquema generado para invocar la *insertar* operación en *cuenta* componente empresarial.|  
  
5.  Repita el paso anterior para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **respuesta**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *SiebelAccount.SiebelBindingSchema.InsertResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para llevar a cabo una operación en un componente de negocio de Siebel. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] consume este mensaje y lo pasa al sistema Siebel. La respuesta en el sistema Siebel se guarda en otra ubicación. Una orquestación típica para realizar operaciones en componentes empresariales de Siebel contendría:  
  
-   Enviar y recibir formas a fin de enviar mensajes a Siebel y recibir respuestas.  
  
-   Un unidireccional puerto de recepción para recibir mensajes de solicitud para enviar a Siebel.  
  
-   Puerto para enviar mensajes de solicitud para Siebel y recibir respuestas de envío bidireccional.  
  
-   Un puerto de envío unidireccional para enviar las respuestas de Siebel a una carpeta.  
  
 Una orquestación de ejemplo para la *insertar* operación en un *cuenta* componente empresarial es similar al siguiente:  
  
 ![Orquestación para insertar datos en Siebel BC](../../adapters-and-accelerators/adapter-siebel/media/f005df04-dfbf-4c75-8f9b-2bc3a357d52b.gif "f005df04-dfbf-4c75-8f9b-2bc3a357d52b")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveXML|Receive|-Establecer **nombre** a *ReceiveXML*<br />-Establecer **activar** a *es True*|  
|SendToLOB|Send|-Establecer **nombre** a *SendToLOB*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la *puerto* columna son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|FileIn|-Establecer **identificador** a *FileIn*<br />-Establecer **tipo** a *FileInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SaveResponse|-Establecer **identificador** a *SaveResponse*<br />-Establecer **tipo** a *SaveResponseType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y los valores que se pueden establecer para especificar los mensajes para formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveXML|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *FileIn.Insert.Request*|  
|SendToLOB|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.Insert.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.Insert.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.Insert.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [cómo generar orquestaciones](../../core/how-to-build-orchestrations.md) y [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. [Cómo crear una aplicación](../../core/how-to-create-an-application.md) se enumeran los pasos.
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviar al sistema Siebel.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta en el sistema Siebel.  
  
    -   Definir un puerto de envío WCF-Custom o WCF-Siebel físico para enviar mensajes al sistema Siebel. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md).
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk para crear puertos de envío (para las llamadas salientes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para llevar a cabo una *insertar* operación en el *cuenta* componente empresarial de Siebel. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [iniciar una aplicación de BizTalk](../../core/how-to-start-and-stop-a-biztalk-application.md) o [iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   Se está ejecutando el puerto de envío WCF-Custom o WCF-Siebel para enviar mensajes al sistema Siebel.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar el mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe ajustarse al esquema de la operación de inserción (en el componente de negocio de cuenta) que ha generado anteriormente. Por ejemplo, el mensaje de solicitud para insertar un registro en el componente de empresa de la cuenta es:  
  
```  
<Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
  <ArrayOfAccountInsertRecord>  
    <AccountInsertRecord xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">  
      <Currency_x0020_Code>usd</Currency_x0020_Code>  
      <Current_x0020_Volume>9</Current_x0020_Volume>  
      <Customer_x0020_Account_x0020_Group>Sold-To Party</Customer_x0020_Account_x0020_Group>  
      <Location>Location_1</Location>  
      <Main_x0020_Phone_x0020_Number>4256543212</Main_x0020_Phone_x0020_Number>  
      <Name>Name_Surname</Name>  
      <Party_x0020_Name>test_party</Party_x0020_Name>  
      <Primary_x0020_Address_x0020_Id>1212 street</Primary_x0020_Address_x0020_Id>  
    </AccountInsertRecord>  
  </ArrayOfAccountInsertRecord>  
</Insert>  
```  
  
 Vea [esquemas de mensaje para las operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md) para obtener más información acerca del esquema del mensaje de solicitud.  
  
 La orquestación consume el mensaje de solicitud y lo pasa al sistema Siebel. La respuesta en el sistema Siebel se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta del sistema Siebel para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<InsertResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
  <InsertResult>  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">1-8ANYV</string>  
  </InsertResult>  
</InsertResponse>  
```  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones puede surgir al realizar una operación sobre el uso del componente de negocio [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [excepciones y control de errores con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlaces, puede importar los valores de configuración desde el archivo para que no es necesario crear los puertos de envío, recepción, puertos, etc. para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador en el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)