---
title: Recibir IDOC desde SAP mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDOCs, sample (receiving)
- IDOCs, business scenarios for receiving
- IDOCs, receiving from SAP using BizTalk Server
ms.assetid: b904bf07-1108-4ed3-8564-d83eaafff247
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45dc38a939e71a8f4eb3d3afe87736fc548f8570
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-idocs-from-sap-using-biztalk-server"></a>Recibir IDOC desde SAP mediante BizTalk Server
Recibir un IDOC implica la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para que actúe como un servidor RFC para recibir una llamada RFC especial de SAP. El adaptador SAP puede recibir IDOC actúa como un servidor RFC o un servidor de tRFC. Para obtener más información sobre cómo recibir un IDOC con el adaptador que se comporta como un servidor de tRFC, consulte [recibir IDOC desde SAP en un contexto transaccional usando el servidor BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md).  
  
 La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone dos operaciones diferentes para recibir IDOC:  
  
-   **Recibir** operación habilita el adaptador recibir los IDOC que tengan un esquema fuertemente tipado.  
  
-   **ReceiveIdoc** operación habilita el adaptador recibir los IDOC que tengan un esquema débilmente tipada. Esta operación recibe IDOC como una cadena en un mensaje XML en el \<idocData > etiqueta.  
  
 En el lado de adaptador, puede especificar un valor para el **ReceiveIDocFormat** enlace de propiedad para especificar el formato de IDOC recibiría el adaptador.  
  
-   **Escribió** especifica el adaptador recibirá IDOC con esquema fuertemente tipado. Esto da como resultado un IDOC XML.  
  
-   **Cadena** especifica el adaptador recibirá IDOC con esquema débilmente tipada. Esto da como resultado un mensaje XML con el \<idocData > etiqueta.  
  
-   **RFC** especifica el adaptador recibirá IDOC en cualquier formato.  
  
 Para recibir IDOC, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también admite un conjunto de propiedades de contexto de mensaje que pueden usar los clientes de adaptador en las orquestaciones. Para obtener la lista de propiedades, vea [propiedades de contexto de mensaje para recibir IDOC](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md).  
  
 Para obtener más información acerca de cómo los [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite recibir IDOC desde un sistema SAP, consulte [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md). Para obtener más información acerca de la estructura de SOAP de los mensajes para recibir un IDOC, consulte [esquemas de mensaje para las operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).  
  
## <a name="biztalk-scenarios-for-receiving-idocs-from-an-sap-system"></a>Escenarios de BizTalk para recibir IDOC desde un sistema SAP  
 En la tabla siguiente proporciona los escenarios clave de BizTalk para recibir IDOC desde un sistema SAP:  
  
|Adaptador de entrada de SAP|Procesamiento de BizTalk|Salida|  
|-------------------------------|------------------------|------------|  
|IDOC (a través de la interfaz de tRFC)|**Tiempo de diseño de metadatos**<br /><br /> 1.  Establezca la propiedad de enlace GenerateFlatFileCompatibleIdocSchema a **True**.<br />2.  Generar el esquema para el **recepción** operación para obtener un uso específico de IDOC [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].<br />3.  Establezca la propiedad de enlace ReceiveIdocFormat a **Typed**.<br /><br /> **Tiempo de diseño de orquestación**<br /><br /> 1.  Recibir IDOC de XML.<br />2.  Usar el ensamblador de archivo sin formato para convertir XML IDOC a archivo sin formato.|IDOC de archivo sin formato|  
|IDOC (a través de la interfaz de tRFC)|**Tiempo de diseño de metadatos**<br /><br /> 1.  Establezca la propiedad de enlace GenerateFlatFileCompatibleIdocSchema a **True**.<br />2.  Generar el esquema para el **recepción** operación para obtener un uso específico de IDOC [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].<br />3.  Establezca la propiedad de enlace ReceiveIdocFormat a **Typed**.<br /><br /> **Tiempo de diseño de orquestación**<br /><br /> -Recibir IDOC de XML.|IDOC DE XML|  
|IDOC (a través de la interfaz de tRFC)|**Tiempo de diseño de metadatos**<br /><br /> 1.  Establezca la propiedad de enlace GenerateFlatFileCompatibleIdocSchema a **True**.<br />2.  Generar el esquema para el **recepción** operación para obtener un uso específico de IDOC [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].<br />3.  Establezca la propiedad de enlace ReceiveIdocFormat a **cadena**.<br /><br /> **Tiempo de diseño de orquestación**<br /><br /> 1.  Recibir mensaje XML con IDOC de archivo sin formato en \<idocData > etiqueta.<br />2.  Usar la compatibilidad de XPath del adaptador de WCF en la configuración del puerto de recepción para extraer el IDoc de archivo sin formato del mensaje XML. Por ejemplo:<br />     `/*[local-name()='ReceiveIdoc']/*[local-name()='idocData']`<br />3.  Utilice el Desensamblador de archivos sin formato para convertir IDOC de archivo sin formato en XML IDOC.<br /><br /> **Importante** este enfoque puede utilizarse para recibir los IDOC con el nuevo basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y aplicarlos directamente en un proyecto de BizTalk existente escrito para recibir IDOC desde el adaptador de SAP de BizTalk existente. También es el enfoque recomendado para recibir IDOC con número de versión menor que el número de versión (SYSREL).|IDOC DE XML|  
|IDOC (a través de la interfaz de tRFC)|**Tiempo de diseño de metadatos**<br /><br /> 1.  Generar el esquema para el **ReceiveIdoc** operación desde el nodo IDOC mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].<br />2.  Establezca la propiedad de enlace ReceiveIdocFormat a **cadena**.<br /><br /> **Tiempo de diseño de orquestación**<br /><br /> -Recibir mensaje XML con el IDOC representado como una cadena en el \<idocData > etiqueta.|IDOC de archivo sin formato en mensajes XML|  
  
## <a name="how-to-receive-an-idoc-from-an-sap-system"></a>¿Cómo recibir un IDOC desde un sistema SAP?  
 Realizar una operación en un sistema SAP mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md). Para recibir un IDOC desde un sistema SAP, estas tareas son:  
  
1.  Cree un proyecto de BizTalk y generar el esquema para el IDOC que desea invocar en el sistema SAP. Al generar el esquema Asegúrese de que se establecen las propiedades de enlace necesaria, como se muestra en la tabla anterior. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes desde el sistema SAP.  
  
3.  Crear una orquestación para recibir un IDOC desde un sistema SAP.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="samples-based-on-this-topic"></a>Muestras basadas en este tema  
 Ejemplos, ReceiveIDOC y ReceiveIDOC_SYSREL, en función de este tema también se proporcionan con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 Debe generar esquema para el *recepción* el funcionamiento de la *ORDERS03. V3.620* IDOC en el */IDOC/ORDERS/ORDERS03* nodo. Vea [exploración, búsqueda y obtener metadatos para las operaciones de IDOC de SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-idoc-operations-in-sap.md) para obtener instrucciones sobre cómo generar el esquema para un IDOC determinado. Al generar el esquema, puede establecer las siguientes propiedades:  
  
-   *GenerateFlatFileCompatibleIDoc* – genera \<appinfo > etiquetas para que el analizador de archivos sin formato de BizTalk puede usarse en escenarios de BizTalk para admitir IDOC de archivo sin formato.  
  
-   *FlatFileSegmentIndicator* : indica si el esquema IDOC \<appinfo > etiquetas deben contener los nombres de definición de segmento o nombres de tipos de segmento. Esto es aplicable cuando un deseos usado para enviar y recibir un IDOC de archivo sin formato de SAP. Si el *GenerateFlatFileCompatibleIDoc* se establece en false, entonces *FlatFileSegmentIndicator* se omite la propiedad de enlace.  
  
> [!IMPORTANT]
>  Dado que va a generar el esquema para una llamada entrante de IDOC, asegúrese de seleccionar **servicio (operación entrante)** desde el **seleccione el tipo de contrato** lista desplegable situada en la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 En este tema, debe crear dos mensajes: uno para recibir un IDOC desde el sistema SAP y el otro para enviar una respuesta.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema:  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregue una nueva orquestación al proyecto de BizTalk.  
  
2.  Abra la vista de orquestación del proyecto de BizTalk, si no está abierto. Haga clic en **vista**, seleccione **otras ventanas**y haga clic en **Vista orquestación**.  
  
3.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el recién crear mensaje y seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *ReceiveIDOC.SAPBindingSchema2*, donde *ReceiveIDOC* es el nombre de su proyecto de BizTalk. *SAPBindingSchema2* es el esquema generado para la operación de recepción.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **respuesta**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *ReceiveIDOC.SAPBindingSchema3*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir IDOC desde el sistema SAP. En un escenario típico, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recibe una llamada IDOC desde el sistema SAP, procesa la solicitud y pasa la respuesta al sistema SAP. Para lograr esto como parte de una orquestación, la orquestación debe contener:  
  
-   Puerto para recibir IDOC desde el sistema SAP y enviar la respuesta de recepción bidireccional.  
  
-   Formas de recepción y envío.  
  
-   Forma construir mensaje y en el que una forma asignación de mensajes, para generar una respuesta que se enviarán al sistema SAP.  
  
    > [!NOTE]
    >  Si la orquestación incluye una recepción bidireccional (solicitud-respuesta) de puerto para recibir IDOC desde el sistema SAP, la orquestación debe enviar una respuesta al sistema SAP. De lo contrario, el sistema SAP no envía el IDOC siguiente. Sin embargo, si el puerto de recepción un unidireccional, la orquestación no tiene que enviar una respuesta al sistema SAP.  
  
-   Un puerto de envío unidireccional para enviar el IDOC recibido desde el sistema SAP en una carpeta.  
  
 Una orquestación de ejemplo para recibir un IDOC desde un sistema SAP tiene el siguiente aspecto:  
  
 ![Orquestación para recibir IDOC](../../adapters-and-accelerators/adapter-sap/media/20d4f251-2474-4fd5-becd-2915f9efa81b.gif "20d4f251-2474-4fd5-becd-2915f9efa81b")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-Establecer **nombre** a *ListenToSAP*<br /><br /> -Establecer **activar** a *es True*|  
|SaveIDOC|Send|-Establecer **nombre** a *SaveIDOC*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-construct-message-shape"></a>Agregar forma construir mensaje  
 En la orquestación, debe generar una respuesta y enviarlo al sistema SAP. Para ello, debe agregar una forma construir mensaje y en el que dar forma a una asignación de mensajes a la orquestación. La forma asignación de mensajes invoca el código que genera un mensaje de respuesta que se envía al sistema SAP. La forma asignación de mensajes también establece la acción de la respuesta que se enviarán al sistema SAP.  
  
> [!IMPORTANT]
>  Si la orquestación incluye una recepción bidireccional (solicitud-respuesta) de puerto para recibir IDOC desde el sistema SAP, la orquestación debe enviar una respuesta al sistema SAP. De lo contrario, el sistema SAP no envía el IDOC siguiente. Sin embargo, si el puerto de recepción un unidireccional, la orquestación no tiene que enviar una respuesta al sistema SAP.  
  
 Para la forma construir mensaje, establezca la **construir mensaje** propiedad **respuesta**.  
  
 El código para generar la respuesta podría ser parte de la misma solución de Visual Studio que el proyecto de BizTalk. Un código de ejemplo para generar un mensaje de respuesta tiene el siguiente aspecto.  
  
```  
namespace IdocReceiveResponseMessageCreator  
{  
    public class IdocReceiveResponseMessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  
  
        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\test\\in";  
            try  
            {  
                ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                Console.WriteLine("EXCEPTION: " + ex.ToString());  
                throw ex;  
            }  
            //Create Message From XML  
            Message = new XmlDocument();  
            Message.PreserveWhitespace = true;  
            Message.Load(ResponseDoc);  
            return Message;  
        }   
    }  
}  
```  
  
> [!NOTE]
>  Después de compilar el proyecto, IdocReceiveResponseMessageCreator.dll se creará en el directorio del proyecto. Debe agregar este archivo DLL a la caché de ensamblados global (GAC).  
  
 Agregue la siguiente expresión para invocar este código de la forma asignación de mensajes y establecer la acción para la respuesta enviada al sistema SAP. Para agregar una expresión, haga doble clic en la forma asignación de mensajes para abrir el Editor de expresiones.  
  
```  
Response = IdocReceiveResponseMessageCreator.IdocReceiveResponseMessageCreator.XMLMessageCreator();  
Response(WCF.Action)= "http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response";  
```  
  
> [!IMPORTANT]
>  Debe establecer explícitamente la acción en el mensaje de respuesta. Si no establece la acción, adaptador de WCF-Custom llega en el mensaje de acción mediante la anexión de "Respuesta" a la acción de solicitud. Por lo tanto, se convierte en la acción para el mensaje de respuesta `http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/ReceiveResponse`. Sin embargo, la sapBinding espera a que la acción de respuesta anexando "/ respuesta" a la acción de solicitud, por ejemplo `http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response`.  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para el puerto lógico. El nombre que aparece en el *puerto* columna es el nombre del puerto, tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|ReceiveIDOCPort|-Establecer **identificador** a *ReceiveIDOCPort*<br /><br /> -Establecer **tipo** a *ReceiveIDOCPortType*<br /><br /> -Establecer **patrón de comunicación** a *solicitudes y respuestas*<br /><br /> -Establecer **dirección de comunicación** a *envío recepción*|  
|GetIDOCPort|-Establecer **identificador** a *GetIDOCPort*<br /><br /> -Establecer **tipo** a *GetIDOCPortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*|  
  
> [!IMPORTANT]
>  Si la orquestación incluye una recepción bidireccional (solicitud-respuesta) de puerto para recibir IDOC desde el sistema SAP, la orquestación debe enviar una respuesta al sistema SAP. De lo contrario, el sistema SAP no envía el IDOC siguiente.  
  
### <a name="adding-a-flat-file-assembler"></a>Agregar un ensamblador de archivo sin formato  
 Debe agregar un ensamblador para convertir el mensaje entrante de IDOC en un archivo plano.  
  
##### <a name="to-add-a-flat-file-assembler"></a>Para agregar un ensamblador de archivo sin formato  
  
1.  Haga clic en el proyecto de BizTalk, seleccione **agregar**y seleccione **nuevo elemento**.  
  
2.  En el cuadro de diálogo, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Categorías|Archivos de canalización|  
    |Plantillas instaladas de Visual Studio|Canalización de envío|  
    |Nombre|SendIDOC|  
  
3.  Se abrirá el Diseñador de canalizaciones. Desde el **componentes de canalización de BizTalk** herramientas, arrastre el **ensamblador de archivo sin formato** componente de canalización en el **ensamblado** fase de la canalización de envío.  
  
4.  Desde el **propiedades de componente de canalización** ver, especifique un valor para el **esquema de documento** propiedad. En la lista desplegable, asegúrese de seleccionar el esquema correspondiente en el IDOC la operación de recepción.  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y los valores que se pueden establecer para especificar los mensajes para formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ListenToSAP|-Establecer **mensaje** a *de solicitud*<br /><br /> -Establecer **operación** a *ReceiveIDOCPort.ReceiveIDOC.Request*|  
|SaveIDOC|-Establecer **mensaje** a *de solicitud*<br /><br /> -Establecer **operación** a *GetIDOCPort.ReceiveIDOC.Request*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br /><br /> -Establecer **operación** a *ReceiveIDOCPort.ReceiveIDOC.Response*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, vea [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md)
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [cómo configurar una aplicación](../../core/how-to-configure-an-application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir ubicaciones de envío y puerto de envío físico. Esta ubicación contendrá el IDOC procedentes del sistema SAP.  
  
        > [!IMPORTANT]
        >  Para la canalización XMLTransmit, asegúrese de seleccionar ***SendIDOC***. Creó esta canalización como parte del proyecto de BizTalk.  
  
    -   Definir un WCF-Custom o puerto de recepción de WCF-SAP. Este puerto recibirá un IDOC entrante desde el sistema SAP y pasar a la orquestación. Este puerto también envía la respuesta al sistema SAP. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).
  
        > [!IMPORTANT]
        >  Asegúrese de que la propiedad de enlace **ReceiveIDocFormat** está establecido en **Typed**.  
  
        > [!IMPORTANT]
        >  Si la propiedad de enlace **EnableBizTalkCompatibilityMode** se establece en true, asegúrese de agregar el esquema de propiedades de BizTalk DLL para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un recurso en la aplicación de BizTalk, es decir, la aplicación en la que la se implementa el proyecto. Para obtener instrucciones sobre cómo agregar recursos vea [solucionar problemas de funcionamiento con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md).  
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).
  
 También debe agregar el ensamblado del proyecto IdocReceiveResponseMessageCreator a la aplicación de BizTalk. Ha creado este proyecto para generar la respuesta que se enviarán al sistema SAP. Para ello:  
  
1.  En el árbol de consola en el lado izquierdo de la consola de administración de BizTalk Server, en la aplicación de BizTalk que ha importado los enlaces, haga clic en **recursos**, seleccione **agregar** y, a continuación, haga clic en **Ensamblados de BizTalk**.  
  
2.  En el **agregar recursos** cuadro de diálogo, haga clic en **agregar** y navegue hasta la carpeta que contiene IdocReceiveResponseMessageCreator.dll. Seleccione el archivo y, a continuación, haga clic en **abiertos**.  
  
3.  En el **agregar recursos** cuadro de diálogo, haga clic en **Aceptar**.  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para recibir un IDOC desde el sistema SAP. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md), o [cómo iniciar una aplicación](../../core/how-to-start-and-stop-a-biztalk-application.md).
  
 En esta fase, asegúrese de que:  
  
-   El puerto de envío de archivo para guardar el IDOC entrante en una ubicación de archivo se está ejecutando  
  
-   El WCF-Custom o WCF-SAP puerto de recepción para recibir IDOC desde SAP está ejecutando el sistema.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe ir el sistema SAP y enviar un IDOC en el adaptador. El adaptador recibe el IDOC y lo guarda en una ubicación de archivo especificada como parte de la orquestación.  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones que puede surgir al recibir un IDOC desde un sistema SAP mediante BizTalk Server, vea [excepciones y control de errores con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlaces. Una vez que se genera un archivo de enlaces, puede importar los valores de configuración desde el archivo para que no es necesario crear los puertos de envío, recepción, puertos, etc. para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador SAP reutilizar](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)