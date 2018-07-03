---
title: Resolución de acuerdos, detección de esquemas y autorización para los mensajes EDI recibidos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 503e307c-4cb0-49b5-8751-82dcea203151
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0af984b0665c3ef4d567d3a3dd032232139f7d64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006405"
---
# <a name="agreement-resolution-schema-discovery-and-authorization-for-received-edi-messages"></a>Resolución de acuerdos, detección de esquemas y autorización para los mensajes EDI recibidos
Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje EDI, la canalización de recepción EDI realiza la búsqueda de acuerdos de socio comercial, la detección de esquemas y los procesos de autorización para determinar el modo en que se procesa el mensaje.  
  
## <a name="agreement-resolution"></a>Resolución de acuerdos  
 La canalización de recepción EDI lleva a cabo la resolución de acuerdos de socios comerciales mediante la realización de una serie de pasos para determinar si hay una coincidencia entre los campos de encabezado del mensaje y las propiedades en la definición del acuerdo. Una vez que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ha determinado el acuerdo, determina el esquema del documento que se aplica al intercambio (véase a continuación). Usa las propiedades asociadas al acuerdo coincidente y el esquema correspondiente para validar y procesar el mensaje recibido.  
  
 Para llevar a cabo la resolución de acuerdos, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realiza los siguientes pasos:  
  
1. Resolver el acuerdo mediante la coincidencia del calificador e identificador del remitente y el calificador e identificador del receptor en el encabezado del intercambio con los de las propiedades de un acuerdo.  
  
2. Si el paso 1 no funciona, resuelve el acuerdo mediante la coincidencia solo con el calificador e identificador de remitente en el encabezado del intercambio con los de las propiedades de un acuerdo. Además, como no funcionó el primer paso, se puede asumir con seguridad que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] va a recibir el mensaje. Por lo tanto, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] intenta hacer coincidir el calificador e identificador del receptor con lo siguiente:  
  
   -   Valores “BT” y “HostX12Recvr” (para mensajes con codificación X12) y  
  
   -   Valores “BT” y “HostEdifactRecvr” (para mensajes con codificación EDIFACT)  
  
   > [!IMPORTANT]
   > - **BizTalk Server 2013 R2, 2013 y 2010**: campos The ISA5, ISA6, ISA7, ISA8, UNB2.1, UNB2.2, UNB3.1 y UNB3.2 son obligatorios en la configuración del acuerdo.  
   >   -   **BizTalk Server 2009 y 2006 R2**: campos The ISA7, ISA8, UNB3.1 y UNB3.2 no son obligatorios en la configuración de la entidad. Si los campos se dejan en blanco, el motor de EDI generará una resolución basada en los valores de ISA5, ISA6, UNB2.1 y UNB2.2.  
   >   -   Para que las resoluciones de BizTalk Server 2009 y 2006 R2 sean compatibles con las nuevas versiones de BizTalk Server, se introducen los identificadores codificados de forma rígida (HostX12Recvr y HostEdifactRecvr) y el calificador (BT).  
   >   -   Los mensajes EDIFACT deberían seguir la [instrucciones UNECE](http://www.unece.org/tradewelcome/areas-of-work/un-centre-for-trade-facilitation-and-e-business-uncefact/outputs/standards/unedifact/tradeedifactrules.html) para las reglas y sintaxis de mensajes.  
  
3. Si el paso 2 no funciona, use las propiedades del acuerdo de reserva.  
  
   En el primer paso, para X12 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará los siguientes valores para realizar la coincidencia:  
  
- ISA05 (calificador de remitente)  
  
- ISA06 (identificador de remitente)  
  
- ISA07 (calificador de receptor)  
  
- ISA08 (identificador de receptor)  
  
  Para EDIFACT, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará los siguientes valores para realizar la coincidencia:  
  
- UNB2.1 (identificador de remitente)  
  
- UNB2.2 (calificador de remitente)  
  
- UNB3.1 (identificador de receptor)  
  
- UNB3.2 (calificador de receptor)  
  
  Las propiedades del acuerdo usadas para la coincidencia se definen en el **identificadores** página de las fichas de acuerdos específicos de la dirección de la **las propiedades del acuerdo** cuadro de diálogo.  
  
  Estas cuatro propiedades de envío y recepción identifican el acuerdo de socio comercial de forma exclusiva. El uso de las cuatro propiedades proporciona mayor flexibilidad al procesamiento de la recepción. Por ejemplo, es posible que este método de resolución de acuerdos permita el envío de confirmaciones a varias entidades sin crear varios puertos de envío.  
  
  En caso de que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no pueda resolver el acuerdo mediante los cuatro calificadores e identificadores de remitente y receptor, tratará de resolver el acuerdo solo con el calificador e identificador de remitente. Para X12, estos campos son ISA05 e ISA06; para EDIFACT, estos campos son UNB2.1 y UNB2.2. Al igual que con una coincidencia de propiedades de remitente y receptor, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] coincide con los valores del encabezado del intercambio con las propiedades del acuerdo definidas en el **identificadores** página de las fichas de acuerdos específicos de la dirección de la **Las propiedades del acuerdo** cuadro de diálogo. Si solo el calificador de remitente y el identificador se usan para resolver el acuerdo, el calificador e identificador deberían no estar definidos en la pestaña del acuerdo bidireccional del **las propiedades del acuerdo** cuadro de diálogo.  
  
  Si no se encuentra el acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el acuerdo de reserva para socios comerciales, a menos que la configuración del puerto requiera autenticación. Si la configuración del puerto requiere autenticación (si **eliminar mensajes si hay errores de autenticación** o **conservar mensajes si hay errores de autenticación** está seleccionado en el **General** página de la **propiedades de puerto de recepción**), un contrato es necesario para cualquier intercambio recibido por el puerto de recepción. En este caso, si el acuerdo no se resuelve haciendo coincidir el encabezado de intercambio con las propiedades de intercambio, no se permite usar las propiedades del acuerdo de reserva para determinar el acuerdo. El intercambio se tratará como si se hubiese producido un error en la autenticación en caso de que no se encuentre ningún acuerdo, y se suspenderá.  
  
> [!NOTE]
>  Un mensaje en la canalización EDI va al paso siguiente en la resolución del acuerdo hasta que el mensaje se resuelva con el paso que tiene el acuerdo en estado habilitado. Por ejemplo, si el mensaje se resuelve en el primer paso de resolución del acuerdo, pero el acuerdo se encuentra en estado deshabilitado, el mensaje va al paso siguiente para su resolución.  
  
## <a name="schema-discovery"></a>Detección de esquemas  
 Una vez que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] haya determinado el acuerdo que se resuelve en el mensaje, debe determinar el esquema que se debe utilizar para validar y procesar el mensaje. Lo hace mediante las propiedades identificadas en el **configuración de Host Local** página de unidireccional (lado de envío) pestaña del acuerdo de la **las propiedades del acuerdo** cuadro de diálogo.  
  
 Para determinar el esquema, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe determinar, en primer lugar, el espacio de nombres del esquema. El desensamblador EDI usará un espacio de nombres predeterminado para los esquemas estándar incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o determinará el espacio de nombres que se va a usar para un esquema personalizado.  
  
 El **configuración de Host Local** página de la ficha de acuerdo unidireccional de la **las propiedades del acuerdo** cuadro de diálogo le permite configurar una cuadrícula de valores para determinar un espacio de nombres personalizado. Si no se encuentra ninguna coincidencia en la cuadrícula, el Desensamblador EDI utiliza el espacio de nombres predeterminado en el **espacio de nombres de destino** campo marcado para la fila predeterminada.  
  
### <a name="x12-schema-discovery"></a>Detección de esquemas X12  
 Para los mensajes con codificación X12, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina un espacio de nombres personalizado mediante el identificador de remitente de la aplicación (GS02) y el identificador de conjunto de transacciones (ST01) del encabezado del intercambio entrante. Intenta buscar una coincidencia entre estos valores y los valores de las propiedades GS02 y ST01 de la **personalizar espacio de nombres de destino** cuadrícula en el **configuración de Host Local** página (en **transacciones Configuración del conjunto de**) de la ficha de acuerdo bidireccional del **las propiedades del acuerdo** cuadro de diálogo. Si encuentra a una coincidencia, usará el espacio de nombres identificado en la misma fila de la cuadrícula para determinar el esquema a nosotros para validar y procesar el mensaje. En caso de que no se determine el espacio de nombres de destino, se usará el espacio de nombres de destino predeterminado. Si no se identifica ningún espacio de nombres en el **espacio de nombres de destino** marcado para la fila de forma predeterminada, el campo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará el espacio de nombres identificado en las propiedades de acuerdo de reserva para mensajes codificados en X12, cuyo valor predeterminado es `http://schemas.microsoft.com/BizTalk/Edi/X12/2006`.  
  
 Para los intercambios X12, una vez detectado el espacio de nombres de destino, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina el esquema mediante la siguiente información:  
  
- El espacio de nombres de destino que acaba de detectar.  
  
- La versión o el lanzamiento de los primeros cinco caracteres de ST03 (si GS07 == X - Accredited Standards Committee X12). Si ST03 no está presente, no es válido o no origina la resolución del esquema, la versión viene determinada por los cinco primeros caracteres de GS08 o de ISA12 (si GS07 != X).  
  
- El tipo de documento en ST01.  
  
  El desensamblador EDI concatena el tipo de codificación, la versión, el lanzamiento y el tipo de documento para determinar el nombre del esquema, por ejemplo, "X12_00401_864". A continuación, concatena el espacio de nombres de destino con el nombre de esquema, por ejemplo, `http://schemas.microsoft.com/BizTalk/Edi/X12/2006/X12#X12_00401_864`.  
  
  Para un intercambio de HIPAA 837 entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite tres esquemas de HIPAA 837:  
  
|Esquema 837|Valor de GS08 en la versión 4010|Valor de GS08/ST03 en la versión 5010|  
|----------------|--------------------------------|--------------------------------------|  
|Claim-Dental_837D|004010X097A1|005010X224A1|  
|Claim-Institutional_837I|004010X096A1|005010X223A1|  
|Claim-Professional_837P|004010X098A1|005010X222|  
  
> [!NOTE]
>  En las versiones HIPAA, para el conjunto de transacciones 278 (Revisión de servicios de asistencia sanitaria), tanto los pares de solicitud como los de respuesta comparten el mismo valor para GS08 y ST01. En función de los valores del desencadenador en el campo BHT02, puede diferenciar entre una Solicitud / Respuesta 278 en la versión 5010:  
> 
> 1. Cualquiera de los valores 01, 13 y 36 en BHT02 indica una Solicitud de revisión de servicios de asistencia sanitaria  
>    2.  11 en BHT02 indica Respuesta de revisión de servicios de asistencia sanitaria  
  
### <a name="edifact-schema-discovery"></a>Detección de esquemas EDIFACT  
 Para mensajes con codificación EDIFACT, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina un espacio de nombres personalizado mediante el tipo de mensaje (UNH2.1), el número de versión del mensaje (UNH2.2), el número de lanzamiento del mensaje (UNH2.3), el código asignado (UNH2.5), el identificador de grupo funcional (UNG2.1) y el calificador de código de envío de la aplicación (UNG2.2) del encabezado del intercambio entrante. A continuación, intenta buscar una coincidencia entre estos valores y los valores de las propiedades UNH2.1, UNH2.2, UNH2.3, UNH2.5, UNG2.1 y UNG2.2 en la **personalizar espacio de nombres de destino** cuadrícula (bajo **configuración del conjunto de transacciones**) de la pestaña del acuerdo bidireccional del **las propiedades del acuerdo** cuadro de diálogo. Si encuentra a una coincidencia, usará el espacio de nombres identificado en la misma fila de la cuadrícula para determinar qué esquema utilizar para validar y procesar el mensaje. En caso de que no se determine el espacio de nombres de destino, se usará el espacio de nombres de destino predeterminado. Si no se identifica ningún espacio de nombres en el **espacio de nombres de destino** marcado para la fila de forma predeterminada, el campo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará el espacio de nombres identificado en las propiedades del acuerdo de reserva para mensajes codificados en EDIFACT, cuyo valor predeterminado es `http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`.  
  
 Para los intercambios EDIFACT, una vez detectado el espacio de nombres de destino, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina el esquema mediante la siguiente información:  
  
- El espacio de nombres de destino acaba de detectar.  
  
- El número de versión del mensaje en UNH2.2.  
  
- El número de versión del mensaje en UNH2.3.  
  
- El tipo de mensaje en UNH2.1.  
  
- El código asignado en UNH2.5.  
  
  El desensamblador EDI concatena el tipo de codificación, la versión, el lanzamiento y el tipo de mensaje para determinar el nombre del esquema, por ejemplo, " EFACT_D94A_CONTEN". A continuación, concatena el espacio de nombres de destino con el nombre de esquema, por ejemplo, `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006/EFACT#EFACT_D94A_CONTEN`.  
  
  Si UNH2.5 está presente en el mensaje, el desensamblador EDI tratará primero de encontrar un esquema coincidente usando el valor UNH2.5 como parte del nombre del esquema, por ejemplo “EFACT_D94A_CONTEN_TEST”. Si no se encuentra ningún esquema coincidente, el desensamblador EDI regresará para buscar el esquema sin el valor UNH2.5.  
  
## <a name="authorization"></a>Autorización  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprueba los valores de los campos de autorización y seguridad definidos para el acuerdo con los campos del mensaje. En caso de que haya una falta de coincidencia, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspenderá el intercambio. Para los mensajes codificados con EDIFACT, estos campos son la contraseña de referencia del destinatario (UNB6.1 y UNB6.2). Para los mensajes codificados con X12, estos campos son el calificador y la información de autorización (ISA1-2), y el calificador y la información de seguridad (ISA3-4).  
  
## <a name="see-also"></a>Vea también  
 [Cómo recibe BizTalk Server los mensajes EDI](../core/how-biztalk-server-receives-edi-messages.md)