---
title: "Envía una confirmación EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a036d08-8a65-43ad-b72c-2a246d302792
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a47a3fbe13f4cf054b6114050b8777231c4b217
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sending-an-edi-acknowledgment"></a>Enviar una confirmación EDI
Las confirmaciones indican el estado de la transmisión del mensaje EDI. Una vez que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un intercambio EDI, devolverá una o más confirmaciones al remitente de un intercambio EDI, en función de las confirmaciones que se hayan habilitado.  
  
 Las confirmaciones de mensaje EDI, basadas en el nivel de validación, pueden ser de dos tipos:  
  
-   A **confirmación técnica** generados como resultado de validación de encabezados. La confirmación técnica informa del estado del procesamiento de un encabezado de intercambio y finalizador mediante el receptor de direcciones.  
  
-   A **confirmación funcional** generados como resultado de validación de cuerpo. La confirmación funcional genera un informe de los errores que aparecen al procesar el documento recibido.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]puede devolver confirmaciones técnicas y funcionales en respuesta a un único intercambio. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Devuelve una única confirmación técnica para cada intercambio. Para intercambios X12, devolverá una confirmación funcional para cada grupo recibido. Para intercambios EDIFACT, devolverá una confirmación funcional para cada intercambio, independientemente de los grupos que contenga dicho intercambio.  
  
## <a name="x12-acknowledgments"></a>Confirmaciones de X12  
 **X12 confirmación técnica**  
  
 Se envía una confirmación TA1 positiva si el encabezado ISA y el finalizador IEA de un mensaje X12 es válido (independientemente de otros contenidos). Para obtener más información sobre el contenido de una confirmación de TA1, consulte [X12 confirmación TA1](../core/x12-ta1-acknowledgment.md).  
  
 **X12 confirmación funcional**  
  
 Se usa una confirmación 997 para confirmar la recepción de un grupo funcional o intercambio, para aceptar o rechazar uno o más grupos funcionales en una o más transacciones y comprobar y generar un informe para el cumplimiento del estándar. Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un intercambio con varios grupos, devolverá una confirmación para cada grupo. Si un grupo contiene varios conjuntos de transacciones, la confirmación para dicho grupo contendrá varios bucles AK2, uno para cada conjunto de transacciones, en función de si se generan bucles AK2 para los conjuntos de transacciones aceptados. Para obtener más información sobre el contenido de una confirmación 997, consulte [X12 confirmación 997](../core/x12-997-acknowledgment.md).  
  
> [!NOTE]
>  Cuando la canalización de recepción EDI genera el segmento Encabezado de grupo funcional (GS) para la confirmación funcional de X12, el código del remitente de aplicación (GS02) y el código de receptor de la aplicación (GS03) se tomarán del grupo funcional que se va a confirmar. Sin embargo, se asigna GS02 en un mensaje entrante en GS03 en la confirmación y GS03 en un mensaje entrante se asigna a GS02 en la confirmación.  
  
## <a name="edifact-acknowledgments"></a>Confirmaciones EDIFACT  
 **Confirmación técnica de EDIFACT**  
  
 Para EDIFACT, no se usa una confirmación técnica independiente pero las secciones de la confirmación funcional o la confirmación CONTRL (vea a continuación) se vuelven a usar para la confirmación de recepción. Esto simula una confirmación técnica.  
  
 Para obtener más información sobre la confirmación CONTRL técnica, consulte [mensaje CONTRL de EDIFACT como confirmación técnica](../core/edifact-contrl-message-as-technical-acknowledgment.md).  
  
 **Confirmación funcional de EDIFACT**  
  
 Para EDIFACT, la confirmación funcional CONTRL se usa para confirmar un intercambio recibido, grupo y mensaje; aceptar o rechazar un intercambio recibido, grupo y mensaje y para enumerar los errores sintácticos o funcionalidades no admitidas que se contengan en ellos. La confirmación CONTRL genera el informe de los resultados de una comprobación sintáctica del intercambio completo recibido.  
  
 Para obtener más información sobre la confirmación CONTRL funcional, vea [mensaje CONTRL de EDIFACT como confirmación funcional](../core/edifact-contrl-message-as-functional-acknowledgment.md).  
  
## <a name="when-an-acknowledgment-is-generated"></a>Cuándo se publica una confirmación  
 La canalización de recepción EDI generará una confirmación si se cumplen algunas de las siguientes condiciones:  
  
-   Un elemento de datos en el intercambio recibido recibe la confirmación. Para mensajes codificados en X12, la canalización de recepción generará una confirmación técnica de TA1 si el elemento de datos ISA14 está establecido en 1. Para los mensajes con codificación EDIFACT, la canalización de recepción generará una técnica de CONTRL ACK si el elemento de datos UNB9 está establecido en 2 y generará una ACK CONTRL funcional si el elemento de datos UNB9 está establecido en 1.  
  
-   Una propiedad de acuerdo solicita la confirmación. Para los intercambios X12, estas propiedades son la **TA1 esperado** y **997 esperado** propiedades en el **confirmaciones** página de las fichas de acuerdo bidireccional de la **Propiedades del acuerdo de** cuadro de diálogo. Para los intercambios EDIFACT, estas propiedades son la **recepción del mensaje (CONTRL) esperada** y **confirmación (CONTRL) esperada** en el **confirmaciones** página de las fichas de acuerdo bidireccional de la **propiedades del acuerdo de** cuadro de diálogo. Cuando habilite un tipo de confirmación, puede también indicar si procesar por lotes ese tipo de confirmación.  
  
-   Una propiedad global solicita la confirmación cuando no se determina ningún acuerdo para el intercambio. Estas propiedades son  
  
    -   **TA1 esperado** y **997 esperado** propiedades en el **confirmaciones** página de la pestaña del acuerdo el **X12 configuración de reserva** cuadro de diálogo.  
  
    -   **Recepción del mensaje (CONTRL) esperada** y **confirmación (CONTRL) esperada** en el **confirmaciones** página de la pestaña del acuerdo el **reserva de EDIFACT Configuración de** cuadro de diálogo.  
  
 Para EDIFACT, la canalización de recepción EDI devolverá dos confirmaciones CONTRL independientes si se solicitan la confirmación técnica y la confirmación funcional. La confirmación CONTRL incluirá sólo la información de confirmación de recepción. La confirmación funcional CONTRL incluirá información de recepción e información de confirmación funcional. Para obtener más información, consulte [confirmación CONTRL de EDIFACT](../core/edifact-contrl-acknowledgment.md).  
  
## <a name="identifying-an-acknowledgment-with-a-control-number"></a>Identificar una confirmación con un número de control  
 Cada confirmación necesita identificarse mediante un número de control de conjunto de transacciones para X12 (el elemento de datos ST2) o un número de referencia de conjunto de transacciones para EDIFACT (el elemento de datos UNH1). Si se configura un acuerdo para la confirmación saliente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] definirá el número de referencia o control del conjunto de transacciones en el valor definido para el acuerdo basándose en lo siguiente:  
  
-   **Para X12 confirmaciones** – (**número de Control de confirmación (ST02)** propiedad en **configuración de Host Local** página (**configuración del receptor** sección) del acuerdo pestaña **propiedades del acuerdo de** cuadro de diálogo  
  
-   **Para confirmaciones EDIFACT** – (**número de Control de confirmación de Edifact** propiedad en **configuración de Host Local** página (**configuración del receptor** sección) de la ficha de acuerdo **propiedades del acuerdo de** cuadro de diálogo  
  
 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no determina el acuerdo para la confirmación, usará las mismas propiedades como mencionadas anteriormente, pero está disponible en la ficha de acuerdo en el **X12 configuración de reserva** ad **reserva de EDIFACT Configuración** cuadros de diálogo. Esta configuración se aplica a las confirmaciones funcionales y técnicas si ambas están configuradas. Este entero se aumentará en uno para cada confirmación o intercambio generados.  
  
 El sobre de una canalización se crea a partir de los datos en los mensajes recibidos de acuerdo con el esquema de control de confirmaciones.  
  
## <a name="preparing-the-acknowledgment"></a>Preparar la confirmación  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera el sobre para una confirmación como si generara un sobre para un mensaje examinando las definiciones del Encabezado de control de intercambio y el Encabezado de grupo funcional. Para obtener más información, consulte [resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).  
  
 Para habilitar el enrutamiento perfecto de la confirmación generada (TA1, 997 o CONTRL), el desensamblador EDI rellenará las propiedades `DestinationPartyReceiverQualifier`, `DestinationPartyReceiverIdentifier`, `DestinationPartySenderQualifier` y `DestinationPartySenderIdentifier` en la confirmación.  
  
## <a name="synchronous-and-asynchronous-acknowledgments"></a>Confirmaciones sincrónicas y asíncronas  
 Tiene la posibilidad de enviar confirmaciones EDI de forma sincrónica o asíncrona. Si es sincrónica, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enrutará la confirmación directamente a la canalización de envío de un puerto de recepción de solicitud-respuesta bidireccional. Si es asíncrono, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enrutará la confirmación al cuadro de mensajes y se suscribirá un puerto de envío a ese mensaje.  
  
 Para especificar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía la confirmación sincrónicamente, seleccione **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta** en el **configuración de Host Local** página ( **Configuración del receptor** sección) en **configuración de intercambio** en la ficha de acuerdo bidireccional (para acuerdos de X12 y EDIFACT). Si desactiva esta propiedad, la canalización de envío del puerto de recepción bidireccional debe establecerse para devolver un intercambio EDI.  
  
 Si un escenario usar un puerto de recepción solicitud-respuesta, y tanto la confirmación técnica como la confirmación funcional están habilitadas, la confirmación técnica se volverá a enviar de forma sincrónica y la funcional de forma asíncrona.  
  
 Cuando se recibe un mensaje con codificación EDDINT/AS2 a través de HTTP/HTTPS, si se envía un MDN en respuesta a una carga EDI envuelta de MIME (en el mismo socket), no se enviará una confirmación EDI de forma sincrónica. Si en este caso el **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta** propiedad está activada, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ignorará la propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Estructura de confirmación EDI](../core/edi-acknowledgment-structure.md)   
 [Servicio EDI y esquemas de Control](../core/edi-service-and-control-schemas.md)   
 [X12 confirmación TA1](../core/x12-ta1-acknowledgment.md)   
 [X12 confirmación 997](../core/x12-997-acknowledgment.md)   
 [Confirmación CONTRL de EDIFACT](../core/edifact-contrl-acknowledgment.md)   
 [Mensaje de CONTRL de EDIFACT como confirmación técnica](../core/edifact-contrl-message-as-technical-acknowledgment.md)   
 [Mensaje de CONTRL de EDIFACT como confirmación funcional](../core/edifact-contrl-message-as-functional-acknowledgment.md)