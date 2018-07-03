---
title: Recibir llamadas de RFC de entrada de SAP con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFC calls, receiving using BizTalk Server
ms.assetid: 822fd9fb-772f-4910-a11e-25c1d5dca6e1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e70e2b81fd71a01ef6eae9e77ae3efea8cbf494
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986989"
---
# <a name="receive-inbound-rfc-calls-from-sap-using-biztalk-server"></a>Recibir llamadas de RFC de entrada de SAP con BizTalk Server
En un escenario de servidor RFC, hay tres entidades:  
  
- Un cliente SAP que se envía una solicitud a SAP para invocar una RFC. Esto podría invocarse mediante la GUI de SAP o mediante la realización de un cliente RFC llamar a través de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
- El sistema SAP que contiene una definición de función RFC que se invoca el cliente de SAP. El sistema SAP que se pasa en la solicitud al servidor RFC (el adaptador). Se usa el adaptador para obtener los metadatos de la llamada RFC que hace que el servidor SAP en el adaptador.  
  
- El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] que actúa como servidor RFC y hospeda la solicitud de cambio real.  
  
  La primera entidad, el cliente de SAP, no se trata en este tema. Si utiliza la GUI de SAP para invocar una RFC, consulte la documentación de SAP. Si usas el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para invocar una RFC, consulte [invocar RFC de SAP mediante el uso de BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).  
  
  Esta sección proporciona instrucciones sobre cómo usar el adaptador para recibir una llamada de servidor RFC, una vez que la solicitud de cambio es invocado por un cliente de SAP. Para obtener más información sobre cómo el adaptador es compatible con RFC receptora servidor llama con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [operaciones en RFC de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).  
  
## <a name="how-to-receive-an-inbound-rfc-call-from-the-sap-system"></a>¿Cómo recibir una llamada de RFC de entrada desde el sistema SAP?  
 Realizar una operación en un sistema SAP mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md). Para recibir una llamada de RFC desde el sistema SAP, estas tareas son:  
  
1. Configurar el sistema SAP para enviar RFC a una aplicación externa, en este caso el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
2. Crear un proyecto de BizTalk y generar el esquema para la solicitud de cambio que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] va a recibir desde el sistema SAP.  
  
3. Crear mensajes en el proyecto de BizTalk para recibir mensajes desde el sistema SAP y enviar respuestas.  
  
4. Crear una orquestación para recibir una solicitud de cambio desde el sistema SAP, procesarlo y enviar la respuesta al sistema SAP.  
  
5. Compile e implemente el proyecto de BizTalk.  
  
6. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
7. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="activities-on-the-sap-system"></a>Actividades en el sistema SAP  
 Antes de usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para recibir las llamadas a RFC entrantes desde el sistema SAP, asegúrese de completar las tareas siguientes en el sistema SAP.  
  
- Debe existir un destino RFC para el adaptador de SAP. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recibe las solicitudes de cambio desde el sistema SAP a través de un destino RFC definido en el sistema SAP. El destino RFC que contiene el Host de puerta de enlace de SAP, el servicio de puerta de enlace de SAP y el identificador de programa de SAP que se debe especificar en el URI de conexión en el código. Para obtener información acerca de cómo configurar un destino de RFC de SAP, consulte [crear una RFC, destino RFC y enviar una solicitud de cambio de sistema SAP](creating-an-rfc-in-an-sap-system.md).  
  
- Debe crear un módulo de función que define la solicitud de cambio en el sistema SAP. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza la definición de RFC en el sistema SAP para recuperar metadatos sobre la solicitud de cambio (tanto en tiempo de diseño como en tiempo de ejecución). Para obtener más información, consulte [crear una solicitud de cambio en un sistema SAP](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).  
  
   El siguiente es un ejemplo del código fuente en el sistema SAP para una solicitud de cambio que agrega dos enteros y devuelve su resultado. El código simplemente llama a la solicitud de cambio a través de un destino especificado. La implementación de la función se realiza mediante el código de cliente del adaptador SAP.  
  
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
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, RFCServer, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).  
  
## <a name="generating-the-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo recibir una llamada RFC entrante desde el sistema SAP, se genera el esquema para *Z_RFC_ADD* RFC. Este RFC que creó en el paso anterior. Este RFC toma dos valores enteros como parámetros de entrada.  
  
 Consulte [examinar, buscar y obtener metadatos para operaciones de RFC de SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) para obtener instrucciones sobre cómo generar el esquema para un determinado RFC.  
  
> [!IMPORTANT]
>  Dado que va a generar el esquema para una llamada entrante de RFC, asegúrese de seleccionar **(operación de entrada) de servicio** desde el **seleccione el tipo de contrato** lista desplegable en el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 Este tema, debe crear dos mensajes: uno para recibir mensajes desde el sistema SAP y otro para enviar una respuesta al sistema SAP.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema:  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  
  
1.  Agregue una nueva orquestación al proyecto de BizTalk.  
  
2.  Abra la vista de orquestación del proyecto de BizTalk, si no está abierto. Haga clic en **vista**, apunte a **Other Windows**y haga clic en **Vista orquestación**.  
  
3.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en la recién cree el mensaje y seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel **Message_1**, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *RFCServer.SAPBindingSchema.Z_RFC_ADD*, donde *RFCServer* es el nombre de su proyecto de BizTalk. *SAPBindingSchema* es el esquema generado para la solicitud de cambio *Z_RFC_ADD*.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **respuesta**.|  
    |Tipo de mensaje|Podrá ver la respuesta en la misma transacción desde donde se envía la solicitud de cambio.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Para obtener información sobre las excepciones que puede surgir al recibir una llamada al servidor RFC de un sistema SAP mediante BizTalk Server, vea [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]excepciones y control de errores con el adaptador SAP. En este ejemplo, considere un escenario donde un cliente envía una solicitud al sistema SAP para agregar dos enteros. El sistema SAP toma la solicitud, con los parámetros de entrada y la pasa al servidor RFC externo hospedado por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recibe la solicitud desde el sistema SAP, el proceso de la solicitud para agregar dos números enteros y genera una respuesta. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] pasa la respuesta al sistema SAP, que a su vez, se pasa al cliente RFC.  
  
 Para lograr esto como parte de una orquestación, la orquestación debe contener:  
  
- Puerto para recibir la solicitud al servidor RFC desde el sistema SAP y enviar la respuesta de recepción bidireccional.  
  
- Enviar y recibir las formas.  
  
- Forma construir mensaje, y en el que una forma asignación de mensajes, para procesar la solicitud de servidor RFC procedentes del sistema SAP.  
  
  Una orquestación de ejemplo para una llamada de servidor RFC es similar al siguiente.  
  
  ![Orquestación para realizar una llamada servidor RFC](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-Establecer **nombre** a *ListenToSAP*<br />-Establecer **activar** a *True*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-construct-message-shape"></a>Adición de la forma construir mensaje  
 Para procesar la llamada RFC entrante para agregar dos valores enteros, debe agregar una forma construir mensaje y en el que una forma asignación de mensajes a la orquestación, entre las dos formas de envío. En este ejemplo, la forma asignación de mensajes se invoca para agregar dos enteros. La forma asignación de mensajes también establece la acción de la respuesta que se envíe al sistema SAP.  
  
 Para la forma construir mensaje, establezca la **mensaje construido** propiedad **respuesta**.  
  
 El código para procesar la solicitud RFC podría formar parte de la misma solución de Visual Studio que el proyecto de BizTalk. Un código de ejemplo para agregar dos enteros tiene este aspecto.  
  
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
>  Después de compilar el proyecto, se crearán RFCServerResponseCreator.dll en el directorio del proyecto. Debe agregar este archivo DLL a la caché de ensamblados global (GAC).  
  
 Agregue la siguiente expresión para invocar este código de la forma asignación de mensajes y para establecer la acción para la respuesta enviada al sistema SAP. Para agregar una expresión, haga doble clic en la forma asignación de mensajes para abrir el Editor de expresiones.  
  
```  
Response = RFCServerResponseCreator.RFCServerResponseCreator.CreateResponse(Request.X, Request.Y);  
Response(WCF.Action) = "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response";  
```  
  
> [!IMPORTANT]
>  Debe establecer explícitamente la acción en el mensaje de respuesta. Si no establece la acción, el adaptador de WCF-Custom llega el mensaje de acción mediante la anexión de "Respuesta" a la acción de solicitud. Por lo tanto, se convierte en la acción para el mensaje de respuesta `http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`. Sin embargo, el sapBinding espera a que la acción de respuesta mediante la anexión de "/ respuesta" a la acción de solicitud, por ejemplo `http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`.  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para el puerto lógico. El nombre que aparece en el *puerto* columna es el nombre del puerto, tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|RFCServerPort|-Establecer **identificador** a *RFCServerPort*<br />-Establecer **tipo** a *RFCServerPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío recepción*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especifique los mensajes para las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores se establezcan para especificar los mensajes de las formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ListenToSAP|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *RFCServerPort.Add.Request*|  
|SendResponse|-Establecer **mensaje** a *FuncResponse*<br />-Establecer **operación** a *RFCServerPort.Add.Response*|  
  
 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  
  
 Debe ahora compile la solución de BizTalk y, a continuación, implementarlo en un servidor BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [cómo configurar una aplicación](../../core/how-to-configure-an-application.md).
  
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para esta orquestación, debe:  
  
  - Definir un WCF-Custom o puerto de recepción de SAP de WCF. Este puerto recibe las llamadas entrantes de RFC desde el sistema SAP y enviará la respuesta al sistema SAP. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).  
  
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).
  
  También debe agregar el ensamblado del proyecto RFCServerResponseCreator a la aplicación de BizTalk. Ha creado este proyecto para procesar la llamada RFC recibida desde el sistema SAP. Para ello:  
  
1.  En el árbol de consola en el lado izquierdo de la consola de administración de BizTalk Server, en la aplicación de BizTalk donde se importan los enlaces, haga clic en **recursos**, apunte a **agregar**y, a continuación, haga clic en **Ensamblados de BizTalk**.  
  
2.  En el **agregar recursos** cuadro de diálogo, haga clic en **agregar**y, a continuación, navegue hasta la carpeta que contiene RFCServerResponseCreator.dll. Seleccione el archivo y, a continuación, haga clic en **abierto**.  
  
3.  En el **agregar recursos** cuadro de diálogo, haga clic en **Aceptar**.  
  
## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para recibir las llamadas entrantes de RFC de un sistema SAP. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md), y [cómo iniciar una aplicación](../../core/how-to-start-and-stop-a-biztalk-application.md).
  
 En esta etapa, asegúrese de que:  
  
-   El WCF-Custom o WCF SAP puerto de recepción para recibir las llamadas a RFC de SAP se ejecuta el sistema.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe enviar una solicitud de cambio para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Puede hacerlo mediante la ejecución de la transacción SE37 en el sistema SAP. También debe especificar los parámetros de entrada para la llamada RFC. El adaptador recibe la llamada junto con los parámetros, lo procesa y envía la respuesta al sistema SAP. Podrá ver la respuesta en la misma transacción desde donde se envía la solicitud de cambio.  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones que puede surgir al recibir una llamada al servidor RFC de un sistema SAP mediante BizTalk Server, vea [excepciones y control de errores con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlaces. Cuando genere un archivo de enlaces, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío, recepción, puertos, etc., de la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [enlaces del adaptador SAP reutilizar](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)