---
title: Configuración de mensajes de remitente (NRR) de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6ca2709-ac4b-48c0-82f8-8a43971a86cb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1785a5502bc1adb9cc8b9aa7f85b6a4473d21c5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233580"
---
# <a name="configuring-sender-message-tracking-nrr"></a>Configuración del seguimiento de mensajes de remitente (NRR)
Como parte de la configuración de esta página, se puede especificar si los mensajes de salida y sus confirmaciones (MDN) se almacenan en la base de datos sin repudio. Para obtener más información, consulte [procesamiento de AS2 en BizTalk Server](../core/as2-processing-in-biztalk-server.md).  
  
 Para almacenar mensajes en la base de datos sin repudio, las entidades deben habilitar NRR (recepción sin repudio) como parte de las propiedades del acuerdo AS2. NRR garantiza que la entidad remitente ha verificado el recibo firmado procedente del destinatario del mensaje. Conceptualmente, un NRR es una prueba irrefutable para el remitente del mensaje de que el mensaje ha llegado a su destino sin alteraciones. Se puede establecer NRR solo cuando el mensaje original y la confirmación están firmados digitalmente.  
  
> [!IMPORTANT]
>  Todas las propiedades se deshabilitan en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
>   
>  Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-message-tracking-for-outbound-as2-messages-and-inbound-mdn"></a>Para configurar el seguimiento de mensajes para mensajes AS2 salientes y MDN entrantes  
  
1.  Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md). Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **seguimiento de mensaje de remitente (NRR)**.  
  
    > [!NOTE]
    >  Para garantizar la recepción sin repudio, debe establecer la autenticación e integridad del mensaje. La forma recomendada de hacerlo es mediante una firma digital en el mensaje. Como resultado, si selecciona cualquiera de las propiedades para almacenar mensajes en la base de datos sin repudio, debería firmar el mensaje seleccionando la **debe firmarse el mensaje** propiedad en el **validación** página.  
  
3.  Seleccione **NRR habilitado para mensajes AS2 salientes codificados** para almacenar mensajes AS2 salientes codificados en la base de datos sin repudio.  
  
4.  Seleccione **NRR habilitado para mensajes AS2 salientes descodificados** para almacenar mensajes AS2 salientes descodificados en la base de datos sin repudio.  
  
5.  Seleccione **NRR habilitado para MDN de entrada** para almacenar MDN entrantes en la base de datos sin repudio.  
  
6.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración del Host Local (AS2)](../core/configuring-local-host-settings-as2.md)