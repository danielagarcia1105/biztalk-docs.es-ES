---
title: Invocar tRFCs en SAP mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tRFCs, invoking using BizTalk Server
ms.assetid: 9489adca-cf2c-4e15-8573-445acd7ebf73
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eeaa8b0d67e4592ef6622f747a1ddaea875084d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-trfcs-in-sap-using-biztalk-server"></a>Invocar tRFCs en SAP mediante BizTalk Server
Llamadas a funciones remotas (tRFCs) transaccional garantiza un tiempo de ejecución y solamente uno de una solicitud de cambio en un sistema SAP. Puede invocar cualquiera de los documentos de RFC obtenidas por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un tRFC. Invocar un tRFC es similar a la invocación de una solicitud de cambio (consulte [invocar RFC en SAP utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)) con las siguientes diferencias:  
  
-   El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies tRFCs bajo un nodo diferente (**TRFC**) que las solicitudes de cambio (**RFC**).  
  
-   operaciones de tRFC incluyen un parámetro GUID que se asigna al Id. de transacción de SAP para el tRFC por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Después de invocar un tRFC, debe invocar la operación de RfcConfirmTransID para confirmar la tRFC en el sistema SAP (confirman). Esta operación aparece directamente en el **TRFC** nodo [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
 Para obtener más información acerca de cómo los [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite la invocación de un tRFC, consulte [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md). Para obtener más información acerca de la estructura de SOAP de los mensajes para invocar un tRFC, consulte [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md).  
  
## <a name="how-to-invoke-a-trfc-in-an-sap-system-using-biztalk-server"></a>¿Cómo invocar un tRFC en un sistema SAP mediante BizTalk Server?  
 Realizar una operación en un sistema SAP mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md). Para invocar un tRFC en un sistema SAP, estas tareas son:  
  
1.  Cree un proyecto de BizTalk y genere el esquema para el que desea invocar en el sistema SAP de tRFC. También debe generar el esquema para el **RfcConfirmTransID** operación para confirmar el TID en el sistema SAP.  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes desde el sistema SAP.  
  
3.  Crear una orquestación para invocar un tRFC en el sistema SAP y, a continuación, confirmar el TID que se crea en el sistema SAP en respuesta a la llamada de tRFC por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, tRFCClient, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo invocar un tRFC mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], se generará el esquema para:  
  
-   *BAPI_SALESORDER_CREATEFROMDAT2* tRFC.  
  
-   Operación de RfcConfirmTransID. Debe usar esta operación para confirmar el TID que se crea en el sistema SAP. Una vez que el sistema SAP recibe esta llamada elimina el TID del sistema.  
  
 Vea [buscar, búsqueda y obtener los metadatos de tRFC operaciones en SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-trfc-operations-in-sap.md) para obtener más información sobre cómo generar el esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado a los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 En este tema, debe crear cuatro mensajes: establece un mensaje de respuesta de solicitud establecido para invocar el tRFC y otro mensaje de solicitud y respuesta para invocar la operación de RfcConfirmTransID.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Abra la vista de orquestación del proyecto de BizTalk, si no está abierto. Haga clic en **vista**, seleccione **otras ventanas**y haga clic en **Vista orquestación**.  
  
2.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el recién crear mensaje y seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel para **Message_1**, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione el tipo de mensaje. Por ejemplo, seleccione *tRFC_Client.SAPBindingSchema1.BAPI_SALESORDER_CREATEFROMDAT2*, donde *tRFC_Client* es el nombre de su proyecto de BizTalk. *SAPBindingSchema1* es el esquema generado para *BAPI_SALESORDER_CREATEFROMDAT2*.|  
  
5.  Repita el paso anterior para crear mensajes de más de tres. En el **propiedades** panel para los mensajes nuevos, haga lo siguiente.  
  
    |Identificador de conjunto a|Establecer el tipo de mensaje en|  
    |-----------------------|-------------------------|  
    |Respuesta|*tRFC_Client.SAPBindingSchema1.BAPI_SALESORDER_CREATEFROMDAT2Response*|  
    |TIDRequest|*tRFC_Client.SAPBindingSchema3.RfcConfirmTransID*|  
    |TIDResponse|*tRFC_Client.SAPBindingSchema3.RfcConfirmTransIDResponse*|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para invocar tRFCs en un sistema SAP. En esta orquestación, puede quitar un mensaje de solicitud en una determinada ubicación de recepción. La orquestación consume este mensaje y lo pasa al sistema SAP. La respuesta se recibe de SAP y se guarda en otra ubicación. El mensaje de respuesta contiene un GUID. La orquestación incluye un **construir mensaje** para extraer el GUID de la respuesta y construir un mensaje que se ajusta al esquema de la **RfcConfirmTransID** operación. El mensaje para invocar la **RfcConfirmTransID** operación se envía al sistema SAP con el GUID como un parámetro _ una orquestación típica para invocar tRFCs en un sistema SAP, seguido por un **RfcConfirmTransID**contendría la operación:  
  
-   Enviar y recibir formas para enviar mensajes al sistema SAP y recibir respuestas.  
  
-   Una forma construir mensaje y en el que dar forma a una asignación de mensajes para construir un mensaje para la **RfcConfirmTransID** operación.  
  
-   Un unidireccional puerto de recepción para recibir mensajes de solicitud para enviar al sistema SAP para invocar el tRFC.  
  
-   Puerto para enviar mensajes al invocar el tRFC y recibir la respuesta de envío bidireccional.  
  
-   Bidireccional puerto de envío para enviar mensajes para invocar la **RfcConfirmTransID** operación y recibir respuesta.  
  
-   Unidireccional dos puertos de envío para enviar las respuestas desde el sistema SAP a una carpeta.  
  
 Una orquestación de ejemplo es similar al siguiente:  
  
 ![Orquestación para realizar un cliente tRFC llamada](../../adapters-and-accelerators/adapter-sap/media/369d62dd-9ae4-4673-b346-03d2acfb453a.gif "369d62dd-9ae4-4673-b346-03d2acfb453a")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveXml|Receive|-Establecer **nombre** a *ReceiveXml*<br />-Establecer **activar** a *es True*|  
|SendToLOB|Send|-Establecer **nombre** a *SendToLOB*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
|SendTIDMsg|Send|-Establecer **nombre** a *SendTIDMsg*|  
|ReceiveTIDRsp|Receive|-Establecer **nombre** a *ReceiveTIDRsp*<br />-Establecer **activar** a *False*|  
|SendTIDRsp|Send|-Establecer **nombre** a *SendTIDRsp*|  
  
### <a name="adding-the-construct-message-shape"></a>Agregar la forma construir mensaje  
 La respuesta desde el sistema SAP para la llamada de tRFC contiene un GUID. Para confirmar la llamada tRFC, debe pasar el mismo GUID de la operación de RfcConfirmTransID. Para ello, debe incluir una forma construir mensaje, y dentro de ese dar forma a una asignación de mensajes, en la orquestación. En este caso, el propósito de la forma construir mensaje es:  
  
-   Para extraer el GUID de la respuesta que se recibe desde el sistema SAP para la llamada de tRFC.  
  
-   Para construir un mensaje que se ajusta al esquema de mensajes para la operación de RfcConfirmTransID.  
  
 Para la forma construir mensaje, debe establecer el **construir mensaje** propiedad **TIDRequest**.  
  
 Debe agregar el siguiente fragmento de código a la forma asignación de mensajes:  
  
```  
XmlDoc = new System.Xml.XmlDocument();  
XmlDoc.LoadXml("<RfcConfirmTransID xmlns='http://Microsoft.LobServices.Sap/2007/03/RfcApi/'><TransactionalRfcOperationIdentifier /></RfcConfirmTransID>");  
TIDRequest = XmlDoc;  
TIDRequest.TransactionalRfcOperationIdentifier = xpath(Response,"string(/*[local-name()='BAPI_SALESORDER_CREATEFROMDAT2Response']/*[local-name()='TransactionalRfcOperationIdentifier']/text())");  
```  
  
 Para utilizar el fragmento de código anterior, debe tener:  
  
-   Crea una variable, **XmlDoc**, en el BizTalk del proyecto y establezca su tipo en System.Xml.XmlDocument. Para obtener más información acerca de cómo crear variables, consulte [usar Variables en orquestaciones](../../core/using-variables-in-orchestrations.md).
  
-   Promueve la **TransactionalRfcOperationIdentifier** propiedad en el esquema para la operación de RfcConfirmTransID. Para obtener más información acerca de cómo promover una propiedad, vea [promocionar propiedades](../../core/promoting-properties.md).
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la *puerto* columna son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|FileIn|-Establecer **identificador** a *FileIn*<br />-Establecer **tipo** a *FileInPortType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|tRFC_Port|-Establecer **identificador** a *tRFC_Port*<br />-Establecer **tipo** a *tRFC_PortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SavetRFCResponse|-Establecer **identificador** a *SavetRFCResponse*<br />-Establecer **tipo** a *SavetRFCResponsePortType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
|TID_Port|-Establecer **identificador** a *TID_Port*<br />-Establecer **tipo** a *TIDPortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SaveTIDResponse|-Establecer **identificador** a *SaveTIDResponse*<br />-Establecer **tipo** a *SaveTIDResponsePortType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y los valores que se pueden establecer para especificar los mensajes para formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveXml|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *FileIn.tRFC.Request*|  
|SendToLOB|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *tRFC_Port.tRFC.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *tRFC_Port.tRFC.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SavetRFCResponse.tRFC.Request*|  
|SendTIDMsg|-Establecer **mensaje** a *TIDRequest*<br />-Establecer **operación** a *TID_Port.TID.Request*|  
|ReceiveTIDRsp|-Establecer **mensaje** a *TIDResponse*<br />-Establecer **operación** a *TID_Port.TID.Response*|  
|SendTIDRsp|-Establecer **mensaje** a *TIDResponse*<br />-Establecer **operación** a *SaveTIDResponse.TID.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Debe compilar ahora la solución de BizTalk y, a continuación, implementarlo en un servidor BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [cómo configurar una aplicación](../../core/how-to-configure-an-application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk utilizará el mensaje de solicitud para enviar al sistema SAP.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta desde el sistema SAP.  
  
    -   Definir físico de WCF-Custom o WCF-SAP enviar puertos (una cada para el mensaje de solicitud de tRFC y el mensaje RfcConfirmTransID) para enviar mensajes al sistema SAP. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk Server para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para invocar tRFCs en un sistema SAP. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md), o [cómo iniciar una aplicación](../../core/how-to-start-and-stop-a-biztalk-application.md).  
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   Los puertos de envío WCF-Custom o WCF-SAP para enviar mensajes al sistema SAP se están ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud para la orquestación. Vea [esquemas de mensaje para operaciones de tRFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md) saber acerca del esquema del mensaje de solicitud para invocar un tRFC en un sistema SAP. Por ejemplo, el mensaje de solicitud para invocar BAPI_SALEASORDER_CREATEFROMDAT2 como un tRFC es:  
  
```  
<BAPI_SALESORDER_CREATEFROMDAT2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Trfc/">  
  <ORDER_HEADER_IN>  
    <DOC_TYPE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">TA</DOC_TYPE>  
    <SALES_ORG xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">1000</SALES_ORG>  
    <DISTR_CHAN xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">10</DISTR_CHAN>  
    <DIVISION xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">00</DIVISION>  
    <SALES_OFF xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">1000</SALES_OFF>  
    <REQ_DATE_H xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006-09-01T23:50:00</REQ_DATE_H>  
    <PURCH_DATE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006-08-25T23:50:00</PURCH_DATE>  
    <PURCH_NO_C xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">Cust PO</PURCH_NO_C>  
    <CURRENCY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">EUR</CURRENCY>  
  </ORDER_HEADER_IN>  
  <ORDER_ITEMS_IN>  
    <BAPISDITM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <MATERIAL>P-109</MATERIAL>  
      <PLANT>1000</PLANT>  
      <TARGET_QU>ST</TARGET_QU>  
    </BAPISDITM>  
  </ORDER_ITEMS_IN>  
  <ORDER_PARTNERS>  
    <BAPIPARNR xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <PARTN_ROLE>AG</PARTN_ROLE>  
      <PARTN_NUMB>0000001390</PARTN_NUMB>  
    </BAPIPARNR>  
  </ORDER_PARTNERS>  
  <RETURN/>  
  <TransactionalRfcOperationIdentifier>def689b1-b514-4627-a861-d6d7f51c84e3</TransactionalRfcOperationIdentifier>  
</BAPI_SALESORDER_CREATEFROMDAT2>  
```  
  
 La orquestación consume el mensaje, lo pasa al sistema SAP y recibe una respuesta desde el sistema SAP. El mensaje de respuesta se guarda en la otra ubicación de archivo especificada como parte de la orquestación. La respuesta desde el sistema SAP contiene un GUID. La orquestación, a continuación, genera otro mensaje de solicitud de la respuesta y lo pasa al sistema SAP para ejecutar el RfcConfirmTransID. Después de recibir la respuesta desde el sistema SAP para la operación de RfcConfirmTransID, se copia en la ubicación del archivo. Para resumir, después de la operación se ejecuta correctamente:  
  
-   Un mensaje de respuesta de SAP para invocar el tRFC se copia en la ubicación del archivo. Contiene el mismo GUID que se envió al sistema SAP. El mensaje de respuesta invocando BAPI_SALESORDER_CREATEFROMDAT2 como un tRFC es:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <BAPI_SALESORDER_CREATEFROMDAT2Response xmlns="http://Microsoft.LobServices.Sap/2007/03/Trfc/">  
      <TransactionalRfcOperationIdentifier>def689b1-b514-4627-a861-d6d7f51c84e3</TransactionalRfcOperationIdentifier>  
    </BAPI_SALESORDER_CREATEFROMDAT2Response>  
    ```  
  
-   Un mensaje de respuesta para el RfcConfirmTransID se copia en la misma ubicación. Se trata de una respuesta vacía. El mensaje de respuesta para la RfcConfirmTransID es:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <RfcConfirmTransIDResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/RfcApi/"></RfcConfirmTransIDResponse>  
    ```  
  
> [!NOTE]
>  Puede usar el **ConvertGuidToTid()** método público expuesto por el ensamblado de adaptador SAP para recuperar el TID en el sistema SAP asignado al GUID del servicio. Para obtener más información, consulte [operaciones especiales](../../adapters-and-accelerators/adapter-sap/special-operations.md).  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones que puede surgir al invocar un tRFC en un sistema SAP mediante BizTalk Server, vea [excepciones y control de errores con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlaces. Una vez que se genera un archivo de enlaces, puede importar los valores de configuración desde el archivo para que no es necesario crear los puertos de envío, recepción, puertos, etc. para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador SAP reutilizar](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)