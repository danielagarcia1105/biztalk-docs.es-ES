---
title: "Crear una orquestación de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c637ae-f94f-40f8-8ce7-73a7b7df9f8f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6223ab8d8aa3c8d1c20559a88257dd0dccaa22e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="create-a-biztalk-server-orchestration"></a>Crear una orquestación de BizTalk Server
> [!NOTE]
>  Este tutorial solo se aplica a BizTalk Server.  
  
 Cree una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que, al implementarla, reciba un mensaje de pedido de compra JSON, lo transforme en una factura XML y envíe una factura JSON.  
  
## <a name="define-message-and-message-types"></a>Definir el mensaje y los tipos de mensaje  
 Esta solución funciona con dos mensajes básicos: pedido de compra y factura. Ya hemos generado el esquema del pedido de compra a partir de un mensaje JSON usando el asistente para esquemas JSON. El ejemplo que se proporciona para este tutorial ya tiene el esquema para el mensaje de factura. Estos esquemas se usan para crear los tipos de mensaje en la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
1.  Agregue una orquestación al proyecto de BizTalk y abra la Vista orquestación.  
  
2.  En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel para la **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `PurchaseOrder`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *BTSJSON. Pedido de compra*, donde *BTSJSON* es el nombre de su proyecto de BizTalk.|  
  
5.  Repita el paso anterior para crear un nuevo tipo de mensaje para el mensaje de factura. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `InvoiceMsg`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *BTSJSON. Factura*.|  
  
## <a name="set-up-the-orchestration"></a>Configurar la orquestación  
 En este paso, va a agregar formas de mensaje y puertos para crear una orquestación.  
  
### <a name="add-message-shapes"></a>Agregar formas de mensaje  
 Abra el archivo de orquestación desde el Explorador de soluciones y agregue las siguientes formas de mensaje.  
  
-   Agregar una forma recepción, dele el nombre **ReceivePO**y el tipo de mensaje **PurchaseOrder**.  
  
-   Agregue una forma de envío, dele el nombre **SendInvoice**y el tipo de mensaje **InvoiceMsg**.  
  
-   Agregue una forma construir mensaje y establezca el **mensajes construidos** propiedad de la forma construir mensaje a **InvoiceMsg**.  
  
-   Agregue una forma Transformación a la forma Construir mensaje. Haga doble clic en la forma transformación y, en la **configuración de transformación** cuadro de diálogo, seleccione la **mapa existente** opción y, a continuación, seleccione **BTSJSON. POToInvoice** mapa. Esta asignación se proporciona como parte del ejemplo. En el cuadro de diálogo, establezca **origen** a **PurchaseOrder** y establecer **destino** a **InvoiceMsg**. Haga clic en **Aceptar**.  
  
### <a name="add-ports"></a>Agregar puertos  
 Agregue dos puertos a la orquestación: uno para recibir mensajes y otro para enviarlos. Use las siguientes propiedades para los puertos:  
  
|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *ReceiveJSONPO*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|ResponseOut|-Establecer **identificador** a *SendJSONInvoice*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
 Conecte los puertos y la forma del mensaje, como se muestra en la siguiente captura de pantalla, y guarde los cambios del proyecto.  
  
 ![Orquestación para procesar mensajes JSON](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes JSON con BizTalk Server](../core/processing-json-messages-using-biztalk-server.md)