---
title: Importar BPEL (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- examples, orchestrations
- examples, BPEL Import Wizard
- BPEL, examples
- BPEL Import Wizard, examples
- BPEL Import Wizard, orchestrations
ms.assetid: 3fc70608-ccd9-4249-b238-c09fc6551db1
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b76cead956ade8d16c5cbd26c55f94eabe15e1fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bpel-import-biztalk-server-sample"></a>Importar BPEL (ejemplo de BizTalk Server)
El ejemplo de Importar BPEL muestra cómo crear una orquestación a partir de una descripción de proceso de Lenguaje de ejecución de procesos empresariales (BPEL) y sus artefactos relacionados.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Wide World Importers es una empresa de transporte que ofrece servicios de envío automatizados a distribuidores. En concreto, Wide World Importers permite a los distribuidores llevar a cabo las siguientes acciones:  
  
-   Solicitar envíos de pedidos  
  
-   Llevar a cabo un seguimiento de los envíos  
  
-   Confirmar los envíos  
  
-   Confirmar la facturación y los pagos de los envíos  
  
 Mientras que la disponibilidad de estos servicios puede representarse mediante el uso de un documento de Lenguaje de descripción de servicios web (WSDL), un documento BPEL describe el modo en el que se espera que las compañías de productos llamen a los servicios y cómo deben esperar la respuesta de Wide World Importers.  
  
 Cuando Northwind Traders contrata los servicios de Wide World Importers para que lleve a cabo su envío, se les entrega un archivo BPEL y algunos artefactos relacionados que describen la interacción. Mediante el archivo BPEL, Northwind Traders crea una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (BPELShipping) para procesar automáticamente los pedidos a través de Wide World Importers.  
  
 Este ejemplo realiza un recorrido por este escenario en el que la aplicación BPELShipping:  
  
1.  Recibe un pedido del sistema de pedidos de cliente de Northwind Traders.  
  
2.  Envía una solicitud de envío a Wide World Importers y solicita una confirmación.  
  
3.  Recibe una confirmación de la solicitud de envío de Wide World Importers.  
  
4.  Recibe una notificación de recogida de Wide World Importers.  
  
5.  Recibe mensajes de estado del envío hasta el momento en el que el cliente ha recibido el envío.  
  
6.  Recibe una factura de Wide World Importers.  
  
7.  Responde a Wide World Importers con una confirmación de recepción de factura.  
  
8.  Recibe una confirmación de pago de Wide World Importers.  
  
9. Envía una confirmación de envío final al sistema de pedidos.  
  
 Se utiliza una aplicación independiente de BizTalk (ShipperProcess) para simular la empresa Wide World Importers para este ejemplo. La aplicación BPELShipping se comunica con ShipperProcess mediante el transporte de archivos, que utiliza ubicaciones del sistema de archivos comunes para la comunicación.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 BPEL para servicios web es un lenguaje basado en XML que describe el proceso empresarial de forma que puedan compartirlo varias empresas distintas que desean hacer negocios entre sí mediante los servicios web. BPEL describe cómo controlar el proceso empresarial en el nivel de protocolo empresarial, pero no describe el proceso interno de una empresa, como los pasos que la empresa realiza para procesar un pedido después de recibirlo de un socio comercial. Este ejemplo está diseñado para mostrar cómo importar BPEL y los archivos WSDL correspondientes, convertirlos a una orquestación y, después, iniciar el proceso empresarial con el socio comercial.  
  
 A continuación, se muestra el procedimiento paso a paso que indica cómo importar los archivos BPEL y WSDL y convertirlos a una orquestación para que interactúe con una aplicación de BizTalk ya generada (ShipperProcess). Si completa los pasos siguientes, no necesitará llevar a cabo los pasos descritos en "Generar e inicializar la aplicación BPELShipping".  
  
#### <a name="to-import-from-bpel-and-build-a-working-solution"></a>Para importar desde BPEL y generar una solución de trabajo  
  
1.  En Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, haga clic en **New**y, a continuación, haga clic en **proyecto**.  
  
    > [!NOTE]
    >  Antes de completar este procedimiento, deberá configurar la aplicación ShipperProcess para crear los proyectos de esquema y los procesos complementarios.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, en el panel tipos de proyecto, seleccione **BizTalk (proyectos)**. En el panel Plantillas, seleccione **proyecto de importación BPEL de servidor BizTalk Server**.  
  
3.  En el **nombre** cuadro, escriba **BPELShipping**.  
  
    > [!NOTE]
    >  Si utiliza un nombre distinto, pueden producirse problemas con el paso de enlace final.  
  
4.  Seleccione una ubicación para el proyecto y, a continuación, haga clic en **Aceptar** para iniciar el Asistente para importar BPEL.  
  
5.  En el **bienvenida** página, haga clic en **siguiente**.  
  
6.  En el **seleccione BPEL, WSDL y XSD archivos** página, haga clic en **examinar**.  
  
7.  Seleccione todos los archivos de la \< *ruta de ejemplos*> \Orchestrations\BPELImport\BPELSource carpeta, haga clic en **abiertos**y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  En este paso, seleccione los archivos BPEL y WSDL para describir el proceso empresarial y los archivos XSD para representar los esquemas de documentos empresariales.  
  
8.  En el **seleccionar archivos WSDL para los WebServices invocados** página, haga clic en **finalizar**.  
  
9. Cuando el Asistente para importar BPEL informe de que la importación se ha realizado correctamente, cierre el asistente. Ya se ha creado el proyecto.  
  
10. En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a la ubicación del proyecto.  
  
11. Ejecute el siguiente comando:  
  
     **sn – k BPELShipping.snk**  
  
12. En el Explorador de soluciones, haga clic en el **BPELShipping** del proyecto y, a continuación, haga clic en **propiedades**.  
  
13. En **comunes\ensamblado**, seleccione el archivo de clave de ensamblado **BPELShipping.snk** creado en el paso 11 y, a continuación, haga clic en **Aceptar**.  
  
14. En el Explorador de soluciones, seleccione todos los archivos .xsd y elimínelos.  
  
15. En el Explorador de soluciones, seleccione **Agregar referencia**y en el **proyectos** , haga clic en **examinar**.  
  
16. Seleccione **ShippingSchemas.dll** desde la ubicación \< *ruta de ejemplos*> \Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development y, a continuación, haga clic en  **Aceptar**.  
  
    > [!NOTE]
    >  La sección "Generar e iniciar la aplicación ShipperProcess" contiene instrucciones acerca de cómo generarla.  
  
17. En el Explorador de soluciones, haga doble clic en **OrderShippingProcess.bpel.odx**.  
  
18. En el **vista** menú, seleccione **otras ventanas/Vista orquestación**.  
  
19. En la ventana Vista orquestación, haga clic en **propiedades de orquestación** y, a continuación, haga clic en **ventana propiedades**.  
  
20. En la ventana Propiedades, establezca la **Exportable a orquestación** propiedad **False**.  
  
21. En el Explorador de soluciones, haga doble clic en **OrderShipping.wsdl.odx**.  
  
22. En la ventana Vista orquestación, expanda **tipos de mensajes de tipos/Multipart**.  
  
23. Expanda **InvoiceAckMessageType** y, a continuación, haga clic en **InvoiceAckMessagePart**.  
  
24. En la ventana Propiedades, expanda el **tipo** campo y, a continuación, seleccione **esquemas/seleccionar del ensamblado mencionado**.  
  
25. En el **Seleccionar tipo de artefacto** cuadro de diálogo, haga clic en **ShippingSchemas**, seleccione la **Imported_InvoiceAckMessage** escriba y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  En los pasos del 23 al 25, reemplaza el tipo de mensaje de los servicios que participan en el proceso de BPEL con los tipos de mensajes correspondientes descritos en ShippingSchemas.  
  
26. Repita los pasos del 23 al 25 para cada tipo de mensaje mediante los siguientes valores.  
  
    |Parte de mensaje|Tipo de mensaje|  
    |------------------|------------------|  
    |InvoiceMessagePart|ShippingSchemas.Imported_InvoiceMessage|  
    |OrderAckMessagePart|ShippingSchemas.Imported_OrderAckMessage|  
    |OrderMessagePart|ShippingSchemas.Imported_OrderMessage|  
    |PaymentConfirmationMessagePart|ShippingSchemas.Imported_PaymentConfirmationMessage|  
    |PickupNotificationMessagePart|ShippingSchemas.Imported_PickupNotificationMessage|  
    |ShipConfirmationMessagePart|ShippingSchemas.Imported_ShipConfirmationMessage|  
    |ShippingHistoryPart|ShippingSchemas.Imported_ShippingHistory|  
    |ShipRequestAckMessagePart|ShippingSchemas.Imported_ShipRequestAckMessage|  
    |ShipRequestMessagePart|ShippingSchemas.Imported_ShipRequestMessage|  
    |ShipStatusMessagePart|ShippingSchemas.Imported_ShipStatusMessage|  
  
27. En el Explorador de soluciones, haga clic en el **BPELShipping** , seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  
  
28. Seleccione todos los archivos .btm en la ubicación \< *ruta de ejemplos*> \Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping.  
  
29. En la ventana Vista orquestación, busque el **asignación de mensajes** forma con el nombre MessageAssignment_1 en ConstructMessage1 y elimínela.  
  
30. En el cuadro de herramientas, arrastre un **transformar** forma en la forma ConstructMessage1.  
  
31. En la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) y abra el **configuración de transformación** cuadro de diálogo.  
  
32. Seleccione **mapa existente**.  
  
33. Seleccione el nombre de asignación completo **BPELShipping.Order2ShipRequest**.  
  
34. Seleccione el origen como **orden. OrderMessagePart**.  
  
35. Seleccione el destino como **ship_request. ShipRequestMessagePart** y haga clic en **Aceptar**.  
  
36. Repita los pasos del 29 al 35 para cada uno de los **asignación de mensajes** formas y reemplácelas con **transformar** formas según la tabla siguiente.  
  
    |Forma para reemplazar|Asignación para utilizarla|Documento de origen|Documento de destino|  
    |----------------------|----------------|---------------------|--------------------------|  
    |MessageAssignment_2|BPELShipping.Order2OrderAck|order.OrderMessagePart|order_ack.OrderAckMessagePart|  
    |MessageAssignment_3|BPELShipping.Order2OrderNAck|order.OrderMessagePart|order_ack.OrderAckMessagePart|  
    |MessageAssignment_4|BPELShipping.Order2ShipHistory|order.OrderMessagePart|ship_history.ShippingHistoryPart|  
    |MessageAssignment_5|BPELShipping.ShipHistory2Completed|order.OrderMessagePart|ship_history.ShippingHistoryPart|  
    |MessageAssignment_6|BPELShipping.Invoice2Ack|invoice.InvoiceMessagePart|invoice_ack.InvoiceAckMessagePart|  
    |MessageAssignment_7|BPELShipping.Order2FinalConfirmation|order.OrderMessagePart|order_shipped.OrderAckMessagePart|  
  
37. Guarde la orquestación.  
  
38. Haga doble clic en **Rule_1** en el **decidir** forma **Decision_1**.  
  
39. En el Editor de expresiones de BizTalk, reemplace  
  
     ship_request_ack(BPELShipping.Ship_Acknowledged) == true  
  
     con  
  
     ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true  
  
40. Haga doble clic en el **bucle** forma denominada **Loop_1**.  
  
41. En el Editor de expresiones de BizTalk, reemplace  
  
     ship_history(BPELShipping.Ship_Completed) == true  
  
     con  
  
     ship_history(ShippingSchemas.Ship_Completed) == true  
  
42. Haga doble clic en **Rule_2** en el **decidir** forma **Decision_2**.  
  
43. En el Editor de expresiones de BizTalk, reemplace  
  
     ship_status(BPELShipping.ShipStatus) == "DONE"  
  
     con  
  
     ship_status(ShippingSchemas.ShipStatus) == "DONE"  
  
44. En la Vista orquestación, expanda **tipos/tipos de correlación** y haga clic en **_OrderCorrelationSet_Type\_**.  
  
45. En la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) en **propiedades de correlación**.  
  
46. En las propiedades de correlación en el panel, haga clic en **BPELShipping.OrderID**y, a continuación, haga clic en **quitar**.  
  
47. En el panel de propiedades disponibles, expanda **esquemas de envío**, seleccione **Id. de pedido**y, a continuación, haga clic en **agregar**.  
  
48. Haga clic en **Aceptar**.  
  
49. Guarde todos los archivos y genere la solución.  
  
50. Implementar la solución.  
  
51. Vaya a la ubicación \< *ruta de ejemplos*> \Orchestrations\BPELImport\Solution\BPELShipping y haga doble clic en **BindAndStartOnly.bat** para enlazar e iniciar la orquestación.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso >*\Orchestrations\BPELImport  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|BPELSource\InvoiceAckMessage.xsd|Esquema de confirmación de factura.|  
|BPELSource\InvoiceMessage.xsd|Esquema de factura.|  
|BPELSource\OrderAckMessage.xsd|Esquema de confirmación de pedido.|  
|BPELSource\OrderHeader.xsd|Esquema de encabezado de pedido.|  
|BPELSource\OrderMessage.xsd|Esquema de mensajes de pedido.|  
|BPELSource\OrderShipping.wsdl|Archivo WSDL al que hace referencia BPEL.|  
|BPELSource\OrderShippingProcess.bpel|Flujo de proceso BPEL.|  
|BPELSource\PaymentConfirmationMessage.xsd|Mensaje de confirmación de pago.|  
|BPELSource\PickupNotificationMessage.xsd|Mensaje de notificación de recogida.|  
|BPELSource\ShipConfirmationMessage.xsd|Mensaje de confirmación de envío.|  
|BPELSource\ShippingHistory.xsd|Documento de historial de envío.|  
|BPELSource\ShipRequestAckMessage.xsd|Enviar confirmación de solicitud.|  
|BPELSource\ShipRequestMessage.xsd|Enviar mensaje de solicitud.|  
|BPELSource\ShipStatusMessage.xsd|Enviar mensaje de estado.|  
|Solution\bindings\BPELBindings.xml|Archivo de enlace que especifica los enlaces de puertos de la orquestación BPELShipping.|  
|Solution\bindings\ShipperBindings.xml|Archivo de enlace que especifica los enlaces de puertos de la orquestación ShipperProcess.|  
|Solution\BPELShipping\BindAndStartOnly.bat|Archivo por lotes que se utiliza para enlazar e iniciar la orquestación BPELImport después de que se haya generado manualmente e implementado.|  
|Solution\BPELShipping\cleanup.bat|Archivo por lotes que se utiliza para quitar el proceso BPELShipping.|  
|Solution\BPELShipping\Setup.bat|Archivo por lotes que se utiliza para instalar e iniciar el ejemplo BPELShipping proporcionado.|  
|Solution\BPELShipping\BPELShipping.sln|El ejemplo BPELShipping ya generado.|  
olution\BPELShipping\BPELShipping\Invoice2Ack.btm|Factura para facturar la asignación de confirmación.|  
|Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm|Asignación para convertir el Mensaje de pedido a la confirmación de envío final.|  
|Solution\BPELShipping\BPELShipping\Order2OrderAck.btm|Asignación para convertir el Mensaje de pedido a la confirmación de pedido.|  
|Solution\BPELShipping\BPELShipping\Order2OrderNack.btm|Asignación para convertir de Mensaje de pedido a confirmación negativa de pedido.|  
|Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm|Asignación para convertir de Mensaje de pedido a Documento de historial de envío.|  
|Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm|Asignación para convertir el Mensaje de pedido a la Solicitud de envío.|  
|Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm|Asignación para definir el Historial de envío como completado.|  
|Solution\ShipperProcess\setup.bat|El archivo por lotes que se va a generar, implementar, enlazar e iniciar la orquestación de la aplicación auxiliar ShipperProcess y sus puertos.|  
|Solution\ShipperProcess\cleanup.bat|Archivo por lotes para detener, dar de baja y anular la implementación de la orquestación de la aplicación auxiliar ShipperProcess y sus puertos.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 El primer paso consiste en generar e iniciar la aplicación ShipperProcess utilizada para simular Wide World Importers.  
  
#### <a name="to-build-and-initialize-the-shipperprocess-application"></a>Para generar e iniciar la aplicación ShipperProcess  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
2.  Desde el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a la siguiente carpeta:  
  
     *\<Ejemplos de ruta de acceso >*\Orchestrations\BPELImport\Solution\ShipperProcess  
  
3.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Genera el proyecto ShippingSchemas, que contiene los esquemas utilizados en ShipperProcess y en el proceso de BPELShipping  
  
    -   Genera el ShipperProcess  
  
    -   Implementa los proyectos ShippingSchemas y ShipperProcess  
  
    -   Crea y enlaza los puertos de envío y recepción utilizados por ShipperProcess  
  
    -   Se inician los puertos utilizados por ShipperProcess  
  
    -   Da de alta e inicia la orquestación ShipperProcess  
  
 Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo. Puede aparecer una o más de las advertencias siguientes; puede pasarlas por alto.  
  
```  
The 'http://contoso.org/samples/Fragments:XXXX' element is not declared. An error occurred at , (35, 16).  
<SAMPLE_LOCATION>\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(667,22): convoy found at 'activate receive(Receive_ShipOrder.Operation_1, Request, initialize Correl)'  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): and 'receive(ReceiveInvoiceAck.Operation_1, Invoice_Ack, Correl)'  
```  
  
> [!NOTE]
>  No será necesario llevar a cabo los pasos siguientes si se han completado los que se describen en "Para importar desde BPEL y generar una solución de trabajo".  
  
#### <a name="to-build-and-initialize-the-bpelshipping-application"></a>Para generar e iniciar la aplicación BPELShipping  
  
1.  > [!WARNING]
    >  Antes de ejecutar estos pasos, debe completar los pasos anteriores titulados "Para generar e iniciar la aplicación ShipperProcess".  
  
     Desde el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a la siguiente carpeta:  
  
     *\<Ejemplos de ruta de acceso >*\Orchestrations\BPELImport\Solution\BPELShipping  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Genera el proyecto BPELShipping  
  
    -   Implementa el proyecto BPELShipping  
  
    -   Crea y enlaza los puertos de envío y recepción utilizados por el proceso BPELShipping  
  
    -   Inicia los puertos utilizados por el proceso BPELShipping  
  
    -   Da de alta e inicia la orquestación BPELShipping  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-bpel-import-sample"></a>Para ejecutar el ejemplo de Importación BPEL  
  
1.  Copia la **Order.xml** de archivos desde el  *\<ruta de ejemplos >*\Orchestrations\BPELImport\Solution en la carpeta a la \< *ruta de ejemplos >*\ Carpeta Orchestrations\BPELImport\Solution\Ports\ReceiveOrder.  
  
2.  El BPELShipping orquestación recoge este archivo como un pedido en el sistema de procesamiento de pedidos de cliente, se ejecuta en el proceso de envío, y crea un archivo cada uno de los \< *ruta de ejemplos*> \Orchestrations\ Carpeta BPELImport\Solution\Ports\SendOrder y \< *ruta de ejemplos*> \Orchestrations\BPELImport\Solution\Ports\FinalConfirmation carpeta. El formato del nombre de estos archivos es \< *MessageID*> .xml, donde  *\<MessageID >* es el GUID generado para identificar de forma exclusiva el mensaje.  
  
## <a name="uninstalling-this-sample"></a>Desinstalar este ejemplo  
  
#### <a name="to-uninstall-the-bpel-import-sample"></a>Para desinstalar el ejemplo Importación BPEL  
  
1.  En un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a \< *ruta de ejemplos*> \Orchestrations\BPELImport\BPELShipping.  
  
2.  Ejecute Cleanup.bat.  
  
3.  Vaya a \< *ejemplos de ruta de acceso*> \Orchestrations\BPELImport\ShipperProcess.  
  
4.  Ejecute Cleanup.bat.  
  
## <a name="see-also"></a>Vea también  
 [Orquestaciones (carpeta de ejemplos de BizTalk Server)](../core/orchestrations-biztalk-server-samples-folder.md)