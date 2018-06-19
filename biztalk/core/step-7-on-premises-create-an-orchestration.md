---
title: 'Paso 7 (de forma local): Crear una orquestación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c0b6d0e-cf00-4eee-9b89-28210bad46f4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b92a641252a76f4668cdf4c96c8df442c43d4719
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280228"
---
# <a name="step-7-on-premises-create-an-orchestration"></a>Paso 7 (de forma local): Crear una orquestación
Según el escenario empresarial, después [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe el mensaje de pedido de ventas de la cola de Bus de servicio, debe comprobar si la cantidad pedida en el mensaje es mayor que 100. Si la cantidad es mayor que 100, el mensaje se inserta en la **SalesOrder** tabla. En caso contrario, el mensaje se envía a una ubicación de archivos compartidos. Northwind consigue su lógica de negocios creando una orquestación. Este tema proporciona instrucciones paso a paso sobre cómo crear la orquestación.  
  
### <a name="to-add-an-orchestration-to-the-includebtsbiztalkservernoversionincludesbtsbiztalkservernoversion-mdmd-project"></a>Para crear una orquestación en el proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ya ha creado, haga clic en el proyecto y seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **nuevo elemento** cuadro de diálogo, seleccione **orquestación de BizTalk**, escriba el nombre de asignación `OrderProcessing.odx`y, a continuación, haga clic en **agregar**.  
  
## <a name="create-messages-for-the-orchestration"></a>Crear mensajes para la orquestación  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Normalmente, un mensaje es una variable cuyo tipo está definido por el esquema correspondiente. Ahora debe crear mensajes para la orquestación y vincularlos a los esquemas que ha generado anteriormente. Necesita crear los tres mensajes siguientes:  
  
|Nombre del mensaje|Corresponde al esquema|  
|------------------|---------------------------|  
|Message1_SO_Inbound|Este mensaje es una instancia de la **ECommerceSalesOrder.xsd** esquema.|  
|Message2_SO_Inbound|Este mensaje es una copia de la **Message1_SO_Inbound**. Como práctica recomendada, debe crear una copia del mensaje, modificar después el nuevo mensaje y dejar el mensaje original intacto. Para obtener más información, consulte [el mensaje de BizTalk Server](http://msdn.microsoft.com/library/aa560436).|  
|Message1_SO_Outbound|Este mensaje es una instancia de la **TableOperations.dbo.SalesOrder (inserción)** esquema.|  
  
#### <a name="to-create-the-messages"></a>Para crear mensajes  
  
1.  Abra la **Vista orquestación** ventana del proyecto de BizTalk, si no está ya abierto. Para ello, haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
2.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel para la **Message_1**, realice lo siguiente:  
  
    |Nombre de la propiedad|Realizar acción|  
    |-------------------|--------------------|  
    |Identificador|Escriba`Message1_SO_Inbound`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *OrderProcessingDemo.ECommerceSalesOrder*, donde *OrderProcessingDemo* es el nombre de su BizTalk proyecto. *ECommerceSalesOrder* es el esquema para el mensaje de pedido de ventas recibido desde la cola de Bus de servicio.|  
  
5.  Repita los pasos para crear los mensajes con los siguientes detalles:  
  
    |Nombre del mensaje||  
    |------------------|-|  
    |Message2_SO_Inbound|-Establecer **identificador** a`Message2_SO_Inbound`<br />-Establecer **tipo de mensaje** a *OrderProcessingDemo.ECommerceSalesOrder*|  
    |Message1_SO_Outbound|-Establecer **identificador** a`Message1_SO_Outound`<br />-Establecer **tipo de mensaje** a *OrderProcessingDemo.TableOperation_dbo_SalesOrder.Insert*|  
  
## <a name="add-shapes-to-the-orchestration"></a>Agregar formas a la orquestación  
 Las formas de la orquestación definen el flujo de una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En esta sección, se agregan las formas necesarias a la orquestación.  
  
#### <a name="to-add-shapes-to-the-orchestration"></a>Para agregar formas a la orquestación  
  
1.  Para empezar, debe agregar una **recepción** forma. Esta forma recibe el mensaje del pedido de ventas entrante desde la cola del Service Bus. Establezca las siguientes propiedades en la forma de recepción.  
  
    1.  Establecer **activar** a **True**.  
  
    2.  Establecer **mensaje** a **Message1_SO_Inbound**.  
  
    3.  Establecer **nombre** a **ReceiveOrder**.  
  
2.  Como se ha mencionado anteriormente, debe crear una copia del mensaje del pedido de ventas original que se recibe en la orquestación.  
  
    1.  Arrastrar y colocar un **construir mensaje** forma bajo la **ReceiveOrder** forma. Dado que esta forma se usa para construir un mensaje de tipo Message2_SO_Inbound, establezca el **mensajes construidos** propiedad **Message2_SO_Inbound**.  
  
    2.  Agregar un **asignación de mensajes** forma dentro de la **construir mensaje** forma. Haga doble clic en la forma para abrir el Editor de expresiones y agregue lo siguiente:  
  
        ```  
        Message2_SO_Inbound = Message1_SO_Inbound; //copy the message  
        Message2_SO_Inbound(*) = Message1_SO_Inbound(*); //copy the context properties on the message  
        ```  
  
         Haga clic en **Aceptar**.  
  
3.  Según el escenario de negocio, el mensaje se debe enviar a distintos destinos en función de la cantidad de elementos pedidos. Por lo tanto, ahora debe extraer el valor de cantidad del mensaje del pedido de ventas entrante.  
  
    1.  El **cantidad** elemento en el mensaje entrante (ECommerceSalesOrder.xsd) contiene el valor de la cantidad pedida. Debe promocionar esta propiedad para que el elemento se pueda usar en las expresiones de la orquestación. Para promover la propiedad, abra el **ECommerceSalesOrder.xsd** esquema, haga clic en **cantidad**, seleccione **promover**y, a continuación, haga clic en **promoción rápida** .  
  
    2.  Cree una variable para almacenar el valor de la cantidad. Para crear una variable, desde el **Vista orquestación**, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**. Establezca las siguientes propiedades de la variable:  
  
        |Nombre de la propiedad|Valor|  
        |-------------------|-----------|  
        |Identificador|Escriba`quantityOrdered`|  
        |Tipo|Seleccione **Int32**.|  
  
    3.  Ahora debe asignar el valor de la **cantidad** elemento a la **quantityOrdered** variable. Arrastrar y colocar un **Editor de expresiones** después de la **construir mensaje** forma. Abra el editor y escriba la siguiente expresión.  
  
        ```  
        quantityOrdered = Message2_SO_Inbound.Quantity;  
        ```  
  
         Haga clic en **Aceptar**.  
  
4.  Después de extraer la cantidad del pedido, ahora necesita crear un bloque de decisiones donde distribuir las dos rutas separadas que toma el flujo de mensajes. Crear el bloque de decisiones en una orquestación mediante la adición de un **decidir** forma.  
  
    1.  Arrastre y coloque una **decidir** forma después de la **Editor de expresiones** forma.  
  
    2.  Seleccione el **Rule_1** forma y en el **propiedades** ventana, especifique lo siguiente:  
  
        |Nombre de la propiedad|Valor|  
        |-------------------|-----------|  
        |Identificador|Escriba `Yes`. **Nota:** es la otra ruta predeterminada denominada **Else**.|  
        |Expresión|Escriba `quantityOrdered > 100`.|  
  
         Ahora las dos rutas están disponibles. Si el valor de la **quantityOrdered** variable es mayor que 100, el mensaje tiene el **Sí** ruta. De lo contrario, mantiene la **Else** ruta. Ahora hay que definir las acciones que se realizarán en cada ruta.  
  
5.  Según el escenario de negocio, si la cantidad del pedido es superior a 100, el mensaje se debe insertar en la tabla SalesOrder. Por lo tanto, en la **Sí** ruta, debe transformar el esquema ECommerceSalesOrder.xsd en el esquema TableOperations.SalesOrder.Insert. Ha creado el esquema de inserción en el tema [(local) del paso 5: generar el esquema para insertar un mensaje en la tabla SalesOrder](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md). Después de transformar el esquema, debe enviar el mensaje fuera a la tabla de base de datos de SQL Server.   
  
    1.  En el **Sí** de ruta, arrastre y coloque una **construir mensaje** forma. Establecer el **mensajes construidos** propiedad para la forma en **Message1_SO_Outbound**.  
  
    2.  En el **construir mensaje** agregar de forma un **transformar** forma. Haga doble clic en la forma para abrir el **configuración de transformación** cuadro de diálogo. Realice lo siguiente:  
  
        1.  Seleccione el **mapa existente** opción.  
  
        2.  Desde el **nombre completo de asignación** lista desplegable, seleccione **OrderProcessingDemo.SalesOrder_SQL**.  
  
        3.  Para **origen**, seleccione **Message2_SO_Inbound**.  
  
        4.  Para **destino**, seleccione **Message1_SO_Outound**.  
  
    3.  Después de la **construir mensaje** forma, arrastre y coloque una **enviar** forma y establezca el **mensaje** propiedad para la forma en `Message1_SO_Outbound`.  
  
6.  Según el escenario de negocio, si la cantidad del pedido es inferior a 100, el mensaje se debe enviar a una ubicación de archivos compartidos. Por lo tanto, en la **Else** ruta debe agregar una forma de envío.  
  
    1.  En el **Else** de ruta, arrastre y coloque una **enviar** forma y establezca el **mensaje** propiedad para la forma en `Message2_SO_Inbound`.  
  
        > [!NOTE]
        >  Se establece el mensaje en Message2_SO_Inbound porque el mismo mensaje que se recibe de la cola del Service Bus se envía a la ubicación de archivos sin procesamiento. Message2_SO_Inbound representa el mensaje que recibe la cola del Service Bus.  
  
## <a name="add-ports-to-the-orchestration"></a>Agregar puertos a la orquestación  
 Los puertos representan los medios de entrada y de salida del mensaje con respecto a una orquestación. Los mensajes son consumidos por la orquestación usando un puerto de recepción y se envían usando un puerto de envío.  En el escenario de negocio, un mensaje se recibe de un medio (cola del Service Bus) y se envía a dos ubicaciones distintas (base de datos de SQL Server o ubicación de recurso compartido de archivos) según el procesamiento del mensaje. Por lo tanto, debe crear un puerto de recepción y dos puertos de envío como parte de la orquestación.  
  
#### <a name="to-add-ports"></a>Para agregar puertos  
  
1.  Arrastre y coloque un **puerto** dar forma a la **superficie para el puerto** panel de la **Diseñador de orquestaciones** para iniciar el **Asistente para configuración de puerto**. En el **bienvenida** página, haga clic en **siguiente**.  
  
2.  En el **propiedades de puerto** página, asigne nombre al puerto de `ReceiveSO` y, a continuación, haga clic en **siguiente**.  
  
3.  En el **seleccionar un tipo de puerto** , seleccione **crear un nuevo tipo de puerto** opción, seleccione la **unidireccional** comunicación de patrón, deje el valor predeterminado para las restricciones de acceso y, a continuación, Haga clic en **siguiente**.  
  
4.  En el **enlace de puerto** página, para la dirección de puerto, seleccione **siempre recibiré los mensajes en este puerto**, deje el enlace del puerto en el valor predeterminado y, a continuación, haga clic en **siguiente**.  
  
5.  En la última página, haga clic en **finalizar**.  
  
6.  Repita los pasos para crear los dos puertos de envío. Especifique los siguientes valores cuando cree los puertos.  
  
    |Nombre de puerto|Propiedades|  
    |---------------|----------------|  
    |SendToSQL|-Establecer **nombre** a **SendToSQL**<br />-Seleccione **crear un nuevo tipo de puerto**<br />: Patrón de comunicación conjunto a **unidireccional**<br />: Establecer la dirección de puerto en **siempre enviaré los mensajes en este puerto**|  
    |SendToFile|-Establecer **nombre** a **SendToFile**<br />-Seleccione **crear un nuevo tipo de puerto**<br />: Patrón de comunicación conjunto a **unidireccional**<br />: Establecer la dirección de puerto en **siempre enviaré los mensajes en este puerto**|  
  
## <a name="connect-ports-and-message-shapes"></a>Conectar puertos y formas de mensaje  
 Ahora debe conectar los puertos y las formas de mensaje para completar la orquestación. La orquestación se inicia cuando se recibe el mensaje por la **ReceiveOrder** forma y finaliza cuando se envía el mensaje de las dos formas de envío. Debe usar este criterio para conectar los puertos y las formas del mensaje.  
  
#### <a name="to-connect-ports-with-message-shapes"></a>Para conectar puertos a las formas de mensaje  
  
1.  Conectar el **ReceiveSO** puerto de recepción para el **ReceiveOrder** forma.  
  
2.  Conecte la forma envío bajo la **Sí** enrutar a la **SendToSQL** puerto de envío. Esto denota que si un mensaje especifica esta ruta (**quantityOrdered** > 100), se enviará a la **SalesOrder** tabla en la base de datos de SQL Server.  
  
3.  Conecte la forma envío bajo la **Else** enrutar a la **SendToFile** puerto de envío. Esto denota que si un mensaje especifica esta ruta (**quantityOrdered** < = 100), se enviará a una ubicación de archivo especificado.  
  
     La orquestación debe tener el siguiente aspecto:  
  
     ![Orquestación](../core/media/bts2010r2-tut1-orch.jpg "BTS2010R2_Tut1_Orch")  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)