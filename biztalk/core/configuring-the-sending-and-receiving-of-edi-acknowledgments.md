---
title: "Configurar el envío y recepción de confirmaciones EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3db1c9f7-bafa-4659-a3c4-0faa56606081
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d1ffc367e4b87d29e372bc434c0eda18da4363a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-the-sending-and-receiving-of-edi-acknowledgments"></a>Configuración del envío y la recepción de confirmaciones EDI
Para configurar el envío de una confirmación de EDI en respuesta a un intercambio recibido, debe hacer lo siguiente:  
  
-   Habilite la confirmación en el acuerdo en el que se ha resuelto el intercambio recibido. De esta manera, declara que la entidad que envía el intercambio espera una confirmación.  
  
-   Si la confirmación debe devolverse con propiedades específicas definidas, como CR LF habilitado, que los caracteres separadores sean diferentes, etc., defina estas propiedades en la otra ficha del acuerdo unidireccional. De esta manera, configura la forma en que la entidad devuelve la confirmación.  
  
    > [!NOTE]
    >  Si un intercambio se resuelve en un acuerdo definido en el **entidad -> PartyB** ficha, las propiedades relacionadas con el modo en que debe generarse la confirmación se configuran en el **PartyB -> entidad** ficha. Esto es necesario porque las propiedades de contexto de confirmación para el remitente y receptor calificadores se establecen en el efecto contrario de los valores especificados en la **entidad -> PartyB** ficha. Por ejemplo, si los identificadores del remitente y el destinatario se configuran en ELLOS y NOSOTROS en el acuerdo en el cual se resuelve el mensaje de intercambio, las propiedades de contexto del remitente y el destinatario se configurarán en NOSOTROS y ELLOS en la confirmación. Normalmente, la otra ficha de acuerdo unidireccional también tendrá los identificadores de remitente y receptor configurados respectivamente en NOSOTROS y ELLOS. Por lo tanto, el mensaje de confirmación se resolverá en dicho acuerdo y se seleccionará la configuración de propiedades. Por lo tanto, si desea tener confirmación para usar diferentes separadores de elementos o si desea tener confirmación para usar CR LF, especifique las propiedades en el **PartyB -> entidad** ficha.  
  
     Conceptualmente, las propiedades para la confirmación se seleccionarán desde cualquier ficha de acuerdo unidireccional que tenga los mismos calificadores de remitente y receptor que están configurados en las propiedades de contexto de la confirmación. No obstante, para facilitar su uso en la práctica, normalmente debe configurar esto en la otra ficha de acuerdo unidireccional del acuerdo que creó en el cual debe haberse resuelto el intercambio.  
  
-   Si usted es una entidad que devuelve una confirmación de EDI a la entidad que envió el intercambio original, configure un puerto de envío unidireccional para seleccionar la confirmación y envío o bien un puerto de recepción bidireccional para enviar la confirmación. Para obtener más información, consulte [configurar un puerto de envío estático para enviar intercambios EDI y confirmaciones](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md).  
  
-   Si usted es una entidad que espera una confirmación de EDI, configure un puerto de envío bidireccional o un puerto de recepción unidireccional para recibir la confirmación. Para obtener más información, consulte [configurar un puerto para recibir mensajes de EDI y confirmaciones](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md).  
  
-   La aplicación EDI de BizTalk contiene los esquemas de control. Como consecuencia, la aplicación que contiene su solución EDI debe contener una referencia a la aplicación EDI de BizTalk. Para obtener más información, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-request-an-acknowledgment-for-the-party-that-sent-the-original-interchange"></a>Para solicitar una confirmación para la entidad que envió el intercambio original  
  
1.  > [!NOTE]
    >  Realizando los pasos de este procedimiento, configura que la entidad que envía el intercambio espera una confirmación.  
  
     En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo. En el **entidades y perfiles empresariales** página, haga clic en la entidad que tenga el acuerdo para la que necesita habilitar la confirmación. En el **acuerdo** sección de la página, haga clic en el acuerdo y haga clic en **propiedades**. En el **propiedades del acuerdo de** cuadro de diálogo, en la ficha de acuerdo unidireccional (a la que se resolverá el intercambio entrante), haga lo siguiente:  
  
    1.  En el **identificadores** página, escriba los valores para el remitente y receptor calificadores.  
  
         Para una confirmación codificada con X12, introduzca valores para ISA5, ISA6, ISA7 e ISA8. Para ISA5 e ISA6, introduzca valores para la entidad que va a enviar el intercambio. Para ISA7 e ISA8, introduzca valores para la entidad que va a recibir el intercambio.  
  
         Para una confirmación codificada con EDIFACT, introduzca valores para UNB2.1, UNB2.2, UNB3.1 y UNB3.2. Para UNB2.1 y UNB2.2, introduzca valores para la entidad que va a enviar el intercambio. Para UNB3.1 y UNB3.2, introduzca valores para la entidad que va a recibir el intercambio.  
  
    2.  En el **confirmaciones** página, seleccionados propiedades que definen el tipo de confirmación que espera la entidad remitente:  
  
         Para X12 confirmaciones, seleccionadas **TA1 esperado** o **997 esperado** según las confirmaciones que se espera. Para cada tipo de confirmación, seleccione **no procesar por lotes \<tipo ACK\>**  si desea que cada instancia de una confirmación que se envían como un intercambio independiente.  
  
         Para confirmaciones EDIFACT, seleccione **recepción del mensaje (CONTRL) esperada** o **confirmación (CONTRL) esperada** según las confirmaciones que se espera. Para cada tipo de confirmación, seleccione **no procesar por lotes \<tipo ACK\>**  si desea que cada instancia de una confirmación que se envían como un intercambio independiente.  
  
    3.  En el **configuración de Host Local** página en el **configuración de intercambio** sección, desactive el **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta** para devolver el confirmación de forma asincrónica a través de un puerto de envío unidireccional. Mantenga esta propiedad seleccionada para devolver la confirmación de forma síncrona por un puerto de recepción bidireccional.  
  
    4.  En el **puertos de envío** página, en la **nombre** columna de la **puertos de envío** cuadrícula, seleccione el puerto de envío que se ha configurado para enviar la confirmación.  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa esta configuración de puerto de envío para determinar qué entidad usar al procesar el mensaje. Para obtener más información, consulte [resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).  
  
        > [!NOTE]
        >  Si no ha configurado el puerto de envío, puede que tenga que realizar este paso más adelante.  
  
### <a name="to-configure-how-the-party-sends-the-acknowledgement-back"></a>Para configurar cómo devuelve la entidad la confirmación  
  
1.  > [!NOTE]
    >  Realizando los pasos de este procedimiento, configura cómo devuelve una confirmación la entidad que recibió el intercambio.  
  
     En la misma **propiedades del acuerdo de** cuadro de diálogo, en la ficha de acuerdo unidireccional, haga lo siguiente:  
  
    1.  En el **identificadores** página, escriba los valores para el remitente y receptor calificadores.  
  
        > [!NOTE]
        >  Al enviar la confirmación, la entidad que recibió el intercambio original se convierte en el remitente, mientras que la entidad que envió el intercambio original pasa a ser el receptor. Por lo tanto, los valores que introduzca en la página Identificadores serán ahora los opuestos de los que introdujo en la ficha del acuerdo unidireccional en el paso anterior. Con esto se consiguen dos fines:  
        >   
        >  -   Que la confirmación que se está devolviendo se resuelva en este acuerdo unidireccional que está creando, pues las propiedades de contexto de remitente y receptor en la confirmación coincidirán con los valores de remitente y receptor que está introduciendo ahora en la página Identificadores.  
        > -   Cualquier personalización que desee incluir en la confirmación puede configurarse en esta ficha del acuerdo. Por ejemplo, puede usar otros separadores, elegir que esté habilitado CR LF, etc.  
  
         Para una confirmación codificada con X12, introduzca valores para ISA5, ISA6, ISA7 e ISA8. Para ISA5 e ISA6, introduzca valores para la entidad que va a enviar la confirmación (que será la misma entidad que recibió el intercambio original). Para ISA7 e ISA8, introduzca valores para la entidad que va a recibir la confirmación (que será la misma entidad que envió el intercambio original).  
  
         Para una confirmación codificada con EDIFACT, introduzca valores para UNB2.1, UNB2.2, UNB3.1 y UNB3.2. Para UNB2.1 y UNB2., introduzca valores para la entidad que va a enviar la confirmación (que será la misma entidad que recibió el intercambio original). Para UNB3.1 y UNB3.2, introduzca valores para la entidad que va a recibir la confirmación (que será la misma entidad que envió el intercambio original).  
  
    2.  Para obtener una confirmación X12 o EDIFACT, si es necesario, en el **juego de caracteres y separadores** página, especifique los separadores que desea usar en la confirmación. También puede especificar si la confirmación debe usar un sufijo CR LF.  
  
    3.  Para obtener una confirmación EDIFACT, si es necesario, en el **sobres** página en el **configuración de intercambio** sección, especifique si la confirmación debe incluir una ni un segmento UNG seleccionando el opciones adecuadas.  
  
## <a name="see-also"></a>Vea también  
 [Configurar confirmaciones EDI](../core/configuring-edi-acknowledgments.md)   
 [Servicio EDI y esquemas de Control](../core/edi-service-and-control-schemas.md)   
 [Enviar una confirmación EDI](../core/sending-an-edi-acknowledgment.md)   
 [Cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md)   
 [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)