---
title: Enviar los IDOC a SAP con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, sample for sending
- IDOCs, sending to SAP using BizTalk Server
- IDOCs, business scenarios for sending
ms.assetid: 92042623-ffbf-472f-9515-e9a77eb320fb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ca8464af7002fe7863246dc440a4da27ee23e1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970325"
---
# <a name="send-idocs-to-sap-using-biztalk-server"></a>Enviar los IDOC a SAP con BizTalk Server
Todas las llamadas IDOC a SAP internamente se tratan como llamadas de tRFC donde el adaptador actúa como un cliente tRFC y llama a una solicitud de cambio de SAP para enviar un IDOC. Esta sección proporciona información sobre el envío de IDOC a SAP mediante el uso de la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone dos operaciones diferentes para enviar los IDOC:  

- **Enviar** operación permite que los clientes del adaptador enviar los IDOC que tengan un esquema fuertemente tipado.  

- **SendIdoc** operación permite que los clientes del adaptador enviar los IDOC que tengan un esquema débilmente tipada. Con esto, los clientes del adaptador pueden enviar los IDOC de archivo sin formato al sistema SAP. El IDOC de archivo sin formato completo sería un valor de nodo en un mensaje SendIdoc XML.  

  Para obtener más información acerca de cómo los [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite el envío de IDOC a un sistema SAP, consulte [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md). Para obtener más información sobre la estructura de SOAP de los mensajes para enviar un IDOC, consulte [esquemas de mensaje para operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).  

## <a name="biztalk-scenarios-for-sending-idocs-with-the-sap-adapter"></a>Escenarios de BizTalk para enviar los IDOC con el adaptador de SAP  
 En la tabla siguiente proporciona escenarios clave de BizTalk para enviar los IDOC a un sistema SAP:  


|       Entrada de BizTalk        |                                                                                                                                                                                                                                                                                                                 Procesamiento de BizTalk                                                                                                                                                                                                                                                                                                                  | Salida de adaptador |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
|        IDOC de archivo sin formato         |                                                         **Tiempo de diseño de metadatos**<br /><br /> 1.  Establezca la propiedad binding GenerateFlatFileCompatibleIdocSchema a **True**.<br />2.  Generar el esquema para el **enviar** operación para un uso específico de IDOC [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].<br /><br /> **Tiempo de diseño de orquestación**<br /><br /> 1.  Recibir IDOC de archivo sin formato<br />2.  Usar el Desensamblador de archivo sin formato para convertir el IDOC de archivo sin formato a XML IDOC mediante el esquema que se acaba de generar.<br />3.  Establezca la acción en **enviar** operación.                                                         |   Enviar mensaje    |
|        IDOC de archivo sin formato         | **Tiempo de diseño de metadatos**<br /><br /> 1.  Establezca la propiedad binding GenerateFlatFileCompatibleIdocSchema a **True**.<br />2.  Generar el esquema para el **SendIdoc** operación desde el nodo IDOC mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].<br /><br /> **Tiempo de diseño de orquestación**<br /><br /> 1.  Recibir IDOC de archivo sin formato<br />2.  Usar el Desensamblador de archivo sin formato para convertir el IDOC de archivo sin formato a XML (en este caso, el mensaje XML contiene un \<idocData\> nodo que contiene todo el mensaje de archivo sin formato Idoc) mediante el esquema que se acaba de generar.<br />3.  Establezca la acción en **SendIdoc** operación. | Mensaje SendIdoc  |
|           IDOC DE XML            |                                                                                                                                                           **Tiempo de diseño de metadatos**<br /><br /> -Generar el esquema para el **enviar** operación para un uso específico de IDOC [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].<br /><br /> **Tiempo de diseño de orquestación**<br /><br /> 1.  Recibir IDOC de XML.<br />2.  Establezca la acción en **enviar** operación.                                                                                                                                                           |   Enviar mensaje    |
| IDOC de archivo sin formato en el mensaje XML |                                                                                                                                                      **Tiempo de diseño de metadatos**<br /><br /> -Generar el esquema para el **SendIdoc** operación desde el nodo IDOC mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].<br /><br /> **Tiempo de diseño de orquestación**<br /><br /> 1.  Recibir mensaje XML.<br />2.  Establezca la acción en **SendIdoc** operación.                                                                                                                                                      | Mensaje SendIdoc  |

## <a name="how-to-send-an-idoc-to-an-sap-system"></a>Cómo enviar un IDOC a un sistema SAP  
 Realizar una operación en un sistema SAP mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md). Para enviar un IDOC a un sistema SAP, estas tareas son:  

1. Cree un proyecto de BizTalk y generar el esquema para el IDOC que desea invocar en el sistema SAP. Al generar el esquema Asegúrese de establecer las propiedades de enlace necesaria, como se muestra en la tabla anterior. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).  

2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes desde el sistema SAP.  

3. Crear una orquestación para enviar un IDOC a un sistema SAP.  

4. Compile e implemente el proyecto de BizTalk.  

5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  

6. Inicie la aplicación de BizTalk.  

   Este tema proporciona instrucciones para realizar estas tareas.  

## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, IDOCSend, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador SAP ](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).  

## <a name="generating-schema"></a>Generar el esquema  
 Este tema muestra cómo enviar un IDOC a un sistema SAP mediante la generación de esquema para el *enviar* operación bajo \IDOC\ORDERS\ORDERS05\ORDERS05. V3(620) IDOC. Consulte [examinar, buscar y obtener metadatos para operaciones de IDOC en SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-idoc-operations-in-sap.md) para obtener más información acerca de cómo generar el esquema para un IDOC determinado.  

## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la vista de orquestación de BizTalk del proyecto.  

 Este tema, debe crear dos mensajes: uno para enviar un IDOC al sistema SAP y otro para recibir una respuesta.  

 Realice los pasos siguientes para crear mensajes y vincularlas al esquema:  

#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  

1.  Abra la vista de orquestación del proyecto de BizTalk, si no está abierto. Haga clic en **vista**, apunte a **Other Windows**y haga clic en **Vista orquestación**.  

2.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  

3.  Haga clic en la recién cree el mensaje y seleccione **ventana propiedades**.  

4.  En el **propiedades** panel **Message_1**, realice lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **IDOCSend**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *IDOCSend.SAPBindingSchema3*, donde *IDOCSend* es el nombre de su proyecto de BizTalk. *SAPBindingSchema3* es el esquema generado para la operación de envío.|  

5.  Repita el paso anterior para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **IDOCResponse**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *IDOCSend.SAPBindingSchema4*.|  

## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para enviar los IDOC a un sistema SAP. En esta orquestación, se puede quitar un archivo sin formato IDOC en una determinada ubicación de recepción. Este archivo se convierte en un mensaje de solicitud XML con un desensamblador de archivo sin formato. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] consume este mensaje y lo pasa al sistema SAP. La respuesta con un GUID se recibe de SAP y se guarda en otra ubicación. Debe incluir el envío y recepción formas para enviar los IDOC al sistema SAP y recibir respuestas. También debe incluir un desensamblador de archivo sin formato para convertir un archivo sin formato en un archivo XML. Contendrían una orquestación típica para enviar e IDOC a un sistema SAP:  

- Enviar y recibir las formas para enviar mensajes al sistema SAP y recibir respuestas.  

- Puerto para recibir los IDOC de archivo sin formato para enviar al sistema SAP de recepción unidireccional.  

- Un desensamblador de archivo sin formato para convertir el IDOC de archivo sin formato en un archivo XML.  

- Puerto para enviar el IDOC al sistema SAP y recibir respuestas de envío bidireccional.  

- Un puerto de envío unidireccional para enviar las respuestas desde el sistema SAP en una carpeta.  

  Una orquestación de ejemplo tendría un aspecto similar al siguiente:  

  ![Orquestación para enviar los IDOC a SAP](../../adapters-and-accelerators/adapter-sap/media/db1490c8-da52-4af3-8a4f-d93bd815025d.gif "db1490c8-da52-4af3-8a4f-d93bd815025d")  

### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  

|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveFile|Receive|-Establecer **nombre** a *ReceiveFile*<br />-Establecer **activar** a *True*|  
|SendToLOB|Send|-Establecer **nombre** a *SendToLOB*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  

### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la *puerto* columna son los nombres de los puertos tal como se muestra en la orquestación.  

|Puerto|Propiedades|  
|----------|----------------|  
|FileIn|-Establecer **identificador** a *FileIn*<br />-Establecer **tipo** a *FileInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SaveResponse|-Establecer **identificador** a *SaveResponse*<br />-Establecer **tipo** a *SaveResponseType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  

### <a name="adding-a-flat-file-disassembler"></a>Agregar un desensamblador de archivos  
 Debe agregar un desensamblador de archivos a la orquestación para convertir el IDOC de archivo sin formato en un formato XML.  

##### <a name="to-add-a-flat-file-disassembler"></a>Para agregar un desensamblador de archivos  

1.  Haga clic en el proyecto de BizTalk, seleccione **agregar**y seleccione **nuevo elemento**.  

2.  En el cuadro de diálogo, haga lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |Categorías|Archivos de canalización|  
    |Plantillas instaladas de Visual Studio|Canalización de recepción|  
    |Nombre|IDOCReceive|  

3.  Se abrirá el Diseñador de canalizaciones. Desde el **componentes de canalización de BizTalk** herramientas, arrastre el **Desensamblador de archivos** componente de canalización en el **desensamblar** fase de la canalización de recepción.  

4.  Desde el **propiedades de componente de canalización** ver, especifique un valor para el **esquema de documento** propiedad. En la lista desplegable, asegúrese de que seleccionar el esquema correspondiente a la operación de envío IDOC.  

## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especifique los mensajes para las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores se establezcan para especificar los mensajes de las formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  

|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveFile|-Establecer **mensaje** a *IDOCSend*<br />-Establecer **operación** a *FileIn.SendIDOC.Request*|  
|SendToLob|-Establecer **mensaje** a *IDOCSend*<br />-Establecer **operación** a *LOBPort.SendIDOC.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *IDOCResponse*<br />-Establecer **operación** a *LOBPort.SendIDOC.Response*|  
|SendResponse|-Establecer **mensaje** a *IDOCResponse*<br />-Establecer **operación** a *SaveResponse.SendIDOC.Request*|  

 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  

 Ahora debe compilar la solución de BizTalk e implementarla en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).

## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [cómo configurar una aplicación](../../core/how-to-configure-an-application.md).

 Configuración de una aplicación implica:  

- Selección de un host de la aplicación.  

- Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para esta orquestación, debe:  

  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarlo al sistema SAP.  

    > [!IMPORTANT]
    >  Para la canalización XMLReceive para este puerto, asegúrese de seleccionar ***IDOCReceive***. Ha creado esta canalización como parte del proyecto de BizTalk.  

  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta desde el sistema SAP.  

  - Definir un puerto de envío WCF-Custom o WCF SAP físico para enviar mensajes al sistema SAP. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).

    > [!NOTE]
    >  También puede establecer el *AutoConfirmSentIdocs* enlaza la propiedad para confirmar los IDOC automáticamente en el sistema SAP. Si lo hace, no es necesario llamar explícitamente a la operación RfcConfirmTransID para confirmar el IDOC. Para obtener más información acerca de la propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md). Para obtener más información acerca de la operación RfcConfirmTransID, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
    > 
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).

## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para enviar un IDOC al sistema SAP. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md), o [cómo iniciar una aplicación](../../core/how-to-start-and-stop-a-biztalk-application.md).

 En esta etapa, asegúrese de que:  

-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  

-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  

-   El puerto de envío WCF-Custom o WCF-SAP para enviar mensajes al sistema SAP se está ejecutando.  

-   La orquestación de BizTalk para la operación se está ejecutando.  

## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud para la orquestación. En este ejemplo, se quitará un IDOC de archivo sin formato definido en el archivo de la ubicación de recepción. Las siguientes acciones tienen lugar después de colocar el mensaje de solicitud:  

- La orquestación toma este IDOC de archivo sin formato y lo convierte en el mensaje de solicitud XML, el esquema para el que se ajusta al esquema generado anteriormente.  

- Si el mensaje de solicitud proporcionado contiene un GUID, el adaptador genera una transacción TID (Id.) y lo envía al sistema SAP.  

- Si el mensaje de solicitud que ha proporcionado no contiene un GUID, el adaptador genera un GUID y utiliza ese GUID para generar un TID. El TID, a continuación, se envía al sistema SAP.  

  En ambos casos, el mensaje de respuesta desde el sistema SAP contiene un GUID. Por ejemplo, un mensaje de respuesta para la operación de envío en el IDOC ORDERS05 es:  

```  
<?xml version="1.0" encoding="utf-8"?>  
<SendResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send">  
  <guid>a5afe162-d5cc-47b0-bf6f-3b0bfe06a97e</guid>  
</SendResponse>  
```  

 Una vez que reciba el GUID debe invocar el **RfConfirmTransID** operación para confirmar el TID. Para obtener más información sobre la **RfcConfirmTransID** operación, vea [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md). Puede crear una nueva orquestación para llamar a esta operación o modificar la orquestación existente. Si desea crear una nueva orquestación, será similar a cualquier otra orquestación en un sistema SAP. Si desea actualizar la orquestación existente, consulte [invocar trfc de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md). La orquestación para invocar un tRFC, tal como se describe en el tema muestra cómo llamar a un **RfcConfirmTransID** operación desde la misma orquestación.  

> [!NOTE]
>  No debe invocar la operación RfcConfirmTransID si establece la *AutoConfirmSentIdocs* enlazar la propiedad a **True**.  

## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones que puede surgir al enviar un IDOC a un sistema SAP mediante BizTalk Server, vea [excepciones y control de errores con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).  

## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlaces. Cuando genere un archivo de enlaces, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío, recepción, puertos, etc., de la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [enlaces del adaptador SAP reutilizar](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).

## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)