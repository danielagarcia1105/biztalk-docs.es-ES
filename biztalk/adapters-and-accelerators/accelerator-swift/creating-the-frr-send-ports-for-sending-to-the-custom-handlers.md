---
title: Creación de los puertos de envío FRR para enviar a los controladores personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed467b149674580b9ed8921a59433c5402a24a0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013941"
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a>Creación de los puertos de envío FRR para enviar a los controladores personalizados
Para llevar a cabo la conciliación de respuestas de FIN, deberá crear una serie de puertos de envío, los cuales envía un mensaje (mensaje original o respuesta) desde [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a los controladores personalizados que procesan los mensajes correlacionados.  

 **Resumen**  

 Crear una serie de puertos de envío con las siguientes propiedades y los componentes, cada uno de ellos que se distinguen por el valor de BTS. Operación en el filtro:  


|        Propiedad o el componente        |                                             Configuración                                              |
|----------------------------------|--------------------------------------------------------------------------------------------------|
|            Puerto de envío             |                                       Puerto unidireccional estático                                        |
|          Tipo de transporte          |                                               FILE                                               |
| Carpeta de destino (URI de dirección) |                         La carpeta que desea enviar el mensaje                          |
|     Nombre de archivo (dirección URI)      |                                         %MessageID%.txt                                          |
|          Canalización de envío           | Microsoft. BizTalk.DefaultPipelines. PassThruTransmit |
|             Filtros              |                                   Como se muestra en las tablas siguientes                                   |

 Los puertos de envío para los distintos mensajes se distinguen por el valor de BTS. Operación de filtro del puerto de envío.  

### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a>Para agregar puertos de envío FRR para enviar a los controladores personalizados  

1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto estático de uno waySend**.  

2.  En el cuadro de diálogo Propiedades de puerto de envío, en el **nombre** , escriba un nombre para el puerto de envío, como FRRCustomHandlersSendPort.  

3.  Para **tipo**, seleccione **archivo**.  

4.  Haga clic en **configurar**.  

5.  En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.  

6.  En el cuadro de diálogo Buscar carpeta, mover la carpeta que desea enviar mensajes desde. Haga clic en **Aceptar**.  

    > [!NOTE]
    >  Si esta carpeta no existe, puede crearlo mediante el **crear nueva carpeta** comando.  

7.  En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.  

    > [!NOTE]
    >  Puede crear una carpeta diferente para cada tipo de mensaje.  

8.  En el cuadro de diálogo Propiedades de puerto de envío para el controlador de envío, compruebe que **BizTalkServerApplication** está seleccionada.  

9. Para **canalización de envío**, seleccione **PassThruTransmit**.  

10. Haga clic en **filtros** en el panel izquierdo y, a continuación, haga lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Tipo **A4SWIFT_FrrService**.|  
    |**Grupo**|**Y**|  
    |**Propiedad**|Seleccione **BTS. Operación**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Escriba uno de los BTS. Valores de la operación de la tabla siguiente.|  

     De BTS. La operación, escriba uno de los siguientes valores:  

    |Tipo de mensaje|BTS. Valor de la operación|  
    |------------------|-------------------------|  
    |Todos los tipos de mensaje de FIN de SWIFT categoría 0 a 9|**A4SWIFT_FrrSendMTMsg**|  
    |MQ Series PAN/NAN (confirmación de nivel de transporte MQ Series/NAK)|**A4SWIFT_FrrSendTransport**|  
    |MT010 (advertencia de no entrega)|**A4SWIFT_FrrSend010NDW**|  
    |MT011 (notificación de entrega)|**A4SWIFT_FrrSend011Delivered**|  
    |MT012 (notificación de remitente)|**A4SWIFT_FrrSend012SenderACK**|  
    |MT015 (DIN o NAK retrasada)|**A4SWIFT_FrrSend015DNK**|  
    |MT019 (anular la notificación)|**A4SWIFT_FrrSend019Abort**|  
    |MTS21_FIN_ACKNAK (confirmación de un mensaje FIN enviado por un LT (ACK)|**A4SWIFT_FrrSendS21ACK**|  
    |MTS21_FIN_ACKNAK (negativo de la confirmación de un mensaje FIN enviado por un LT (NAK)|**A4SWIFT_FrrSendS21NAK**|  

11. Para los mensajes de la categoría 0 a 9 SWIFT FIN que no se envían correctamente, haga lo siguiente el **filtros** panel:  

    > [!NOTE]
    >  El **A4SWIFT_FRRFailedReason** se deben agrupar propiedades en el siguiente filtro.  

    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Tipo **A4SWIFT_FrrService**.|  
    |**Grupo**|**Y**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Tipo **True**.|  
    |**Grupo**|**Y**|  
    |**Propiedad**|Seleccione **BTS. Operación**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Tipo **A4SWIFT_FrrSendMTMsg**.|  
    |**Grupo**|**Y**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Tipo  *\<NAKErrorCode\>*, por ejemplo, "Y01".|  
    |**Grupo**|**Or**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Tipo **TimedOut**.|  
    |**Grupo**|**Or**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Tipo **TransportError**.|  
    |**Grupo**|**Or**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Tipo **DelayedNAK**.|  
    |**Grupo**|**Or**|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.|  
    |**Operador**|Seleccione **==**.|  
    |**Value**|Tipo **AbortMessage**.|  

12. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  

13. Haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  

14. Repita los pasos del 2 al 13 para crear un puerto de envío para cada tipo de mensaje necesario.