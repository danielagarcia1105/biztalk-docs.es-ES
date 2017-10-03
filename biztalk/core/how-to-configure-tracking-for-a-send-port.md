---
title: "Cómo configurar el seguimiento de un puerto de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- configuring, tracking
- tracking, send ports
- configuring [HAT tracking], send ports
- send ports, tracking
- managing [send ports], configuring
- tracking, configuring
- send ports, configuring
- managing [send ports], tracking
- HAT, send ports
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60ba83b7d3451599a0422ec370fed41eeba94407
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-send-port"></a>Cómo configurar el seguimiento de un puerto de envío
En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar el seguimiento de un puerto de envío, tales como las opciones para ver los cuerpos de mensajes y las propiedades promocionadas. Esto le ayuda supervisar el estado de su implementación de BizTalk e identificar cualquier cuello de botella. La configuración de seguimiento que haya definido se aplicará a todas las instancias del puerto de envío.  
  
 Para obtener más información acerca de la instancia de servicio y eventos de mensaje seguimiento características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-tracking-for-a-send-port"></a>Para configurar el seguimiento de un puerto de envío  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar el seguimiento de un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **seguimiento**.  
  
    > [!NOTE]
    >  Un puerto de envío solo se puede asociar a una canalización de envío. Si el seguimiento de cuerpos de mensaje está deshabilitado en la canalización de envío, tampoco se puede supervisar nada en el puerto de envío. En un escenario como este, puede deshabilitar las opciones de "Seguimiento" en ese puerto de envío.  
  
4.  Configurar las opciones de seguimiento que desee, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud antes de procesamiento de puerto**|Activar esta casilla para guardar y hacer un seguimiento del contenido del mensaje antes de recibirlo. **Nota:** debe habilitar el seguimiento de canalización partes de mensaje realizar el seguimiento correctamente el mensaje de respuesta antes de procesamiento de puerto.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud después del procesamiento de puerto**|Activar esta casilla para guardar y realizar un seguimiento del contenido del mensaje después de recibirlo.|  
    |||  
    |||  
    |**Seguimiento de propiedades de mensaje - mensaje de solicitud antes de procesamiento de puerto**|Activar esta casilla para realizar un seguimiento de las propiedades promocionadas de un mensaje entrante.|  
    |**Seguimiento de propiedades de mensaje - mensaje de solicitud después del procesamiento de puerto**|Activar esta casilla si se desea realizar un seguimiento de las propiedades promocionadas de un mensaje saliente.|  
    |||  
    |||  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)