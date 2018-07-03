---
title: Configuración de identificadores (X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 665698d1-c46c-4149-9715-381b4966dd92
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc9b4b5a6b2632c797ff655899b118536dbdde4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003085"
---
# <a name="configuring-identifiers-x12"></a>Configuración de identificadores (X12)
En el acuerdo de socio, debe establecer el X12 propiedades autorización y seguridad con el fin de comprobar que no se recibe el intercambio por no autorización a los destinatarios.  
  
> [!NOTE]
>  Las propiedades de procesamiento de intercambio que se describen aquí se aplican también a los intercambios HIPAA.  
> 
> [!IMPORTANT]
>  Las siguientes propiedades están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.  
> 
> - **DestinationPartyName** en **resoluciones de acuerdos adicionales** sección.  
> 
>   Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la lista anterior de propiedades están deshabilitadas en el **entidad A -> entidad B** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-set-sender-receiver-and-security-properties"></a>Para establecer las propiedades de remitente, destinatario y seguridad  
  
1. Crear un acuerdo de codificación, como se describe en X12 [configuración General de las opciones (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2. En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **identificadores**.  
  
3. Escriba valores para el **ISA1-2 (información y calificador de autorización)**. Seleccione el valor de la **calificador de autorización (ISA1)** de la lista desplegable asociada. Si este valor es distinto de **00**, para el **valor (ISA2)** texto, escriba un mínimo de un carácter alfanumérico y un máximo de 10. Se trata de un campo opcional. Si especifica estos valores, asegúrese de que coinciden con los campos ISA1 e ISA2 en un intercambio recibido; en caso contrario, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspenderá el intercambio.  
  
4. Escriba valores para el **ISA3-4 (información y calificador de seguridad)**. Seleccione el valor de la **calificador de seguridad (ISA3)** en la lista desplegable. Si este valor es distinto de **00**, para el **valor (ISA4)** texto, escriba un mínimo de caracteres alfanuméricos y un máximo de 10. Se trata de un campo opcional. Si estos valores no coinciden con los campos ISA3 e ISA4 en un intercambio recibido, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspenderá el intercambio.  
  
   > [!NOTE]
   >  El valor **03 – contraseña (para compatibilidad con versiones anteriores)**, se incluye por compatibilidad con versiones anteriores con [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y se quitará en futuras versiones.  
  
5. Especifique los valores de **ISA5-6 (identificador y calificador de remitente)**. Seleccione un valor para el calificador de la **calificador de Id. de remitente (ISA5)** lista desplegable. Para obtener el identificador, en el **valor (ISA6)** texto, escriba un mínimo de un carácter alfanumérico y un máximo de 15 caracteres.  
  
6. Especifique los valores de **ISA7-8 (calificador e identificador)**. Seleccione un valor para el calificador de la **calificador de Id. de remitente (ISA7)** lista desplegable. Para obtener el identificador, en el **valor (ISA8)** texto, escriba un mínimo de un carácter alfanumérico y un máximo de 15 caracteres.  
  
7. En el **resoluciones de acuerdos adicionales** sección, para **DestinationPartyName** propiedad, especifique un valor para la entidad de destino. Este valor también se usa para resolver los mensajes de salida a un acuerdo. Para obtener más información, vea [resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).  
  
   > [!NOTE]
   >  Normalmente no es necesario establecer la **DestinationPartyName** propiedad. Esta propiedad está disponible como parte de las propiedades de acuerdo para admitir escenarios de actualización. Al actualizar desde BizTalk Server 2006 R2 o BizTalk Server 2009, el **DestinationPartyName** propiedad está establecida en el nombre de la entidad en BizTalk Server 2006 R2 o BizTalk Server 2009.  
  
8. Haga clic en **aplicar** para aceptar los cambios o haga clic en **Aceptar** para introducir y validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
   > [!IMPORTANT]
   >  Si hace clic en **Aceptar** o **aplicar** en esta fase, se producirá un error. Eso es porque deberá proporcionar ISA5 a ISA8 valores en el **identificadores** pestaña de la ficha del acuerdo unidireccional.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las opciones de intercambio (X12)](../core/configuring-interchange-settings-x12.md)