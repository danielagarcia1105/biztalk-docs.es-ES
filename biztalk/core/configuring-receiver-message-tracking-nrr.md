---
title: "Configuración del receptor de mensajes seguimiento (NRR) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce30737a-341b-45be-81a0-a7336219185e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942a9c62e69f9f39bf445f0b3028a4e6707f48d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-receiver-message-tracking-nrr"></a>Configuración del seguimiento de mensajes de receptor (NRR)
Como parte de la configuración de esta página, puede especificar si los mensajes entrantes y sus confirmaciones (MDN) se almacenan en la base de datos sin repudio. Para obtener más información, consulte [procesamiento de AS2 en BizTalk Server](../core/as2-processing-in-biztalk-server.md).  
  
 Para almacenar mensajes en la base de datos sin repudio, las entidades deben habilitar NRR (recepción sin repudio) como parte de las propiedades del acuerdo AS2. NRR garantiza que la entidad remitente ha verificado el recibo firmado procedente del destinatario del mensaje. Conceptualmente, un NRR es una prueba irrefutable para el remitente del mensaje de que el mensaje ha llegado a su destino sin alteraciones. Se puede establecer NRR solo cuando el mensaje original y la confirmación están firmados digitalmente.  
  
> [!IMPORTANT]
>  Ninguna propiedad se deshabilita en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación para la entidad A. Sin embargo, se deshabilitan todas las propiedades en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-message-tracking-for-inbound-as2-messages-and-outbound-mdn"></a>Para configurar el seguimiento de mensajes de AS2 entrantes y MDN saliente  
  
1.  Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md). Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **seguimiento de mensaje de receptor (NRR)**.  
  
    > [!NOTE]
    >  Para garantizar la recepción sin repudio, debe establecer la autenticación e integridad del mensaje. La forma recomendada de hacerlo es mediante una firma digital en el mensaje. Como resultado, si selecciona cualquiera de las propiedades para almacenar mensajes en la base de datos sin repudio, debería firmar el mensaje seleccionando la **debe firmarse el mensaje** propiedad en el **validación** página.  
  
3.  Seleccione **NRR habilitado para mensajes AS2 codificados de entrada** para almacenar mensajes AS2 salientes codificados en la base de datos sin repudio.  
  
4.  Seleccione **NRR habilitado para mensajes AS2 entrantes descodificados** para almacenar mensajes AS2 salientes descodificados en la base de datos sin repudio.  
  
5.  Seleccione **NRR habilitado para MDN de salida** para almacenar MDN entrantes en la base de datos sin repudio.  
  
6.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración del Host Local (AS2)](../core/configuring-local-host-settings-as2.md)