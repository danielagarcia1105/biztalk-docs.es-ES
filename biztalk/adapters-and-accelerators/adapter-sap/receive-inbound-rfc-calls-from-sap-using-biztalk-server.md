---
title: Recibir llamadas de RFC de entrada de SAP mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: RFC calls, receiving using BizTalk Server
ms.assetid: 822fd9fb-772f-4910-a11e-25c1d5dca6e1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b949ae0d6d5938493c78ed542a67d3c8bd09b48
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="receive-inbound-rfc-calls-from-sap-using-biztalk-server"></a>Recibir llamadas de RFC de entrada de SAP con BizTalk Server
En un escenario de servidor RFC, hay tres entidades:  
  
-   Un cliente SAP que envía una solicitud a SAP para invocar una solicitud de cambio. Esto se podría invocar mediante la GUI de SAP o mediante la realización de un cliente RFC llaman a través de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   El sistema SAP que contiene una definición de función RFC, se invoca el cliente SAP. El sistema SAP se pasa en la solicitud al servidor RFC (el adaptador). Se usa el adaptador para obtener los metadatos de la llamada RFC que realiza el servidor SAP en el adaptador.  
  
-   La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] que actúa como el servidor RFC y hospeda la solicitud de cambio real.  
  
 La primera entidad, el cliente SAP, no se describe en este tema. Si usas la GUI de SAP para invocar una solicitud de cambio, consulte la documentación de SAP. Si usas el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para invocar una solicitud de cambio, consulte [invocar RFC en SAP utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).  
  
 Esta sección proporciona instrucciones sobre cómo usar el adaptador para recibir una llamada de servidor RFC, tras la solicitud de cambio es invocado por un cliente SAP. Para obtener más información sobre cómo el adaptador es compatible con RFC receptora server llama usando la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [operaciones en RFC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).  
  
## <a name="how-to-receive-an-inbound-rfc-call-from-the-sap-system"></a>¿Cómo recibir una llamada de RFC entrantes desde el sistema SAP?  
 Realizar una operación en un sistema SAP mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md). Para recibir una llamada de RFC desde el sistema SAP, estas tareas son:  
  
1.  Configurar el sistema SAP para enviar RFC a una aplicación externa, en este caso el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
2.  Crear un proyecto de BizTalk y generar esquema para la solicitud de cambio que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] va a recibir desde el sistema SAP.  
  
3.  Crear mensajes en el proyecto de BizTalk para recibir mensajes desde el sistema SAP y enviar respuestas.  
  
4.  Crear una orquestación para recibir una solicitud de cambio desde el sistema SAP, procesarlo y enviar la respuesta al sistema SAP.  
  
5.  Compilar e implementar el proyecto de BizTalk.  
  
6.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
7.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="activities-on-the-sap-system"></a>Actividades en el sistema SAP  
 Antes de usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para recibir llamadas RFC entrantes desde el sistema SAP, asegúrese de completar las tareas siguientes en el sistema SAP.  
  
-   Debe existir un destino RFC para el adaptador SAP. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recibe las solicitudes de cambio desde el sistema SAP a través de un destino RFC definido en el sistema SAP. El destino RFC que contiene el Host de puerta de enlace de SAP, el servicio de puerta de enlace de SAP y el identificador de programa de SAP que debe especificar en el URI de conexión en el código. Para obtener información acerca de cómo configurar un destino RFC en SAP, consulte [crear una solicitud de cambio, el destino de RFC y enviar una solicitud de cambio de sistema SAP](creating-an-rfc-in-an-sap-system.md).  
  
-   Debe crear un módulo de función que define la solicitud de cambio en el sistema SAP. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa la definición de RFC en el sistema SAP para recuperar metadatos sobre la solicitud de cambio (tanto en tiempo de diseño y en tiempo de ejecución). Para obtener más información, consulte [crear una solicitud de cambio en un sistema SAP](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).  
  
     El siguiente es un ejemplo del código fuente en el sistema SAP para una solicitud de cambio que agrega dos enteros y devuelve su resultado. El código llama simplemente la solicitud de cambio a través de un destino especificado. La implementación de la función se realiza mediante el código de cliente del adaptador SAP.  
  
    ```  
    FUNCTION Z_RFC_ADD.  
    *"------------------------------------------------------------------  
    *"  
    *"Local interface:  
    *"  IMPORTING  
    *"     VALUE(X) TYPE  INT4  
    *"     VALUE(Y) TYPE  INT4  
    *"     VALUE(DEST) TYPE  CHAR20 DEFAULT 'SAPADAPTER'  
    *"  EXPORTING  
    *"     VALUE(RESULT) TYPE  INT4  
    *"------------------------------------------------------------------  
    CALL FUNCTION 'Z_RFC_ADD' DESTINATION DEST  
      EXPORTING X = X  
                Y = Y  
      IMPORTING RESULT = RESULT.  
  
    ENDFUNCTION.  
    ```  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, RFCServer, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).  
  
## <a name="generating-the-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo recibir una llamada RFC entrante desde el sistema SAP, se genera el esquema para *Z_RFC_ADD* RFC. Este RFC ha creado en el paso anterior. Este RFC toma dos valores enteros como parámetros de entrada.  
  
 Vea [exploración, búsqueda y get de metadatos para las operaciones de RFC en SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) para obtener instrucciones sobre cómo generar el esquema para un determinado RFC.  
  
> [!IMPORTANT]
>  Dado que va a generar el esquema para una llamada entrante de RFC, asegúrese de seleccionar **servicio (operación entrante)** desde el **seleccione el tipo de contrato** lista desplegable situada en la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 En este tema, debe crear dos mensajes: uno para recibir mensajes desde el sistema SAP y el otro para enviar una respuesta al sistema SAP.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema:  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregue una nueva orquestación al proyecto de BizTalk.  
  
2.  Abra la vista de orquestación del proyecto de BizTalk, si no está abierto. Haga clic en **vista**, seleccione **otras ventanas**y haga clic en **Vista orquestación**.  
  
3.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el recién crear mensaje y seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para **Message_1**, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *RFCServer.SAPBindingSchema.Z_RFC_ADD*, donde *RFCServer* es el nombre de su proyecto de BizTalk. *SAPBindingSchema* es el esquema generado para la solicitud de cambio *Z_RFC_ADD*.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **respuesta**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *RFCServer.SAPBindingSchema.Z_RFC_ADDResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir llamadas de servidor RFC desde el sistema SAP. En este ejemplo, considere un escenario donde un cliente RFC envía una solicitud al sistema SAP para agregar dos enteros. El sistema SAP recibe la solicitud, con los parámetros de entrada y lo pasa al servidor RFC externo hospedado por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recibe la solicitud desde el sistema SAP, proceso de la solicitud para agregar dos números enteros y genera una respuesta. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] pasa la respuesta al sistema SAP, que a su vez, se pasa al cliente RFC.  
  
 Para lograr esto como parte de una orquestación, la orquestación debe contener:  
  
-   Puerto para recibir la solicitud al servidor RFC desde el sistema SAP y enviar la respuesta de recepción bidireccional.  
  
-   Formas de recepción y envío.  
  
-   Forma construir mensaje, y en el que una forma asignación de mensajes, para procesar la solicitud al servidor RFC procedentes del sistema SAP.  
  
 Una orquestación de ejemplo para una llamada de servidor RFC es similar al siguiente.  
  
 ![Orquestación para realizar servidor RFC llamada](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-Establecer **nombre** a *ListenToSAP*<br />-Establecer **activar** a *es True*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-construct-message-shape"></a>Agregar forma construir mensaje  
 Para procesar la llamada RFC entrante para agregar dos valores enteros, debe agregar una forma construir mensaje y en el que una forma asignación de mensajes a la orquestación, entre las dos formas de envío. En este ejemplo, la forma asignación de mensajes, se invoca para agregar dos enteros. La forma asignación de mensajes también establece la acción de la respuesta que se enviarán al sistema SAP.  
  
 Para la forma construir mensaje, establezca la **construir mensaje** propiedad **respuesta**.  
  
 El código para procesar la solicitud RFC podría formar parte de la misma solución de Visual Studio que el proyecto de BizTalk. Código de ejemplo para sumar dos enteros tiene el siguiente aspecto.  
  
```  
namespace RFCServerResponseCreator  
{  
    public class RFCServerResponseCreator  
    {  
        private static XmlDocument messageIn;  
        private static XmlDocument messageOut;  
        public static XmlDocument CreateRequest(int a, int b, string destination)  
        {  
            messageIn = new XmlDocument();  
            messageIn.LoadXml(  "<Z_RFC_ADD xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<DEST>" + destination + "</DEST>" +  
                                "<X>" + a + "</X>" +  
                                "<Y>" + b + "</Y>" +   
                                "</Z_RFC_ADD>"  
                             );  
            return messageIn;  
        }  
        public static XmlDocument CreateResponse(int a, int b)  
        {  
            int c = a + b;  
            messageOut = new XmlDocument();  
            messageOut.LoadXml( "<Z_RFC_ADDResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<RESULT>" + c + "</RESULT>" +   
                                "</Z_RFC_ADDResponse>"  
                              );  
            return messageOut;  
        }  
    }  
}  
```  
  
> [!NOTE]
>  Después de compilar el proyecto, RFCServerResponseCreator.dll se creará en el directorio del proyecto. Debe agregar este archivo DLL a la caché de ensamblados global (GAC).  
  
 Agregue la siguiente expresión para invocar este código de la forma asignación de mensajes y establecer la acción para la respuesta enviada al sistema SAP. Para agregar una expresión, haga doble clic en la forma asignación de mensajes para abrir el Editor de expresiones.  
  
```  
Response = RFCServerResponseCreator.RFCServerResponseCreator.CreateResponse(Request.X, Request.Y);  
Response(WCF.Action) = "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response";  
```  
  
> [!IMPORTANT]
>  Debe establecer explícitamente la acción en el mensaje de respuesta. Si no establece la acción, adaptador de WCF-Custom llega en el mensaje de acción mediante la anexión de "Respuesta" a la acción de solicitud. Por lo tanto, se convierte en la acción para el mensaje de respuesta `http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`. Sin embargo, la sapBinding espera a que la acción de respuesta anexando "/ respuesta" a la acción de solicitud, por ejemplo `http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`.  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para el puerto lógico. El nombre que aparece en el *puerto* columna es el nombre del puerto, tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|RFCServerPort|-Establecer **identificador** a *RFCServerPort*<br />-Establecer **tipo** a *RFCServerPortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío recepción*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y los valores que se pueden establecer para especificar los mensajes para formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ListenToSAP|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *RFCServerPort.Add.Request*|  
|SendResponse|-Establecer **mensaje** a *FuncResponse*<br />-Establecer **operación** a *RFCServerPort.Add.Response*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Debe compilar ahora la solución de BizTalk y, a continuación, implementarlo en un servidor BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [cómo configurar una aplicación](../../core/how-to-configure-an-application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir un WCF-Custom o puerto de recepción de WCF-SAP. Este puerto recibirá llamadas RFC entrantes desde el sistema SAP y enviará la respuesta al sistema SAP. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).  
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).
  
 También debe agregar el ensamblado del proyecto RFCServerResponseCreator a la aplicación de BizTalk. Ha creado este proyecto para procesar la llamada RFC recibida desde el sistema SAP. Para ello:  
  
1.  En el árbol de consola en el lado izquierdo de la consola de administración de BizTalk Server, en la aplicación de BizTalk que ha importado los enlaces, haga clic en **recursos**, seleccione **agregar**y, a continuación, haga clic en **Ensamblados de BizTalk**.  
  
2.  En el **agregar recursos** cuadro de diálogo, haga clic en **agregar**y, a continuación, navegue hasta la carpeta que contiene RFCServerResponseCreator.dll. Seleccione el archivo y, a continuación, haga clic en **abiertos**.  
  
3.  En el **agregar recursos** cuadro de diálogo, haga clic en **Aceptar**.  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para recibir llamadas entrantes de RFC de un sistema SAP. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md), y [cómo iniciar una aplicación](../../core/how-to-start-and-stop-a-biztalk-application.md).
  
 En esta fase, asegúrese de que:  
  
-   El WCF-Custom o WCF-SAP puerto de recepción para recibir llamadas RFC de SAP se ejecuta el sistema.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe enviar una solicitud de cambio para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Puede hacerlo mediante la ejecución de la transacción SE37 en el sistema SAP. También debe especificar los parámetros de entrada para la llamada RFC. El adaptador recibe la llamada junto con los parámetros, lo procesa y envía la respuesta al sistema SAP. Podrá ver la respuesta en la misma transacción del que envió la solicitud de cambio.  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones que puede surgir al recibir una llamada de servidor RFC desde un sistema SAP mediante BizTalk Server, vea [excepciones y control de errores con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlaces. Una vez que se genera un archivo de enlaces, puede importar los valores de configuración desde el archivo para que no es necesario crear los puertos de envío, recepción, puertos, etc. para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador SAP reutilizar](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)