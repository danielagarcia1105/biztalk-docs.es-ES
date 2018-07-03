---
title: Ejecutar transacciones de BAPI de SAP con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ff5cf7-5e98-4d74-a13f-4de65c215d41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67614e9ec07a2e675c0972ad4ea3429266726b56
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978677"
---
# <a name="run-bapi-transactions-in-sap-using-biztalk-server"></a>Ejecutar transacciones de BAPI de SAP con BizTalk Server
El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] permite a los clientes del adaptador realizar transacciones en un sistema SAP mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Antes de crear una orquestación para una transacción, debe entender primero un escenario básico en el que se realizarán las transacciones. En un escenario típico de transacción, se envía un mensaje de solicitud con varias operaciones (como la invocación de un BAPI) al sistema SAP. Esto se hará referencia a como un "mensaje de operación". La orquestación debe extraer de cada mensaje de operación del mensaje de solicitud y enviar los mensajes de operación individual al sistema SAP. La orquestación envía uno tras otro con la misma conexión. La orquestación extrae los mensajes individuales desde el mensaje"operación" mediante una transformación XML a través de una asignación de BizTalk.  
  
 Una vez realizadas las operaciones, la orquestación debe confirmar o anular la transacción mediante el envío de mensajes para BAPI_TRANSACTION_COMMIT o BAPI_TRANSACTION_ROLLBACK, respectivamente. Estos se hará referencia a como "mensajes de transacción".  
  
## <a name="how-does-the-adapter-enable-transactions-through-biztalk-server"></a>¿Cómo habilitar el adaptador las transacciones a través de BizTalk Server?  
 Para permitir transacciones en un sistema SAP mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- Proporciona las propiedades de contexto de mensaje se abra, volver a usar, cierre y anularán.  
  
- Usa BAPI_TRANSACTION_COMMIT y BAPI_TRANSACTION_ROLLBACK para confirmar o anular las operaciones. Estos se exponen por el sistema SAP.  
  
  En la tabla siguiente se enumera algunas directrices sobre el uso de las propiedades con BAPI_TRANSACTION_COMMIT o BAPI_TRANSACTION_ROLLBACK:  
  
|de mensaje|OPEN|VOLVER A USAR|CLOSE|ABORT|  
|-------------|----------|-----------|-----------|-----------|  
|Primer mensaje (mensaje de operación)|Sí|no|no|no|  
|Subsiguientes mensajes (operación)|no|Sí|no|no|  
|BAPI_TRANSACTION_COMMIT (mensaje de la transacción)|no|no|Sí|no|  
|BAPI_TRANSACTION_ROLLBACK (mensaje de la transacción)|no|no|Sí|Sí|  
  
 En la tabla, un "Sí" indica la propiedad de contexto de mensaje que se usará para un mensaje. De forma similar, un "No" denota la propiedad de contexto de mensaje no para su uso con un mensaje.  
  
 Para resumir la tabla:  
  
-   El primer mensaje siempre debe ser un mensaje de operación y solo debe usar la propiedad abierta.  
  
-   Los mensajes de operación posterior deben usar la propiedad de reutilización.  
  
-   El mensaje de la transacción correspondiente BAPI_TRANSACTION_COMMIT para confirmar la transacción debe usar la propiedad cerrar.  
  
-   El mensaje de la transacción correspondiente a BAPI_TRANSACTION_ROLLBACK para anular la transacción puede usar las propiedades de cierre o anulación. Si usa la anulación, lo ideal es que el mensaje debe ser en el bloque de excepción de la orquestación.  
  
## <a name="key-considerations-related-to-transactions-using-biztalk-server"></a>Consideraciones clave relacionados con las transacciones con BizTalk Server  
  
- Si hay más de un puerto de envío de una orquestación, el adaptador separa automáticamente la transacción para los mensajes recibidos de cada puerto. Es decir, no puede abarcar una transacción a través de puertos.  
  
- Número de reintentos de mensaje no se admite para los mensajes en una transacción de SAP. Por lo tanto, los usuarios deben establecer el intento de reintento de mensaje en cero.  
  
- El adaptador puede producir resultados no deseados para las combinaciones de marcado como "No" en la tabla anterior. Debe usar combinaciones marcadas como "Sí".  
  
- Los mensajes enviados al adaptador que no tienen una propiedad de contexto de mensaje se ejecutará con normalidad sin que se enlaza con el contexto de transacción actual.  
  
- BAPI_TRANSACTION_COMMIT o BAPI_TRANSACTION_ROLLBACK lo ideal es que debe ser el último mensaje en el contexto de transacción actual en la orquestación.  
  
  Las secciones siguientes proporcionan instrucciones sobre cómo realizar transacciones en SAP utilizando la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="how-to-perform-a-transaction-on-an-sap-system"></a>¿Cómo realizar una transacción en un sistema SAP?  
 Realizar una operación en un sistema SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md). Para llevar a cabo las transacciones en un sistema SAP, estas tareas son:  
  
1. Cree un proyecto de BizTalk y generar el esquema para la solicitud de cambio en el que desea realizar la transacción. Además, debe generar el esquema para BAPI_TRANSACTION_COMMIT y RFC BAPI_TRANSACTION_ROLLBACK.  
  
2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes desde el sistema SAP.  
  
3. Crear una orquestación que extrae los "mensajes de operación" individuales del mensaje de solicitud y lo envía al sistema SAP. Según el mensaje de solicitud, la orquestación también decide si debe confirmar o revertir la transacción.  
  
4. Compile e implemente el proyecto de BizTalk.  
  
5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, SAPTransaction, basado en este tema se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 Para demostrar cómo realizar transacciones en un sistema SAP, necesita los siguientes esquemas:  
  
- Para el mensaje"operación" para realizar operaciones en un sistema SAP. El mensaje de solicitud enviado al adaptador debe ajustarse a este esquema. Puede tratarse de cualquier esquema específica del usuario que contiene cualquier número de nodos de la operación. En este tema, se utiliza el esquema MultipleOrders.xsd. El esquema también se proporciona como parte del ejemplo de la transacción enviada con la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] ejemplos. Para obtener más información, consulte [ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).  
  
- Para llevar a cabo las operaciones en un sistema SAP, como la invocación de una solicitud de cambio. El mensaje de solicitud para realizar una operación debe ajustarse a este esquema. Este esquema debe generarse mediante el uso de la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]. En este tema, se invoca la RFC BAPI_SALESORDER_CREATEFROMDAT2. Para obtener información acerca de cómo generar el esquema RFC, consulte [examinar, buscar y obtener metadatos para operaciones de RFC de SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md).  
  
- Para anular o confirmar una transacción. La solicitud para confirmar o anular una transacción debe ajustarse a este esquema. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa el BAPI_TRANSACTION_COMMIT y RFC BAPI_TRANSACTION_ROLLBACK para confirmación y reversión de las operaciones, respectivamente. Debe generar el esquema para estos RFC mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
> [!NOTE]
>  Debe asegurarse de que todos los esquemas necesarios se agregan al proyecto de BizTalk.  
> 
> [!IMPORTANT]
>  Debe agregar una referencia al esquema de propiedades de BizTalk para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] al proyecto de BizTalk. El archivo de esquema *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*, se instala de forma el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] el programa de instalación, normalmente en \<unidad de instalación\>: \Program Files\Microsoft BizTalk Adapter Pack \Bin.  
  
## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la ventana Vista orquestación del proyecto de BizTalk.  
  
 Antes de crear mensajes, debe determinar el número de nodos de "operación" tiene el mensaje de solicitud (de tipo MultipleOrders.xsd). En este ejemplo, suponga que el mensaje de solicitud tiene dos mensajes de operación para invocar la RFC BAPI_SALESORDER_CREATEFROMDAT2. Por lo tanto, debe crear un conjunto de mensajes de solicitud y respuesta que se asigna al esquema generado para esta RFC.  
  
 Debe crear los siguientes mensajes en el proyecto de BizTalk.  
  
- Un mensaje, SendtoAdapter, para el mensaje de solicitud que se enviará a la orquestación. Este mensaje se debe asignar el esquema para el mensaje de entrada, MultipleOrders.xsd.  
  
- Un mensaje, BAPIMessage, para la primera operación que se envía al sistema SAP. También debe crear un mensaje de respuesta, BAPIResponse, para la respuesta de la primera operación. Los mensajes de solicitud y respuesta deben asignarse al esquema generado para la solicitud de cambio BAPI_SALESORDER_CREATEFROMDAT2.  
  
- Un mensaje, BAPICommitMessage, para la operación de confirmación. También debe crear un mensaje de respuesta, BAPICommitResponse, para el mensaje de respuesta correspondiente. Los mensajes de solicitud y respuesta deben asignarse al esquema de RFC BAPI_TRANSACTION_COMMIT.  
  
- Un mensaje, BAPIRollbackMessage, para la operación de reversión. También debe crear un mensaje de respuesta, BAPIRollbackResponse, para el mensaje de respuesta correspondiente. Los mensajes de solicitud y respuesta deben asignarse al esquema de RFC BAPI_TRANSACTION_ROLLBACK.  
  
  Realice los pasos siguientes para crear mensajes y vincularlas al esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  
  
1.  Abra la vista de orquestación del proyecto de BizTalk, si no está ya abierto. Haga clic en **vista**, apunte a **Other Windows**y haga clic en **Vista orquestación**.  
  
2.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el recién creado el mensaje y, a continuación, seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel **Message_1**, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **SendToAdapter**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *SAPTransaction.MultipleOrders*, donde *SAPTransaction* es el nombre de su proyecto de BizTalk. *MultipleOrders* es el esquema del mensaje de solicitud.|  
  
5.  Repita el paso anterior para crear mensajes de más de seis. En el **propiedades** panel para los mensajes nuevos, haga lo siguiente.  
  
    |Identificador de conjunto para|Establecer el tipo de mensaje en|  
    |-----------------------|-------------------------|  
    |BAPIMessage|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2*|  
    |BAPIResponse|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2Response*|  
    |BAPICommitMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMIT*|  
    |BAPICommitResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMITResponse*|  
    |BAPIRollbackMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACK*|  
    |BAPIRollbackResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACKResponse*|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para realizar transacciones en un sistema SAP. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] consume el mensaje y lo pasa al sistema SAP. La respuesta desde el sistema SAP se guarda en otra ubicación.  
  
 Otra consideración tomar al crear una orquestación es:  
  
- Asignar el esquema del mensaje de solicitud a la de la RFC BAPI_SALESORDER_CREATEFROMDAT2.  
  
- Asignar el esquema del mensaje de solicitud a la de la BAPI_TRANSACTION_COMMIT y RFC BAPI_TRANSACTION_ROLLBACK.  
  
  Puede asignar los esquemas mediante una transformación XML a través de una asignación de BizTalk. Para lograr esto, incluya las formas de transformación en la orquestación.  
  
  Por último, en función de si el mensaje de solicitud tiene información para confirmar o anular la transacción, la orquestación debe decidir el mensaje adecuado para enviarlo al sistema SAP. Para lograr esto, incluya una forma decidir en la orquestación.  
  
  Para obtener más información sobre las diferentes formas incluidas en la orquestación, consulte el **la interfaz de usuario del Diseñador de orquestaciones** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)].
  
  Una orquestación de ejemplo para una transacción de SAP es similar al siguiente.  
  
  ![Orquestaciones para realizar transacciones en SAP](../../adapters-and-accelerators/adapter-sap/media/727f82e9-51a9-4a94-9d0a-d05c17904bde.gif "727f82e9-51a9-4a94-9d0a-d05c17904bde")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveInputXML|Receive|-Establecer **nombre** a *ReceiveInputXML*<br /><br /> -Establecer **activar** a *True*|  
|SendToLOB|Send|-Establecer **nombre** a *SendToLOB*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br /><br /> -Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
 Dado que el mensaje de solicitud tiene dos mensajes de inserción, debe crear otro conjunto de envío y recepción de formas para enviar mensajes a SAP y recibir una respuesta. Sin embargo, dado que es posible que se confirma o revierte los mensajes de inserción, debe crearse el segundo conjunto de formas dentro de un bloque de decisiones. Debe crear un conjunto de formas para confirmar y otro conjunto de formas para la reversión.  
  
> [!NOTE]
>  Puede agregar un bloque de decisiones arrastrando y colocando la forma decidir desde el cuadro de herramientas de orquestaciones de BizTalk.  
  
#### <a name="message-shapes-for-commit"></a>Formas de mensaje para confirmar  
 En la tabla siguiente se enumera las formas para la "ruta de acceso de confirmación" de la orquestación. En este caso, no es necesario crear un mensaje de recepción para un mensaje de solicitud. El mensaje de solicitud se transferirá de la forma de mensaje anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|SendBAPICommit|Send|-Establecer **nombre** a *SendBAPICommit*|  
|ReceiveCommitResponse|Receive|-Establecer **nombre** a *ReceiveCommitResponse*<br /><br /> -Establecer **activar** a *False*|  
|SendResponse2|Send|-Establecer **nombre** a *SendResponse2*|  
  
#### <a name="message-shapes-for-abort"></a>Formas de mensaje para anular  
 En la tabla siguiente se enumera las formas para la "ruta de acceso de reversión" de la orquestación.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|SendBAPIRollback|Send|-Establecer **nombre** a *SendBAPIRollback*|  
|ReceiveRollbackResponse|Receive|-Establecer **nombre** a *ReceiveRollbackResponse*<br /><br /> -Establecer **activar** a *False*|  
|SendResponse3|Send|-Establecer **nombre** a *SendResponse3*|  
  
### <a name="setting-the-rule-expression"></a>Establecer la expresión de regla  
 Incluye las formas de mensaje para la confirmación y anular las operaciones dentro de un bloque de decisiones mediante la adición de una forma decidir. Para especificar la condición en la que la orquestación tomará una decisión, debe especificar una expresión en la forma de regla basada en el que la transacción se confirma o revierte. Por ejemplo, debe especificar la siguiente expresión para la forma de regla:  
  
```  
SendToAdapter.isCommit == true  
```  
  
 Donde, SendToAdapter es el mensaje que ha creado para el esquema del mensaje de solicitud. Por lo tanto, en el mensaje de solicitud, si la `isCommit` etiqueta se establece en **True**, la orquestación toma la ruta "commit". En caso contrario, la orquestación toma la ruta de "reversión".  
  
 Para que pueda especificar esta condición en el editor de expresiones, debe haber promocionado el `isCommit` propiedad en el esquema de mensaje para el mensaje de solicitud enviado al adaptador. Este tema, para usar el esquema de entrada es MultipleOrders.xsd. Debe promocionar la `isCommit` propiedad en este esquema. Para obtener más información acerca de la promoción de una propiedad, vea [promocionar propiedades](../../core/promoting-properties.md).
  
### <a name="adding-construct-message-shapes"></a>Agregar formas de mensaje de construcción  
 Como se explicó anteriormente, el mensaje de solicitud enviado al adaptador contiene insertar dos mensajes y, a continuación, un mensaje de confirmación o anulación. Debe agregar una forma construir mensaje y, en la que dar forma a una transformación para extraer los mensajes de operación individual que se envíen al sistema SAP. También debe agregar una forma asignación de mensajes para establecer el mensaje de las propiedades de contexto para habilitar las transacciones.  
  
#### <a name="the-first-construct-message-shape"></a>La primera forma de construir mensaje  
 Supongamos que la primera forma construir mensaje se denomina "ReceiveXML." De esta forma, especifique la propiedad mensajes construidos como "BAPIMessage". Haga doble clic en la forma transformación para abrir el **configuración de transformación** cuadro de diálogo. En el cuadro de diálogo:  
  
- Elija esta opción para crear una nueva asignación.  
  
- En el panel izquierdo, seleccione **origen** y desde el **nombre de Variable** lista desplegable seleccione *SendToAdapter*.  
  
- En el panel izquierdo, seleccione **destino** y desde el **nombre de Variable** lista desplegable seleccione *BAPIMessage*.  
  
- Haga clic en **Aceptar** para iniciar el asignador. Asignar el esquema del mensaje de solicitud en el esquema de la BAPI_SALESORDER_CREATEFROMDAT2. Puede usar el **índice** functoid para crear una asignación entre lo esquemas de origen y el destino. Un **índice** functoid le permite seleccionar información de un registro específico en una serie de registros.  
  
   La siguiente ilustración muestra los esquemas asignados mediante un **índice** functoid.  
  
   ![Esquemas asignados mediante un functoid de índice](../../adapters-and-accelerators/adapter-sap/media/d0ade577-ea74-4be3-a724-4ba19397d8d3.gif "d0ade577-ea74-4be3-a724-4ba19397d8d3")  
  
   Para obtener más información sobre el uso de la **configuración de transformación** cuadro de diálogo, vea el **cuadro de diálogo de configuración de transformación** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)].
  
   Para obtener más información sobre cómo usar el functoid de índice, vea [el Functoid de índice](../../core/index-functoid.md).
       
   Después de asignar los esquemas, puede probar la asignación mediante la página de propiedades del archivo de mapa. Para obtener más información, consulte el  **<Map File> cuadro de diálogo página de propiedades, comprobar asignación** ficha [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)].
  
  En la forma asignación de mensajes, especificar la propiedad de contexto de mensaje para iniciar la transacción. Por ejemplo, podría ser la propiedad de contexto de mensaje para el primer mensaje:  
  
```  
BAPIMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "OPEN";  
```  
  
#### <a name="the-commit-construct-message-shape"></a>La forma construir mensaje de confirmación  
 Supongamos que la forma construir mensaje para la operación de confirmación se denomina "CommitMessage." De esta forma, especifique la propiedad mensajes construidos como "BAPICommitMessage". Haga doble clic en la forma transformación para abrir el **configuración de transformación** cuadro de diálogo. En el cuadro de diálogo:  
  
- Elija esta opción para crear una nueva asignación.  
  
- En el panel izquierdo, seleccione **origen** y desde el **nombre de Variable** lista desplegable seleccione *SendToAdapter*.  
  
- En el panel izquierdo, seleccione **destino** y desde el **nombre de Variable** lista desplegable seleccione *BAPICommitMessage*.  
  
- Haga clic en Aceptar para iniciar al asignador. Asignar el esquema del mensaje de solicitud en el esquema de BAPI_TRANSACTION_COMMIT. No necesita incluir un functoid de índice para esta asignación porque el nodo BAPI_TRANSACTION_COMMIT no contiene una jerarquía de registro.  
  
  En la forma asignación de mensajes, especificar la propiedad de contexto de mensaje para confirmar la transacción. Por ejemplo, podría ser la propiedad de contexto de mensaje para el primer mensaje:  
  
```  
BAPICommitMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "CLOSE";  
```  
  
#### <a name="the-rollback-construct-message-shape"></a>La forma construir mensaje de reversión  
 Supongamos que la forma construir mensaje para la operación de reversión se denomina "RollbackMessage." De esta forma, especifique la propiedad mensajes construidos como "BAPIRollbackMessage". Haga doble clic en la forma transformación para abrir el **configuración de transformación** cuadro de diálogo. En el cuadro de diálogo:  
  
- Elija esta opción para crear una nueva asignación.  
  
- En el panel izquierdo, seleccione **origen** y desde el **nombre de Variable** lista desplegable seleccione *SendToAdapter*.  
  
- En el panel izquierdo, seleccione **destino** y desde el **nombre de Variable** lista desplegable seleccione *BAPIRollbackMessage*.  
  
- Haga clic en Aceptar para iniciar al asignador. Asignar el esquema del mensaje de solicitud en el esquema de BAPI_TRANSACTION_ROLLBACK. No necesita incluir un functoid de índice para esta asignación porque el nodo BAPI_TRANSACTION_ROLLBACK no contiene una jerarquía de registro.  
  
  En la forma asignación de mensajes, especificar la propiedad de contexto de mensaje que revierta la transacción. Por ejemplo, podría ser la propiedad de contexto de mensaje para el primer mensaje:  
  
```  
BAPIRollbackMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "ABORT";  
```  
  
> [!IMPORTANT]
>  En escenarios típicos, debe usarse el mensaje correspondiente a BAPI_TRANSACTION_ROLLBACK con la propiedad de contexto de anulación en un bloque de excepción.  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la *puerto* columna son los nombres de los puertos tal como se muestra en la orquestación.  
  
 Para esta orquestación, se crean tres puertos. El primer puerto toma el mensaje de solicitud de una carpeta especificada. El segundo puerto envía los mensajes al sistema SAP y recibe una respuesta. El tercer puerto guardará la respuesta a otra carpeta. Por lo tanto:  
  
-   El primer puerto solo recibe mensajes para un único esquema, es decir, MultipleOrders.xsd.  
  
-   El segundo puerto envía y recibe mensajes para el esquema de RFC BAPI_SALESORDER_CREATEFROMDAT2. Además, se usará el mismo puerto para confirmar o revertir la transacción. Por lo tanto, este puerto también recibe mensajes de esquemas para BAPI_TRANSACTION_COMMIT y RFC BAPI_TRANSACTION_ROLLBACK. Para habilitar esta opción, se crean tres operaciones distintas en este puerto, cada uno correspondiente a un esquema de mensaje específico.  
  
-   Al igual que el segundo puerto, este puerto también recibirá mensajes con tres esquemas diferentes. Por lo tanto, es necesario crear tres operaciones distintas en este puerto.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|FileIn|-Establecer **identificador** a *FileIn*<br /><br /> -Establecer **tipo** a *FileInType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br /><br /> -Establecer **tipo** a *LOBPortType*<br /><br /> -Establecer **patrón de comunicación** a *de solicitud-respuesta*<br /><br /> -Establecer **dirección de comunicación** a *envío y recepción*<br /><br /> -Creación de una operación *BAPIMessage*.<br /><br /> -Creación de una operación *CommitMessage*. Esta operación se utilizará para enviar el mensaje de confirmación.<br /><br /> -Creación de una operación *RollbackMessage*. Esta operación se utilizará para enviar el mensaje de reversión.|  
|SaveResponse|-Establecer **identificador** a *SaveResponse*<br /><br /> -Establecer **tipo** a *SaveResponseType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*.<br /><br /> -Creación de una operación *BAPIMessage*.<br /><br /> -Creación de una operación *CommitMessage*. Esta operación se utilizará para guardar las respuestas para el mensaje de confirmación.<br /><br /> -Creación de una operación *RollbackMessage*. Esta operación se utilizará para guardar las respuestas para el mensaje de reversión.|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especifique los mensajes para las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores se establezcan para especificar los mensajes de las formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveInputXML|-Establecer **mensaje** a *SendToAdapter*<br /><br /> -Establecer **operación** a *FileIn.Transaction.Request*|  
|SendToLOB|-Establecer **mensaje** a *BAPIMessage*<br /><br /> -Establecer **operación** a *LOBPort.BAPIMessage.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *BAPIResponse*<br /><br /> -Establecer **operación** a *LOBPort.BAPIMessage.Response*|  
|SendResponse|-Establecer **mensaje** a *BAPIResponse*<br /><br /> -Establecer **operación** a *SaveResponse.BAPIMessage.Request*|  
|SendBAPICommit|-Establecer **mensaje** a *BAPICommitMessage*<br /><br /> -Establecer **operación** a *LOBPort.CommitMessage.Request*|  
|ReceiveCommitResponse|-Establecer **mensaje** a *BAPICommitResponse*<br /><br /> -Establecer **operación** a *LOBPort.CommitMessage.Response*|  
|SendResponse2|-Establecer **mensaje** a *BAPICommitResponse*<br /><br /> -Establecer **operación** a *SaveResponse.CommitMessage.Request*|  
|SendBAPIRollback|-Establecer **mensaje** a *BAPIRollbackMessage*<br /><br /> -Establecer **operación** a *LOBPort.RollbackMessage.Request*|  
|ReceiveRollbackResponse|-Establecer **mensaje** a *BAPIRollbackResponse*<br /><br /> -Establecer **operación** a *LOBPort.RollbackMessage.Response*|  
|SendResponse3|-Establecer **mensaje** a *BAPIRollbackResponse*<br /><br /> -Establecer **operación** a *SaveResponse.RollbackMessage.Request*|  
  
 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  
  
## <a name="handling-exceptions"></a>Control de excepciones  
 En las orquestaciones complejas como la de realizar transacciones de BAPI, es importante que mantener un seguimiento del estado de la orquestación, informar de errores cuando se producen, para que pueda resolver los problemas cuando se producen. Orquestación de BizTalk proporciona herramientas para controlar los errores, para mantener el estado de una orquestación y solucionar problemas cuando se producen a través de las transacciones, compensación y control de excepciones.  
  
 Como un marco para las transacciones y control de excepciones, el Diseñador de orquestaciones proporciona la **ámbito** forma. Un ámbito puede tener un tipo de transacción, una compensación y cualquier número de controladores de excepción. Un ámbito contiene uno o más bloques. Tiene un cuerpo y, opcionalmente, puede tener cualquier número de bloques de control de excepciones anexado a él. En el caso de las transacciones de BAPI, toda la orquestación (consulte la figura anterior) se puede incluir en un ámbito.  
  
 Para capturar la excepción, debe agregar un **excepción de filtrado** bloque a la orquestación. **Capturar excepción** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones. En el caso de las transacciones de BAPI, debe agregar la rutina de "Anular" para el **excepción de filtrado** en bloques, es decir, debe agregar lo siguiente a la rutina de "Anular":  
  
- Una forma construir mensaje, que consta de una transformación (para extraer el mensaje de solicitud de mensaje de entrada) y una forma asignación de mensajes (para establecer la propiedad de contexto)  
  
- Enviar y recibir las formas.  
  
  El ejemplo de transacciones de SAP para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (SAPTransaction) se incluye con [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] muestra el control de excepciones, demasiado. Para obtener más información sobre el ejemplo, vea [ejemplos para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).  
  
  Para obtener más información acerca de cómo controlar las excepciones, en general, usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [uso de transacciones y controlar excepciones](../../core/using-transactions-and-handling-exceptions.md).
  
## <a name="add-the-biztalk-property-schema-to-biztalk"></a>Agregar el esquema de propiedades de BizTalk a BizTalk  
 En el proyecto de BizTalk, se ha agregado una referencia de ensamblado para el esquema de propiedades de BizTalk para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Debe agregar el mismo ensamblado como un recurso en la aplicación de BizTalk, es decir, la aplicación donde se implementará el proyecto de BizTalk. El archivo de esquema *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*, se instala de forma el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] normalmente por debajo de instalación \<unidad de instalación\>: \Program Files\Microsoft el adaptador de BizTalk Pack\bin. Sin este recurso, no podrá implementar el proyecto.  
  
#### <a name="to-add-an-assembly-as-a-resource-in-biztalk"></a>Para agregar un ensamblado como un recurso en BizTalk  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, la aplicación a la que desea agregar un ensamblado de BizTalk.  
  
3. Haga clic en **recursos**, apunte a **agregar** y, a continuación, haga clic en **ensamblados de BizTalk**.  
  
4. En el **Agregar recurso** cuadro de diálogo, haga clic en **agregar**, navegue hasta la carpeta que contiene el archivo de ensamblado de BizTalk, seleccione el archivo de ensamblado de BizTalk y, a continuación, haga clic en **abierto**.  
  
5. En **opciones**, especifique las opciones para instalar el ensamblado de BizTalk en la GAC y, a continuación, haga clic en **Aceptar**.  
  
   Debe ahora compile la solución de BizTalk y, a continuación, implementarlo en un servidor BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [cómo configurar una aplicación](../../core/how-to-configure-an-application.md).
  
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para esta orquestación, debe:  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarlo al sistema SAP.  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta desde el sistema SAP.  
  
  - Definir un puerto de envío WCF-Custom o WCF SAP físico para enviar mensajes al sistema SAP. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md). Dado que el envío puerto envía y recibe los mensajes sean conformes a más de un esquema y realiza dos operaciones, debe establecer acciones dinámicas para las operaciones. Para obtener más información acerca de las acciones, vea [configurar la acción SOAP para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md). Asegúrese de que se adhiera a las siguientes consideraciones claves durante la creación de un WCF-Custom o WCF SAP puerto de envío para realizar transacciones.  
  
    |Establezca los valores siguientes|En este valor.|  
    |-----------------------|-------------------|  
    |Acción|El puerto de envío envía y recibe mensajes de más de una operación. Por lo tanto, se debe establecer la acción en el puerto de envío para cada operación.<br /><br /> `<BtsActionMapping>   <Operation Name="BAPIMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_SALESORDER_CREATEFROMDAT2" />   <Operation Name="CommitMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_COMMIT" />   <Operation Name="RollbackMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_ROLLBACK" /> </BtsActionMapping>`|  
    |EnableBizTalkCompatibilityMode|Establezca esta propiedad de enlace en **True**.|  
    |EnableConnectionPooling|Establezca esta propiedad de enlace en **False** antes de realizar las transacciones. En escenarios donde el canal configurado entre el adaptador y BizTalk es inesperadamente, se agrega la conexión correspondiente al grupo de conexiones. Cuando se abre otro canal, y el nuevo canal toma el mismo objeto de conexión, las transacciones no confirmadas en el objeto de conexión anterior también se confirmarán cuando se confirman las transacciones a través del canal nuevo. Para evitar esto, debe deshabilitar la agrupación de conexiones al realizar las transacciones.|  
  
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk Server para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).
    > 
    > [!IMPORTANT]
    >  Puede configurar un transporte de copia de seguridad en un WCF-Custom o WCF SAP puerto de envío que le permite enviar mensajes a otro sistema SAP, si el transporte principal no funcione correctamente. Sin embargo, para realizar transacciones en un sistema SAP, basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no admite la especificación de un transporte de copia de seguridad que apunta a otro servidor SAP.  
  
## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar las transacciones de rendimiento de aplicación de BizTalk en un sistema SAP. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md), [cómo iniciar una aplicación](../../core/how-to-start-and-stop-a-biztalk-application.md).
  
 En esta etapa, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-SAP para enviar mensajes al sistema SAP se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud para la orquestación en una ubicación predefinida. El mensaje de solicitud debe ajustarse a un esquema específico, por ejemplo, esquema MultipleOrders.xsd. Por ejemplo, un mensaje de solicitud para crear pedidos de ventas en un sistema SAP y, a continuación confirmar la operación es:  
  
```  
<ns0:Orders xmlns:ns0="http://BAPISend.MultipleOrders">  
  <Order>  
      <ORDER_HEADER_IN>  
        <DOC_TYPE>TA</DOC_TYPE>  
        <SALES_ORG>1000</SALES_ORG>  
        <DISTR_CHAN>10</DISTR_CHAN>  
        <DIVISION>00</DIVISION>  
        <SALES_OFF>1000</SALES_OFF>  
        <REQ_DATE_H>20060901</REQ_DATE_H>  
        <PURCH_DATE>20060901</PURCH_DATE>  
        <PURCH_NO_C>Cust A</PURCH_NO_C>  
        <CURRENCY>EUR</CURRENCY>  
      </ORDER_HEADER_IN>  
      <ORDER_ITEMS_IN>  
          <MATERIAL>P-109</MATERIAL>  
          <PLANT>1000</PLANT>  
          <TARGET_QU>ST</TARGET_QU>  
      </ORDER_ITEMS_IN>  
      <ORDER_PARTNERS>  
          <PARTN_ROLE>AG</PARTN_ROLE>  
          <PARTN_NUMB>0000000257</PARTN_NUMB>  
      </ORDER_PARTNERS>  
    <RETURN></RETURN>  
  </Order>  
  <isCommit>true</isCommit>  
  <BAPI_TRANSACTION_COMMIT>  
  </BAPI_TRANSACTION_COMMIT>  
</ns0:Orders>  
```  
  
 La orquestación consume el mensaje y lo envía al sistema SAP. La respuesta desde el sistema SAP se guarda en otra ubicación de archivo definida como parte de la orquestación. Para el mensaje de solicitud anterior, se obtienen dos mensajes de respuesta, uno para invocar la RFC BAPI_SALESORDER_CREATEFROMDAT2 y otro para la operación de confirmación con BAPI_TRANSACTION_COMMIT.  
  
 La respuesta para BAPI_SALESORDER_CREATEFROMDAT2 es:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<BAPI_SALESORDER_CREATEFROMDAT2Response xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <SALESDOCUMENT />   
  <ORDER_ITEMS_IN>  
    <BAPISDITM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <ITM_NUMBER>0</ITM_NUMBER>   
      <HG_LV_ITEM>0</HG_LV_ITEM>   
      <PO_ITM_NO />   
      ......  
    </BAPISDITM>  
  </ORDER_ITEMS_IN>  
  <ORDER_PARTNERS>  
    <BAPIPARNR xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <PARTN_ROLE>AG</PARTN_ROLE>   
      <PARTN_NUMB>0000000257</PARTN_NUMB>   
      <ITM_NUMBER>0</ITM_NUMBER>   
      ......   
    </BAPIPARNR>  
  </ORDER_PARTNERS>  
</BAPI_SALESORDER_CREATEFROMDAT2Response>  
```  
  
 La respuesta para BAPI_TRANSACTION_COMMIT es:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<BAPI_TRANSACTION_COMMITResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <RETURN>  
    <TYPE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <ID xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <NUMBER xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</NUMBER>   
    <MESSAGE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <LOG_NO xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <LOG_MSG_NO xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</LOG_MSG_NO>   
    <MESSAGE_V1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V3 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V4 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <PARAMETER xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <ROW xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</ROW>   
    <FIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <SYSTEM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
  </RETURN>  
</BAPI_TRANSACTION_COMMITResponse>  
```  
  
> [!NOTE]
>  Si el mensaje de solicitud invoca la RFC BAPI_TRANSACTION_ROLLBACK, será la segunda respuesta para BAPI_TRANSACTION_ROLLBACK.  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones que puede aparecer al realizar las transacciones en un sistema SAP mediante el uso de BizTalk Server, vea [excepciones y control de errores con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlaces. Cuando genere un archivo de enlaces, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío y recepción, para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [enlaces del adaptador SAP reutilizar](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)