---
title: Configuración de confirmaciones (MDN) (AS2) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb2bf98a-deb4-460f-a1fc-3d2397c39470
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2df8c92d37d5f6bc8fbf8d6d77fb698e6178036
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234108"
---
# <a name="configuring-acknowledgements-mdns-as2"></a>Configuración de confirmaciones (MDN) (AS2)
En el acuerdo de socios comerciales, puede especificar cómo la entidad que recibe el mensaje AS2 genera una respuesta MDN y la devuelve.  
  
> [!IMPORTANT]
>  Las propiedades siguientes están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
>   
>  -   **Reenviar mensaje de AS2 si no se recibe MDN** casilla de verificación y propiedades asociadas  
> -   **Invalidar la configuración del puerto de envío** casilla de verificación y propiedades asociadas  
>   
>  Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-acknowledgements"></a>Para configurar confirmaciones  
  
1.  Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md). Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, haga clic en **confirmaciones (MDN)**.  
  
3.  Seleccione el **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** casilla de verificación para enrutar el MDN a través del descodificador A2 como un mensaje de paso y, a continuación, en el cuadro de mensajes. Cuando esta propiedad se selecciona, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] promueve la propiedad `IsAS2MdnResponseMessage` para fines de enrutamiento.  
  
4.  Si ha activado el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad en el **validaciones** página, seleccione la **solicitar MDN** casilla de verificación si el socio comercial debe generar un MDN en respuesta al mensaje AS2.  
  
     Si el **solicitar MDN** casilla de verificación está seleccionada, también puede establecer las siguientes propiedades:  
  
    1.  Seleccione el **solicitar MDN firmado** casilla de verificación y desde el **algoritmo de firma** lista desplegable seleccione el algoritmo MIC que el socio comercial debe utilizar para firmar el MDN. [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]admite MD5, SHA1 y SHA2 (SHA256 (valor predeterminado), SHA384 y SHA512).
    
        > [!NOTE] 
        > **A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] y versiones más recientes**, soporte técnico SHA2 se incluye automáticamente. Para anterior [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versiones, vea [3123748 KB](https://support.microsoft.com/kb/3123748).
  
    2.  Seleccione el **solicitar MDN asíncrono** casilla de verificación y, a continuación, en la **Receipt-Delivery-Option (URL)** texto cuadro, escriba la dirección URL que la entidad receptora debe enviar el MDN.  
  
         Si el **solicitar MDN asíncrono** casilla de verificación está seleccionada, también puede establecer las siguientes propiedades:  
  
        1.  Seleccione el **reenviar mensaje AS2 si no se recibe MDN** casilla de verificación para habilitar la retransmisión del mensaje AS2. Escriba un valor para **intervalo de reenvío de mensajes de AS2 mínimo**, **intentos de reenvío del mensaje de número de AS2** y **detener intento de reenvíos de mensajes después de AS2** campos para especificar el intervalo de reintento, número máximo de intentos y cuándo se debe detener el reenvío del mensaje.  
  
            > [!NOTE]
            >  Debe seleccionar la **activar informes** casilla de verificación en la **propiedades generales** página de la **General** ficha antes de seleccionar **AS2 de reenvío de mensajes si MDN no recibido**.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]usa la información de seguimiento almacenada para los informes de AS2 con el fin de determinar cuándo se deben reenviar un mensaje AS2.  
  
        2.  Si **reenviar mensaje AS2 si no se recibe MDN** se selecciona la casilla de verificación, compruebe **invalidar la configuración del puerto de envío** para especificar el **intervalo de reintento HTTP mínimo** y  **Número de reintentos HTTP**. Escriba un valor para el **detener intento de HTTP se reintenta después** campo para especificar la cantidad máxima de tiempo que se efectuarán reintentos mediante el adaptador de HTTP.  
  
    3.  Si ha seleccionado la **solicitar MDN asíncrono** casilla de verificación y especifica una dirección URL para **Receipt-Delivery-Option (URL)** propiedad, el **Disposition-Notification-To** texto cuadro, se establece de manera predeterminada en la misma dirección URL. Si no ha seleccionado la **solicitar MDN asíncrono** casilla de verificación, debe especificar un valor para **Disposition-Notification-To**. El valor de este campo no se utiliza durante el procesamiento de AS2.  
  
5.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades del acuerdo de AS2](../core/configuring-as2-agreement-properties.md)