---
title: Cómo crear un puerto de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createreceiveport
helpviewer_keywords:
- receive ports, creating
- managing [receive ports], creating
- creating, receive ports
ms.assetid: 23fae441-be80-4759-b3d6-74787a40e65b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdecbc36962d3e4e45d35171747ff4c450959a83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249748"
---
# <a name="how-to-create-a-receive-port"></a>Cómo crear un puerto de recepción
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para crear un puerto de recepción. Un puerto de recepción es una agrupación lógica de ubicaciones de recepción similares a través de los cuales los servicios interactúan con los socios comerciales externos mediante la recepción de datos.  
  
 Puede crear los siguientes tipos de puertos de recepción:  
  
-   Unidireccionales: se utilizan para aplicaciones que entregan un mensaje sin esperar una respuesta de forma sincrónica.  
  
-   Solicitud-respuesta: se utilizan con aplicaciones que requieren una respuesta a un mensaje.  
  
 Además de la configuración descrita en este tema, también puede especificar opciones de seguimiento de los mensajes administrados por un puerto de recepción, como se describe en [cómo configurar seguimiento para un puerto de recepción](../core/how-to-configure-tracking-for-a-receive-port.md).  
  
> [!NOTE]
>  Si va a crear un puerto de recepción en un equipo remoto y ese equipo no tiene acceso de red DTC habilitado, tendrá que reiniciar el equipo remoto después de crear el puerto de recepción.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-create-a-receive-port"></a>Para crear un puerto de recepción  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee crear un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, función para el tipo de puerto que desea crear.  
  
4.  En el **propiedades de puerto de recepción** ventana, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escribir el nombre del puerto.|  
    |**Sin autenticación**|Haga clic en esta opción para deshabilitar la autenticación. Ésta es la opción predeterminada.|  
    |**Eliminar mensajes si hay errores de autenticación**|Haga clic en esta opción para habilitar la autenticación y eliminar los mensajes no autenticados.|  
    |**Conservar mensajes si hay errores de autenticación**|Habilitar la autenticación y mantener los mensajes no autenticados.|  
    |**Habilitar enrutamiento para mensajes con errores**|Activar esta casilla para intentar enrutar cualquier mensaje que genere un error de procesamiento a una aplicación de suscripción (por ejemplo, otro puerto de recepción o programación de orquestación). Desactive la casilla para suspender los mensajes con error y generar una confirmación negativa (NACK). Esta opción está desactivada de forma predeterminada. Para obtener más información, consulte [cómo habilitar enrutamiento para mensajes de error para un puerto de recepción](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md).|  
  
5.  En el panel izquierdo, haga clic en **ubicaciones de recepción**y crear una nueva ubicación de recepción de este puerto de recepción. Para obtener instrucciones, consulte [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
6.  En el panel izquierdo, haga clic en **asignaciones de entrada**, y realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Documento de origen**|Seleccionar el esquema de origen para usar con este puerto en la lista desplegable.|  
    |**Mapa**|Seleccionar la asignación que desea asociar con este puerto en la lista desplegable.|  
    |**Documento de destino**|Seleccionar el esquema de destino para usar con este puerto en la lista desplegable.|  
  
7.  Si va a crear una respuesta de solicitud de puerto de recepción, a continuación, en el panel izquierdo, haga clic en **asignaciones de salida**, y realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Documento de origen**|Seleccionar el esquema de origen para usar con este puerto en la lista desplegable.|  
    |**Mapa**|Seleccionar la asignación que desea asociar con este puerto en la lista desplegable.|  
    |**Documento de destino**|Seleccionar el esquema de destino para usar con este puerto en la lista desplegable.|  
  
8.  Cuando termine de configurar el puerto de recepción, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar puertos de recepción](../core/managing-receive-ports.md)