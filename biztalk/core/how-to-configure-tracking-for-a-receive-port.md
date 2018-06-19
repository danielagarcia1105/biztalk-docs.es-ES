---
title: Cómo configurar el seguimiento de un puerto de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring [HAT tracking], receive ports
- tracking, receive ports
- receive ports, tracking
- configuring, tracking
- receive ports, configuring
- tracking, configuring
- HAT, receive ports
- configuring, receive ports
- managing [receive ports], tracking
ms.assetid: dd569e84-cb1c-4191-912a-0c2eb2781a85
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e18748a5d9ff8088d09dfe28bf23c7b729b6afc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249108"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a>Cómo configurar el seguimiento de un puerto de recepción
En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar el seguimiento de un puerto de recepción, tales como las opciones para ver los cuerpos de mensajes y las propiedades promocionadas. Esto le ayuda supervisar el estado de su implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e identificar los cuellos de botella. La configuración de seguimiento que configure se aplica a todas las instancias del puerto de recepción.  
  
 Para obtener más información acerca de la instancia de servicio y eventos de mensaje seguimiento características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [lista de comprobación: mensaje y seguimiento de datos de instancia](../core/checklist-message-and-instance-data-tracking.md)  
  
 La configuración de seguimiento que configure se aplica a todas las instancias del puerto de recepción.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-tracking-for-a-receive-port"></a>Para configurar el seguimiento de un puerto de recepción  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee configurar el seguimiento de un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y haga clic en **seguimiento**.  
  
    > [!NOTE]
    >  Antes de habilitar el seguimiento de cuerpos de mensaje en un puerto de recepción, asegúrese de que desea hacer el seguimiento del puerto de recepción; puede sobrecargarse. Por ejemplo, la canalización de recepción RcvPipe se usa en varias ubicaciones de recepción de diferentes puertos de recepción. Si habilita el cuerpo del mensaje de seguimiento opción en RcvPipe, se producirá al cuerpo del mensaje de seguimiento en todas las ubicaciones de recepción, que no puedan ser necesarios. Por lo tanto, establecer el mensaje de seguimiento de cuerpos en los puertos según sus requisitos de recepción.  
  
4.  Configurar las opciones de seguimiento que desee, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud antes de procesamiento de puerto**|Active esta casilla de verificación para guardar el contenido del mensaje y realizar un seguimiento de éste antes de la recepción del mensaje.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud después del procesamiento de puerto**|Active esta casilla de verificación para guardar el contenido del mensaje y realizar un seguimiento de éste después de la recepción del mensaje.|  
    |||  
    |||  
    |**Seguimiento de propiedades de mensaje - mensaje de solicitud antes de procesamiento de puerto**|Activar esta casilla para realizar un seguimiento de las propiedades promocionadas de un mensaje entrante.|  
    |**Seguimiento de propiedades de mensaje - mensaje de solicitud después del procesamiento de puerto**|Activar esta casilla si se desea realizar un seguimiento de las propiedades promocionadas de un mensaje saliente.|  
    |||  
    |||  
  
## <a name="see-also"></a>Vea también  
 [Administrar puertos de recepción](../core/managing-receive-ports.md)