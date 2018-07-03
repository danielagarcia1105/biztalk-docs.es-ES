---
title: Cómo configurar la programación de una ubicación de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, receive locations
- managing [receive locations], scheduling
- scheduling, receive locations
- managing [receive locations], configuring
ms.assetid: 2653e1c3-ddbd-4d3f-be64-2a5fcd7cf267
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724ac21972a49f64264217d4958b91539381f3a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002781"
---
# <a name="how-to-configure-scheduling-for-a-receive-location"></a>Cómo configurar la programación de una ubicación de recepción
En este tema, se describe cómo utilizar la consola de administración de BizTalk Server para configurar las propiedades de programación para una ubicación de recepción. Puede especificar las fechas cuando desee que la ubicación de recepción comience a procesar mensajes o bien cuando desee que la ubicación de recepción detenga ese procesamiento. También puede especificar determinadas horas del día durante las que desea que la ubicación de recepción procese mensajes.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-scheduling-for-a-receive-location"></a>Para configurar la programación de una ubicación de recepción  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee configurar la programación de una ubicación de recepción.  
  
3. Haga clic en **ubicaciones de recepción**, haga clic en la ubicación de recepción y haga clic en **propiedades**.  
  
4. En el panel izquierdo, haga clic en **programación**, configure las propiedades de programación como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
   |Use|Para|  
   |--------------|----------------|  
   |**Fecha de inicio**|Activar esta casilla de verificación y, en el calendario desplegable, seleccionar la fecha en la que la ubicación de recepción empieza a procesar mensajes. Para cambiar el año, haga clic en el año mostrado.|  
   |**Fecha de finalización**|Activar esta casilla de verificación y, en el calendario desplegable, seleccionar la fecha en la que la ubicación de recepción detenga el procesamiento de mensajes. Esta propiedad es opcional. Si no especifica una fecha de finalización, la ubicación de recepción sigue estando activa hasta que se deshabilita.|  
   |**Habilitar ventana de servicio**|Active esta casilla para configurar la ubicación de recepción para recibir mensajes solo a las horas del día especificadas y, después, especifique las horas en el **hora de inicio y hora de detención** cuadros. Si se desactiva la casilla, la ubicación de recepción recibe mensajes en cualquier momento. El valor predeterminado es false (desactivada).|  
   |**Hora de inicio**|Especificar la hora a la que la ubicación de recepción debe empezar a recibir mensajes. Este cuadro solo está disponible cuando el **habilitar ventana de servicio** casilla está activada.|  
   |**Hora de finalización**|Especificar la hora a la que la ubicación de recepción debe dejar de recibir mensajes. Este cuadro solo está disponible cuando el **habilitar ventana de servicio** casilla está activada.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de ubicaciones de recepción](../core/managing-receive-locations.md)