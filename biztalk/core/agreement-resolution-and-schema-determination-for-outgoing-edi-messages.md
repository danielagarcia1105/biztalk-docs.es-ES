---
title: Resolución de acuerdos y determinación de esquemas para mensajes EDI salientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e37aeb9d-1e95-464d-bb71-73653c1d4674
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a718f386686b8a23bc8c97108b94b5fba717ee90
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992029"
---
# <a name="agreement-resolution-and-schema-determination-for-outgoing-edi-messages"></a>Resolución de acuerdos y determinación de esquemas para los mensajes EDI salientes
Para generar un mensaje EDI a un socio comercial, la canalización de envío EDI debe efectuar lo siguiente:  
  
-   Determinar el acuerdo en el que se resuelve el mensaje  
  
-   Determinar el esquema que se va a usar para validar el mensaje  
  
## <a name="agreement-resolution"></a>Resolución de acuerdos  
 La canalización de envío EDI lleva a cabo la búsqueda de acuerdos mediante la realización de una serie de pasos para determinar si hay una coincidencia entre el intercambio saliente y las propiedades de un acuerdo. Una vez que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ha determinado el acuerdo, determina el esquema del documento que se aplica al intercambio (véase a continuación). Usa las propiedades asociadas al acuerdo coincidente y el esquema correspondiente para generar y validar el mensaje saliente.  
  
 Para llevar a cabo la resolución de acuerdos, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realiza los siguientes pasos:  
  
1. Resuelve el acuerdo al hacer coincidir la propiedad de contexto AgreementPartIDForSend con el identificador del acuerdo unidireccional. Esta propiedad debe ser de tipo entero y se puede establecer en un componente personalizado; no la establece [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2. Si el paso 1 no funciona, resuelve el acuerdo haciendo coincidir la tres propiedades de contexto siguientes con las propiedades del acuerdo: AgreementNameForSend, SenderPartyNameForSend y ReceiverPartyNameForSend. Tenga en cuenta que las tres propiedades deben estar configuradas para que se puedan resolver correctamente en un acuerdo. Estas propiedades se pueden configurar en un componente personalizado; no las configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
3. Si el paso 2 no funciona, resuelve el acuerdo haciendo coincidir el nombre de la entidad en las propiedades de contexto de mensaje con la propiedad DestinationPartyName, que se ha establecido como resolución de acuerdo adicional en el **identificadores** ficha de propiedades del acuerdo.  
  
4. Si el paso 3 no funciona, resuelve el acuerdo haciendo coincidir las propiedades siguientes del contexto de un mensaje con las de las propiedades del acuerdo: DestinationPartySenderIdentifier, DestinationPartySenderQualifier, DestinationPartyReceiverIdentifier y DestinationPartyReceiverQualifier. Tenga en cuenta que las cuatro propiedades deben estar configuradas para que se puedan resolver correctamente en un acuerdo. Estas propiedades pueden establecerse en un componente personalizado; no se establecen [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, vea la información que aparece abajo.  
  
   > [!NOTE]
   >  Si algunos de los anteriores conjuntos de propiedades de contexto se promocionan y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no encuentra un acuerdo asociado con estas propiedades de contexto, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspende el mensaje.  
   > 
   >  Si el usuario escribe intencionadamente un conjunto de propiedades de contexto para la resolución del acuerdo y la resolución no puede identificar el acuerdo unidireccional, el mensaje se suspende. Si un acuerdo no se puede resolver según un conjunto de propiedades de contexto, se lanza el correspondiente mensaje de advertencia en el registro de eventos.  
  
5. Si el paso 4 no funciona o no se promociona ninguna de las anteriores propiedades de contexto, el mensaje EDI se resuelve en un acuerdo mediante la coincidencia del puerto de envío que se ha suscrito al mensaje con el puerto de envío asociado a un acuerdo.  
  
   > [!NOTE]
   >  Si el mismo puerto de envío está asociado a varios acuerdos, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará un error.  
  
6. Si no se encuentra ningún acuerdo en los pasos 1, 2, 3 o 4, la canalización de envío usa la configuración del acuerdo de reserva para generar el mensaje saliente.  
  
   **Resolución del acuerdo haciendo coincidir las propiedades de contexto de receptor y remitente**  
  
   En el segundo paso anterior, las cuatro propiedades de contexto usadas en la coincidencia son EDI.DestinationPartySenderIdentifier, EDI.DestinationPartySenderQualifier, EDI.DestinationPartyReceiverIdentifier y EDI.DestinationPartyReceiverQualifier. El espacio de nombres para estas propiedades de contexto es `http://schemas.microsoft.com/Edi/PropertySchema`. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] intenta hacer coincidir estos valores con el remitente y los identificadores del receptor y calificadores en las propiedades del acuerdo unidireccional. Para X12, estos campos son ISA05, ISA06, ISA07 e ISA08 en el **identificadores** página de la ficha de acuerdo unidireccional en el **las propiedades del acuerdo** cuadro de diálogo; para EDIFACT, estos campos son UNB2.1, UNB2.2, UNB3.1 y UNB3.2 en la **identificadores** página de la ficha de acuerdo unidireccional en el **las propiedades del acuerdo** cuadro de diálogo.  
  
   Para habilitar la resolución del acuerdo en el lado del envío mediante los cuatro calificadores e identificadores de remitente y receptor, deberá establecer las cuatro propiedades de contexto. De este modo, se identifica el acuerdo de forma exclusiva. Con este método de búsqueda de acuerdo conseguirá mayor flexibilidad en el procesamiento de envío. Por ejemplo, mediante este método podría evitar la creación de varios puertos de envío en algunas circunstancias, así como filtros de puerto de envío complicados. También permite evitar establecer la propiedad OneWayAgreementId, si así lo desea.  
  
   Si las cuatro propiedades de contexto se han establecido para un mensaje y no se ha encontrado ninguna coincidencia entre las propiedades de contexto y las de propiedad, el mensaje se suspende. El acuerdo se resolverá mediante el puerto de envío asociado con un acuerdo únicamente si no se han establecido las cuatro propiedades de contexto.  
  
> [!NOTE]
>  Un mensaje en la canalización EDI va al paso siguiente en la resolución del acuerdo hasta que el mensaje se resuelva con el paso que tiene el acuerdo en estado habilitado. Por ejemplo, si el mensaje se resuelve en el primer paso de resolución del acuerdo, pero el acuerdo se encuentra en estado deshabilitado, el mensaje va al paso siguiente para su resolución.  
  
## <a name="schema-determination"></a>Determinar el esquema  
 La canalización de envío EDI determina el esquema que se aplica al mensaje desde el nombre de esquema y el espacio de nombres de esquema que se incluyen en el archivo XML intermediario para cada conjunto de transacciones (como información de tipo de documento o en el nodo raíz).  
  
 Para un intercambio que se ha conservado, la canalización de envío usa la información de tipo de documento en los conjuntos de transacciones individuales del archivo XML intermediario para el intercambio completo. Usa los esquemas de segmento de control para procesar los segmentos de sobre.  
  
## <a name="see-also"></a>Vea también  
 [Cómo envía BizTalk Server los mensajes EDI](../core/how-biztalk-server-sends-edi-messages.md)