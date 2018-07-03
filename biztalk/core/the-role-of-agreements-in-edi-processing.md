---
title: Rol de los acuerdos del procesamiento EDI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d81b0449-6656-49f7-a781-5fd60031b3d5
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2125ca348cc8f333b1b223404371ae13b113fe1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980437"
---
# <a name="the-role-of-agreements-in-edi-processing"></a>Rol de los acuerdos en el procesamiento de EDI
Una organización usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes EDI de uno o varios socios comerciales, así como para enviar mensajes EDI a ellos. A su vez, los socios comerciales definen perfiles de negocio que son entidades de negocio dentro de una organización. La forma en que los perfiles de negocio intercambian mensajes se define como parte de los acuerdos entre socios comerciales de dos perfiles de negocio. Para obtener más información, consulte [bloques de creación de una solución de administración de socios comerciales](../core/building-blocks-of-a-trading-partner-management-solution.md).  
  
 Los acuerdos de socios comerciales se crean en la interfaz de usuario de administración de socios comerciales (TPM). Las pantallas TPM se encuentran en el **partes** nodo de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="configuring-an-agreement-for-edi-processing"></a>Configuración de un acuerdo para el procesamiento de EDI  
 Todos los socios comerciales que intercambiarán mensajes EDI con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deben ponerse de acuerdo en los parámetros de comunicación. Después de ello, la organización que hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe crear los socios comerciales en TPM (incluido un socio comercial propio), crear los perfiles de negocio y el acuerdo entre socios comerciales de los perfiles de negocio. Como parte del acuerdo entre socios comerciales, se establecen las propiedades de cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje EDI del perfil de negocio del socio comercial y envía un mensaje EDI a él. En su extremo, los demás socios comerciales deben hacer lo mismo y, para intercambiar mensajes, las configuraciones deben ser compatibles.  
  
 Debe definir los siguientes conjuntos de propiedades para las comunicaciones de EDI.  
  
- Las propiedades de socio comercial que definen aspectos generales del socio comercial, tal como el nombre, los puertos de envío y el certificado de firma.  
  
- Las propiedades de perfil de negocio que definen las identidades de negocio.  
  
- Las propiedades de EDI, como parte del acuerdo entre socios comerciales, que define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesará un mensaje entrante de un socio comercial y cómo generará un mensaje saliente enlazado al socio comercial.  
  
- Las propiedades AS2, como parte del acuerdo entre socios comerciales, que define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] llevará a cabo las comunicaciones AS2, entrantes y salientes. Estas propiedades afectan a las comunicaciones de EDI sólo cuando se envían mensajes EDI a través de AS2.  
  
  > [!NOTE]
  >  El acuerdo AS2 y el acuerdo de mensajería EDI entre los mismos perfiles de negocio se especifican por separado. Los dos acuerdos juntos forman una asociación.  
  
  Las propiedades de acuerdo entre socios comerciales determinan el siguiente procesamiento específico:  
  
- Procesamiento y generación de sobre de EDI  
  
- Procesamiento y generación de confirmaciones  
  
- Validación de mensajes EDI entrantes y salientes  
  
- Creación de lotes  
  
- Informes de estado  
  
  Para las identidades de negocio, puede haber valores específicos, como **D-U-N-S (Dun & Bradstreet)**. Los nombres específicos tienen calificadores específicos, por ejemplo, "01" para Duns. Cuando el nombre de identidad de negocio no es específico, se usa "ZZ" para los mensajes codificados en X12 y "ZZZ" para los mensajes codificados en EDIFACT, lo que indica un nombre que diferentes entidades han definido de forma mutua. El valor y calificador identificarán el perfil de negocio. El nombre de la identidad de negocio se proporciona únicamente para fines informativos. El tiempo de ejecución de BizTalk no lo usará para el procesamiento.  
  
## <a name="determining-an-agreement-for-edi-processing"></a>Determinación de un acuerdo para el procesamiento de EDI  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje EDI, intenta determinar el acuerdo entre socios comerciales en el que se resuelve el mensaje. Intenta resolver el acuerdo entre socios comerciales al hacer coincidir el mensaje y el calificador del remitente, el identificador del remitente, el calificador del destinatario y el identificador del destinatario como parte del acuerdo. Para obtener más detalles sobre este proceso, consulte [resolución de acuerdos, detección de esquemas y autorización para los mensajes EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).  
  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera un mensaje EDI para enviar, intenta determinar el acuerdo que se asocia con el perfil de negocio al que se enviará el mensaje. Intenta resolver el acuerdo al hacer coincidir el mensaje y el acuerdo mediante cualquiera de los elementos siguientes:  
  
- Propiedad de contexto AgreementPartIdForSend  
  
- Propiedades de contexto AgreementNameForSend SenderPartyNameForSend y ReceiverPartyNameForSend  
  
- Los calificadores e identificadores del remitente y los calificadores e identificadores del receptor  
  
- Nombre de puerto de envío  
  
  Para obtener más detalles sobre este proceso, consulte [resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).  
  
## <a name="using-edi-global-properties"></a>Utilizar propiedades globales de EDI  
 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede determinar el acuerdo para un mensaje entrante o saliente, usará el acuerdo de reserva para procesar el intercambio entrante o generar el intercambio saliente. Los acuerdos de reserva se establecen con el botón secundario del **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración y haga clic en **X12 la configuración de reserva** (para mensajes codificados en X12) o **Configuración de reserva de EDIFACT** (mensajes codificados en EDIFACT). Para obtener más información sobre las propiedades globales, consulte [configuración globales o propiedades del acuerdo de reserva](../core/configuring-global-or-fallback-agreement-properties.md).  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará el acuerdo de reserva únicamente si no puede determinar el acuerdo para un intercambio. Si se ha determinado un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no usará un valor de propiedad del acuerdo de reserva para una propiedad que no se haya definido para el acuerdo entre dos socios comerciales.  
  
 Los acuerdos de reserva no se usarán si los valores de puerto requieren autenticación. Si la configuración de puerto para un puerto de recepción requiere autenticación (si **eliminar mensajes si hay errores de autenticación** o **conservar mensajes si hay errores de autenticación** está seleccionado en el **General**  página de la **propiedades de puerto de recepción** cuadro de diálogo), un contrato es necesario para cualquier intercambio recibido por el puerto de recepción. En este caso, no se usan los acuerdos de reserva. Si no se ha determinado ningún acuerdo para un intercambio, éste se tratará como si se hubiera producido un error en la autenticación y se suspenderá.  
  
## <a name="see-also"></a>Vea también  
 [Resolución de acuerdos, detección de esquemas y autorización para los mensajes EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)   
 [Resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)   
 [Configurar propiedades de EDI](../core/configuring-edi-properties.md)   
 [Configuración de las propiedades de acuerdos globales o de respaldo](../core/configuring-global-or-fallback-agreement-properties.md)   
 [Problemas conocidos de las entidades de EDI](../core/known-issues-with-edi-parties.md)