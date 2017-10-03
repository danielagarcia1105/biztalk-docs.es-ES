---
title: "Tutorial: Módulo 3: obtener acceso a propiedades de SharePoint desde una orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, orchestrations
- Windows SharePoint Services adapter tutorials, accessing SharePoint properties
ms.assetid: 310c4002-3416-44c6-b409-1d5467063e28
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a44fd7e30bf511ee77cc1f3e79f6ba63908259ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-module-3---accessing-sharepoint-properties-from-an-orchestration"></a>Tutorial: Módulo 3: obtener acceso a propiedades de SharePoint desde una orquestación
En este tutorial es la continuación de [Tutorial: módulo 2: integrar Office con el adaptador de Windows SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) y muestra cómo obtener acceso a las propiedades de un mensaje entrante en el contexto de Windows SharePoint Services tiempo de ejecución y, a continuación, determine el destino del mensaje, en función de una propiedad que utiliza puertos dinámicos en una orquestación. Para obtener una introducción al adaptador de Windows SharePoint Services, vea [¿qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:  
  
-   Debe contar con una implementación de un solo servidor con una instalación completa de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] en ejecución en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].  
  
-   Debe completar los siguientes tutoriales: [Tutorial: módulo 1 – enviar y recibir mensajes con el adaptador de Windows SharePoint Services](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) y [Tutorial: módulo 2: integrar Office con las ventanas Adaptador de SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)  
  
 Para obtener información acerca de cómo utilizar el adaptador de Windows SharePoint Services en una implementación de varios servidores, vea [configurar e implementar el adaptador de Windows SharePoint Services](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).  
  
## <a name="modify-the-biztalk-project"></a>Modificar el proyecto de BizTalk  
 En este procedimiento, modificará el esquema PurchaseOrder de [Tutorial: módulo 2: integrar Office con el adaptador de Windows SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md). En este procedimiento se muestra cómo promocionar una propiedad de esquema para facilitar el acceso en una orquestación de BizTalk.  
  
#### <a name="modify-the-purchaseorderxsd-schema"></a>Modificar el esquema PurchaseOrder.xsd  
  
1.  Iniciar **Microsoft Visual Studio**.  
  
2.  Haga clic en **archivo**, haga clic en **abiertos**y, a continuación, haga clic en **proyecto/solución**.  
  
3.  Vaya a la `OrderProcess.sln` de archivos y, a continuación, haga clic en **abiertos**.  
  
4.  En **el Explorador de soluciones**, haga clic en el `OrderProcessSchema.xsd` de archivos y, a continuación, haga clic en **abiertos**.  
  
5.  En **el Editor de BizTalk**, expanda `PurchaseOrder`.  
  
6.  Haga clic en `Amount`, haga clic en **promover**y, a continuación, haga clic en **promoción rápida**.  
  
7.  Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] crea un esquema de propiedades para esto en el proyecto actual.  
  
8.  Guarde `PurchaseOrder.xsd`.  
  
## <a name="create-an-orchestration"></a>Crear una orquestación  
 En este procedimiento, se creará una nueva orquestación de BizTalk. En él, se crea la orquestación que se utiliza para procesar un mensaje recibido por el adaptador de Windows Sharepoint Services.  
  
#### <a name="add-a-biztalk-orchestration"></a>Agregar una orquestación de BizTalk  
  
1.  En **el Explorador de soluciones**, haga clic en el `OrderProcess` proyecto de equipo y haga clic en **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En **categorías**, seleccione **archivos de orquestación**.  
  
3.  En **plantillas**, seleccione **orquestación de BizTalk**.  
  
4.  Tipo de `MyCompanyOrderProcessing` en el **nombre** campo y, a continuación, haga clic en **agregar**.  
  
## <a name="create-receive-information"></a>Crear información de recepción  
 En este procedimiento, creará un mensaje, un puerto de recepción y una forma de recepción nuevos para la orquestación. En él se muestra cómo configurar una orquestación para recibir un mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
#### <a name="create-a-new-message"></a>Crear un nuevo mensaje  
  
1.  En **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**. Con esto, se generará un nuevo mensaje con el nombre `Message_1`.  
  
2.  Haga clic en `Message_1`, haga clic en **cambiar el nombre de**y, a continuación, escriba `Message_PO`.  
  
3.  Haga clic en `Message_PO`y, a continuación, haga clic en **ventana propiedades**.  
  
4.  En el **tipo de mensaje** propiedad, expanda **esquemas**y, a continuación, seleccione `OrderProcess.OrderProcessSchema` esquema.  
  
#### <a name="add-a-receive-port-to-the-orchestration"></a>Agregar un puerto de recepción a la orquestación  
  
1.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **puerto** forma a la superficie del puerto. Se iniciará el Asistente para configuración de puertos.  
  
2.  En la pantalla de bienvenida, haga clic en **siguiente**.  
  
3.  Tipo de `ReceivePurchaseOrder` en el **nombre** campo y, a continuación, haga clic en **siguiente**.  
  
4.  Seleccione **crear un nuevo tipo de puerto**.  
  
5.  Tipo de `PurchaseOrderPT` en el **nombre de tipo de puerto** campo y, a continuación, haga clic en **siguiente**.  
  
6.  En el **enlace de puerto pantalla**, deje los valores predeterminados y, a continuación, haga clic en **siguiente**.  
  
7.  Haga clic en **Finalizar**.  
  
8.  En **Vista orquestación**, en **tipos de puerto**, expanda el `PurchaseOrderPT` tipo de puerto.  
  
9. Haga clic en `Operation_1`, haga clic en **cambiar el nombre de**y, a continuación, escriba `PurchaseOrderOperation`.  
  
#### <a name="add-a-receive-shape-to-the-orchestration"></a>Agregar una forma Recepción a la orquestación  
  
1.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **recepción** forma a la orquestación.  
  
2.  Haga clic en la forma recepción y, a continuación, haga clic en **ventana propiedades**.  
  
3.  Establecer el **activar** propiedad `True`.  
  
    > [!NOTE]
    >  Si la propiedad Activar está establecida en False, obtendrá el siguiente error: "error X2214: debe especificar al menos una correlación ya inicializada establecida para una recepción de no activación de un puerto no autocorrelacionado"  
  
4.  Tipo de `Receive_PO` en el **nombre** campo.  
  
5.  En el **ventana propiedades**, seleccione `Message_PO` para la propiedad de mensaje.  
  
6.  Seleccione `ReceivePurchaseOrder.PurchaseOrderOperation.Request` para el **operación** propiedad. Con esto, se asociará el puerto a la forma Recepción en el Diseñador de orquestaciones.  
  
## <a name="create-send-information"></a>Crear información de envío  
 En este procedimiento, creará un mensaje, puertos de envío y una estructura de decisión nuevos en la orquestación. En él, se muestra cómo configurar una orquestación con lógica de decisiones, además de cómo configurar una orquestación para enviar un mensaje a un puerto de envío.  
  
#### <a name="create-a-new-message"></a>Crear un nuevo mensaje  
  
1.  En **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**. Con esto, se generará un nuevo mensaje con el nombre `Message_1`.  
  
2.  Haga clic en `Message_1`, haga clic en **cambiar el nombre de**y, a continuación, escriba `Message_Task`.  
  
3.  Haga clic en `Message_Task`y, a continuación, haga clic en **ventana propiedades**.  
  
4.  En el **tipo de mensaje** propiedad, expanda **esquemas**y, a continuación, seleccione `OrderProcess.OrderProcessSchema` esquema.  
  
#### <a name="add-a-send-port-to-the-orchestration"></a>Agregar un puerto de envío a la orquestación  
  
1.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **puerto** forma a la superficie del puerto. Se iniciará el Asistente para configuración de puertos.  
  
2.  En la pantalla de bienvenida, haga clic en **siguiente**.  
  
3.  Tipo de `SendPurchaseOrder` en el **nombre** campo y, a continuación, haga clic en **siguiente**.  
  
4.  Seleccione **utilizar un tipo de puerto existente**.  
  
5.  En **tipos de puertos disponibles**, seleccione `OrderProcess.PurchaseOrderPT`y, a continuación, haga clic en **siguiente**.  
  
6.  En el **enlace de puerto pantalla**, en **dirección de puerto de comunicación**, seleccione `I'll always be sending messages on this port`y, a continuación, haga clic en **siguiente**.  
  
7.  Haga clic en **Finalizar**.  
  
#### <a name="add-a-send-shape-to-the-orchestration"></a>Agregar una forma Envío a la orquestación  
  
1.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **enviar** forma para el Diseñador de orquestaciones. Colóquela bajo la forma de recepción `Receive_PO`.  
  
2.  Haga clic en la forma de envío y, a continuación, haga clic en **ventana propiedades**.  
  
3.  Tipo de `Send_PO` en el **nombre** campo.  
  
4.  Seleccione `Message_PO` para el **mensaje** propiedad.  
  
5.  Seleccione `SendPurchaseOrder.PurchaseOrderOperation.Request` para el **operación** propiedad. Con esto, se asociará el puerto a la forma Envío en el Diseñador de orquestaciones.  
  
#### <a name="add-a-decide-shape-to-the-orchestration"></a>Agregar una forma Decidir a la orquestación  
  
1.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **decidir** forma para el Diseñador de orquestaciones. Colóquela bajo la forma de envío `Send_PO`.  
  
2.  Haga clic en la forma decidir y, a continuación, haga clic en **ventana Propiedades.**  
  
3.  Tipo de `NeedsApproval` en el **nombre** campo.  
  
4.  En el Diseñador de orquestaciones, haga clic en **Rule_1** en la forma decidir.  
  
5.  En la ventana Propiedades, escriba `ApprovalRequired` para el **nombre** propiedad.  
  
6.  Haga clic en el **expresión** propiedad de campo y, a continuación, haga clic en los puntos suspensivos (**...** ) botón.  
  
7.  En el Editor de expresiones de BizTalk, escriba o copie lo siguiente:  
  
    ```  
    Message_PO(OrderProcess.PropertySchema.Amount) > 1000  
    ```  
  
8.  Haga clic en **Aceptar**.  
  
#### <a name="add-another-send-port-to-the-orchestration"></a>Agregar otro puerto de envío a la orquestación  
  
1.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **puerto** forma a la superficie del puerto. Se iniciará el Asistente para configuración de puertos.  
  
2.  En la pantalla de bienvenida, haga clic en **siguiente**.  
  
3.  Tipo de `SendToTasksList` en el **nombre** campo y, a continuación, haga clic en **siguiente**.  
  
4.  Seleccione **utilizar un tipo de puerto existente**.  
  
5.  En **tipos de puertos disponibles**, seleccione `OrderProcess.PurchaseOrderPT`y, a continuación, haga clic en **siguiente**.  
  
6.  En el **enlace de puerto pantalla**, en **dirección de puerto de comunicación**, seleccione `I'll always be sending messages on this port`.  
  
7.  En **enlace de puerto**, seleccione `Dynamic`y, a continuación, haga clic en **siguiente**.  
  
8.  Haga clic en **Finalizar**.  
  
#### <a name="add-a-send-shape-to-the-decide-shape"></a>Agregar una forma Envío a la forma Decidir  
  
1.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **enviar** forma para el Diseñador de orquestaciones. Colóquela bajo la forma `ApprovalRequired`.  
  
2.  Haga clic en la forma de envío y, a continuación, haga clic en **ventana Propiedades**  
  
3.  Tipo de `CreateApprovalTask` en el **nombre** campo.  
  
4.  Seleccione `Message_Task` para el **mensaje** propiedad.  
  
5.  Seleccione `SendToTasksList.PurchaseOrderOperation.Request` para el **operación** propiedad. Con esto, se asociará el puerto a la forma Envío en el Diseñador de orquestaciones.  
  
## <a name="create-an-expression"></a>Crear una expresión  
 En este procedimiento, agregará una forma Expresión a la solución, con lo que se asignará la ruta de acceso de Tareas a una variable. En él, se muestra cómo agregar lógica a una orquestación para modificar las propiedades de un puerto de envío dinámico.  
  
#### <a name="create-a-new-expression"></a>Crear una nueva expresión  
  
1.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **expresión** forma antes de la `CreateApprovalTask` forma de envío.  
  
2.  Haga clic en la forma de expresión y, a continuación, haga clic en **ventana Propiedades.**  
  
3.  Tipo de `SetPortDestination` en el **nombre** campo.  
  
4.  Haga clic en el **expresión** propiedad de campo y, a continuación, haga clic en los puntos suspensivos (**...** ) botón.  
  
5.  En el **Editor de expresiones de BizTalk**, escriba lo siguiente:  
  
    ```  
    SendToTasksList(Microsoft.XLANGs.BaseTypes.Address) = "wss://localhost/sites/WSSAdapterWalkthrough/Lists/Tasks/";  
    ```  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="construct-a-new-message"></a>Construir un nuevo mensaje  
 En este procedimiento, agregará una forma Construir a la solución, con lo que se construirá una nueva instancia de un tipo de mensaje en la orquestación. En él, se muestra cómo crear un mensaje nuevo que sea una copia del mensaje de entrada y, seguidamente, modificar las propiedades de contexto del nuevo mensaje. Este paso es necesario porque los mensajes son inmutables en BizTalk; es decir, una vez construido el mensaje, no es posible modificar el original.  
  
#### <a name="add-a-construct-shape"></a>Agregar una forma Construir  
  
1.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **construir mensaje** forma antes de la `SetPortDestination` forma expresión.  
  
2.  Haga clic en la forma construir mensaje y, a continuación, haga clic en **ventana Propiedades.**  
  
3.  Tipo de `ConstructTaskMessage`en el **nombre** campo.  
  
4.  Seleccione `Message_Task` para el **mensajes construidos** propiedad.  
  
5.  En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **asignación de mensajes** forma la `ConstructTaskMessage` **construir mensaje** forma.  
  
6.  En el **ventana propiedades**, tipo `InitTaskMessage` en el **nombre** campo.  
  
7.  Haga clic en el **expresión** propiedad de campo y, a continuación, haga clic en los puntos suspensivos (**...** ) botón.  
  
8.  En el **Editor de expresiones de BizTalk**, escriba o copie lo siguiente:  
  
    ```  
    Message_Task = Message_PO;  
    Message_Task(WSS.ConfigOverwrite) = "no";  
    Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";  
    Message_Task(WSS.ConfigPropertiesXml) = "<ConfigPropertiesXml><PropertyName1>Title</PropertyName1><PropertySource1>Approve %XPATH=//orchns:PurchaseOrder/orchns:PurchaseOrderID%</PropertySource1><PropertyName3>Status</PropertyName3><PropertySource3>Not Started</PropertySource3><PropertyName4>Priority</PropertyName4><PropertySource4>(1) High</PropertySource4></ConfigPropertiesXml>";  
    ```  
  
    > [!IMPORTANT]
    >  Al especificar los valores para estas propiedades de contexto, es preciso distinguir entre mayúsculas y minúsculas. Al establecer los valores de configuración para un puerto dinámico con propiedades de contexto, es necesario asegurarse de que se utilizan las mayúsculas y minúsculas del modo apropiado o, de lo contrario, se producirá un error cuando BizTalk intente enrutar el documento al puerto de envío designado.  
  
9. Haga clic en **Aceptar**.  
  
10. Haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.  
  
## <a name="build-the-biztalk-project"></a>Generar el proyecto de BizTalk  
 En este procedimiento, generará e implementará el proyecto de BizTalk. Este paso resulta necesario para crear e implementar el ensamblado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa en tiempo de ejecución.  
  
#### <a name="build-and-deploy-the-solution"></a>Compilar e implementar la solución  
  
1.  Haga clic en **generar**y, a continuación, haga clic en **generar OrderProcess**.  
  
2.  Haga clic en **generar**y, a continuación, haga clic en **implementar OrderProcess**.  
  
3.  Cierre Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="modify-the-receive-location-and-send-port"></a>Modificar la ubicación de recepción y el puerto de envío  
 En este procedimiento, modificará la ubicación de recepción y el puerto de envío existentes para utilizar el procesamiento XML para las canalizaciones. La canalización XML de recepción almacena las propiedades de mensaje utilizadas durante el procesamiento de la orquestación, mientras que la canalización XML de envío almacena las propiedades de mensaje que se aplican en la orquestación y que se utilizarán posteriormente para el enrutamiento de mensajes.  
  
#### <a name="modify-the-receive-location"></a>Modificar la ubicación de recepción  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server.**  
  
2.  Expanda **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **complemento Administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda  **BizTalk Application 1**y, a continuación, haga clic en el **ubicaciones de recepción** nodo.  
  
3.  Haga clic en `SourceLocation`y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo **General**, seleccione `XMLReceive` para el **canalización de recepción** propiedad.  
  
5.  Haga clic en **Aceptar**.  
  
#### <a name="modify-the-send-port"></a>Modificar el puerto de envío  
  
1.  Haga clic en el **puertos de envío** nodo.  
  
2.  Haga clic en `SendToDestination`y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de puerto de envío** cuadro de diálogo **General**, seleccione `XMLTransmit` para el **canalización de envío** propiedad.  
  
4.  Seleccione el **filtros** ficha.  
  
5.  Seleccione la condición existente, presione la tecla SUPR y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="start-a-new-send-port"></a>Iniciar un nuevo puerto de envío  
  
1.  Haga clic en el **puertos de envío** nodo.  
  
2.  Haga clic en `OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`y, a continuación, haga clic en **iniciar**.  
  
> [!NOTE]
>  Puede que sea necesario actualizar la consola si no resulta visible.  
  
## <a name="bind-the-orchestration"></a>Enlazar la orquestación  
 En este procedimiento, enlazará la orquestación a los puertos especificados. Este procedimiento resulta necesario para asociar puertos físicos a la orquestación generada e implementada.  
  
#### <a name="bind-the-orchestration"></a>Enlazar la orquestación  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **orquestaciones** nodo.  
  
2.  Haga clic en el `OrderProcess.MyCompanyOrderProcessing` orquestación y, a continuación, haga clic en **propiedades**.  
  
3.  Seleccione el **enlaces** ficha.  
  
4.  En **Host**, seleccione `BizTalkServerApplication` en el **Host** campo.  
  
5.  En **enlaces**, seleccione `FromSource` para el `ReceivePurchaseOrder` puerto lógico de entrada.  
  
6.  En **enlaces**, seleccione `SendToDestination` para el `SendPurchaseOrder` puerto lógico de salida.  
  
7.  Haga clic en **Aceptar**.  
  
8.  Haga clic en `OrderProcess.MyCompanyOrderProcessing` orquestación y, a continuación, haga clic en **iniciar**.  
  
## <a name="send-a-message-through-the-system"></a>Enviar un mensaje a través del sistema  
 En este procedimiento, creará un formulario de InfoPath y lo cargará en el sitio web de Windows SharePoint Services. El adaptador de Windows SharePoint Services tomará el mensaje, lo archivará en la biblioteca de documentos de archivo y, a continuación, lo enviará a la biblioteca de documentos de destino. Durante el procesamiento del mensaje, se obtendrá acceso a las propiedades de contexto de Windows SharePoint Services que ayudan a determinar el destino.  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a>Crear un formulario de InfoPath para su envío a través del sistema  
  
1.  Abra un explorador web y vaya a la dirección URL del sitio creado. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.  
  
2.  En el menú Inicio rápido, haga clic en `InfoPathSolutions`.  
  
3.  Haga clic en el `PurchaseOrder` archivo para mostrar el **descarga de archivos** cuadro de diálogo y, a continuación, haga clic en **abiertos**. InfoPath cargará el formulario.  
  
4.  En el **Purchase Order ID** , escriba `1003`.  
  
5.  En el **facturar a** , escriba `John Doe`.  
  
6.  En el **cantidad** , escriba `1750`.  
  
7.  En el **fecha del pedido de compra** , escriba `1/3/2005`.  
  
8.  Haga clic en **Guardar**.  
  
9. En el **Guardar como** cuadro de diálogo, escriba `http://<server_name>/sites/WSSAdapterWalkthrough/Source`en el **nombre de archivo** campo y, a continuación, presione ENTRAR.  
  
10. Tipo de `PurchaseOrder3.xml` en el **nombre de archivo** campo y, a continuación, haga clic en **guardar**.  
  
11. Cierre InfoPath.  
  
12. En el explorador Web, haga clic en **documentos y listas**.  
  
13. En **las bibliotecas de documentos**, haga clic en **destino**.  
  
14. En la biblioteca de documentos de destino, verá ahora el mensaje incluido en esta biblioteca. También encontrará una copia archivada en la biblioteca de documentos de archivo.  
  
15. Haga clic en **Inicio**.  
  
16. En **enumera**, haga clic en **tareas**.  
  
17. En la lista Tareas, verá la tarea de aprobación recién creada.  
  
> [!NOTE]
>  Puesto que el importe del pedido superaba los 1.000,00 dólares, se creó la tarea.  
  
## <a name="summary"></a>Resumen  
 En este tutorial, ha visto cómo obtener acceso a las propiedades de contexto de Windows SharePoint Services y cómo determinar el destino de los mensajes que circulan a través de puertos dinámicos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Continúe revisando el resto de la sección del adaptador de Windows SharePoint Services. Para obtener más información, vea los temas de Vea también.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Tutoriales del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-walkthroughs.md)