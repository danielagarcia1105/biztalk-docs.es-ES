---
title: "Creación de los puertos de envío FRR para enviar a los controladores personalizados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7da5d51407bed1cca257e14cc4f548e8c991cf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a>Creación de los puertos de envío FRR para enviar a los controladores personalizados
Para realizar la conciliación de respuesta de FIN, debe crear una serie de puertos de envío, cada uno de los cuales envía un mensaje (original mensaje o respuesta) de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a los controladores personalizados que procesan los mensajes correlacionados.  
  
 **Resumen**  
  
 Crear una serie de puertos de envío con las siguientes propiedades y los componentes, cada uno de ellos que se distinguen por el valor de BTS. Operación en el filtro:  
  
|Propiedad/componente|Configuración|  
|-------------------------|-------------|  
|Puerto de envío|Puerto unidireccional estático|  
|Tipo de transporte|FILE|  
|Carpeta de destino (URI de dirección)|La carpeta que desea enviar el mensaje|  
|Nombre de archivo (dirección URI)|%MessageID%.txt|  
|Canalización de envío|[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. BizTalk.DefaultPipelines. PassThruTransmit|  
|Filtros|Como se muestra en las tablas siguientes|  
  
 Los puertos de envío para los mensajes se distinguen por el valor de BTS. Operación de filtro del puerto de envío.  
  
### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a>Para agregar puertos de envío FRR para enviar a los controladores personalizados  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto estático de una waySend**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba un nombre para el puerto de envío, por ejemplo, FRRCustomHandlersSendPort.  
  
3.  Para **tipo**, seleccione **archivo**.  
  
4.  Haga clic en **configurar**.  
  
5.  En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.  
  
6.  En el cuadro de diálogo Buscar carpeta, mover a la carpeta que desea enviar mensajes desde. Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si esta carpeta no existe, puede crearlo mediante el **crear nueva carpeta** comando.  
  
7.  En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Puede crear una carpeta diferente para cada tipo de mensaje.  
  
8.  En el cuadro de diálogo Propiedades de puerto de envío para el controlador de envío, compruebe que **BizTalkServerApplication** está seleccionada.  
  
9. Para **canalización de envío**, seleccione **PassThruTransmit**.  
  
10. Haga clic en **filtros** en el panel izquierdo y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **A4SWIFT_FrrService**.|  
    |**Grupo**|**Y**|  
    |**Propiedad**|Seleccione **BTS. Operación**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Escriba uno de los BTS. Valores de la operación de la siguiente tabla.|  
  
     De BTS. Operación, escriba uno de los siguientes valores:  
  
    |Tipo de mensaje|BTS. Valor de la operación|  
    |------------------|-------------------------|  
    |Todos los tipos de mensaje SWIFT FINÉS de categoría del 0 al 9|**A4SWIFT_FrrSendMTMsg**|  
    |MQ Series PAN/NAN (confirmación de nivel de transporte MQ Series/NAK)|**A4SWIFT_FrrSendTransport**|  
    |MT010 (advertencia de no entrega)|**A4SWIFT_FrrSend010NDW**|  
    |MT011 (notificación de entrega)|**A4SWIFT_FrrSend011Delivered**|  
    |MT012 (notificación de remitente)|**A4SWIFT_FrrSend012SenderACK**|  
    |MT015 (DIN o NAK diferida)|**A4SWIFT_FrrSend015DNK**|  
    |MT019 (anular la notificación)|**A4SWIFT_FrrSend019Abort**|  
    |MTS21_FIN_ACKNAK (confirmación de un mensaje FIN enviado por un LT (ACK)|**A4SWIFT_FrrSendS21ACK**|  
    |MTS21_FIN_ACKNAK (confirmación de un mensaje FIN enviado por un LT (NAK) de un negativo|**A4SWIFT_FrrSendS21NAK**|  
  
11. Para mensajes de FIN de SWIFT categoría 0 a 9 y que no se envían correctamente, haga lo siguiente el **filtros** panel:  
  
    > [!NOTE]
    >  El **A4SWIFT_FRRFailedReason** propiedades en el siguiente filtro deben estar agrupados.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **A4SWIFT_FrrService**.|  
    |**Grupo**|**Y**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **True**.|  
    |**Grupo**|**Y**|  
    |**Propiedad**|Seleccione **BTS. Operación**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **A4SWIFT_FrrSendMTMsg**.|  
    |**Grupo**|**Y**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de  *\<NAKErrorCode >*, por ejemplo, "Y01".|  
    |**Grupo**|**Or**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **TimedOut**.|  
    |**Grupo**|**Or**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **TransportError**.|  
    |**Grupo**|**Or**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **DelayedNAK**.|  
    |**Grupo**|**Or**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **AbortMessage**.|  
  
12. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
13. Haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
14. Repita los pasos del 2 al 13 para crear un puerto de envío para cada tipo de mensaje requerido.