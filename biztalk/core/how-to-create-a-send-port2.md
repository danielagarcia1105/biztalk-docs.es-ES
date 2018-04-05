---
title: Cómo crear un envío Port2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createsendport
helpviewer_keywords:
- managing [send ports], creating
- creating, send ports
- send ports, creating
ms.assetid: 7f0d07b8-1ac5-4032-bb08-2f7e05185f86
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 796ba5da53257d0f198e4b8bf13ee81835efcf4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-send-port"></a>Cómo crear un puerto de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para crear un puerto de envío. Al crear un puerto de envío, es preciso seleccionar el tipo de puerto de envío que se va a crear, tal y como se especifica a continuación:  
  
-   Unidireccional estático — un puerto sólo de envío.  
  
-   De petición-respuesta estático — un puerto de envío que espera una respuesta por parte del destino.  
  
-   Unidireccional dinámico — un puerto sólo de envío que puede enlazarse a un protocolo y a una ubicación en tiempo de ejecución en función de propiedades de mensaje.  
  
-   De petición-respuesta dinámico — un puerto de envío que espera una respuesta, y puede enlazarse a un protocolo y a una ubicación en tiempo de ejecución en función de propiedades de mensaje.  
  
 Después de crear un puerto de envío, puede llevar a cabo los siguientes pasos adicionales para completar la configuración:  
  
-   Configurar opciones avanzadas de transporte, como el número de reintentos de envío de mensajes de error de mensaje y la programación de la ventana de servicio para el puerto, como se describe en [opciones avanzadas de transporte configurar para un puerto de envío](../core/how-to-configure-transport-advanced-options-for-a-send-port.md).  
  
-   Configurar un transporte de reserva en caso de que el transporte principal no funcione correctamente, como se describe en [configurar opciones de transporte de copia de seguridad para un puerto de envío](../core/how-to-configure-backup-transport-options-for-a-send-port.md).  
  
-   Configurar filtros para determinar qué mensajes se enrutan a este puerto de envío desde el cuadro de mensaje, como se describe en [cómo configurar filtros para un puerto de envío](../core/how-to-configure-filters-for-a-send-port.md).  
  
-   Asignar un certificado de seguridad para el puerto de envío para cifrar o firmar documentos controlados por el puerto de envío, como se describe en [cómo asignar un certificado a un puerto de envío](../core/how-to-assign-a-certificate-to-a-send-port.md).  
  
-   Configurar opciones de seguimiento de mensajes controlados por el puerto de envío, como se describe en [cómo configurar seguimiento para un puerto de envío](../core/how-to-configure-tracking-for-a-send-port.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md). Además, tendrá que contar con permisos de administrador afiliado de SSO en la base de datos de inicio de sesión único (SSO) empresarial. Para obtener más información, consulte [grupos de usuarios de SSO](../core/sso-user-groups.md).  
  
### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **nuevo**y, a continuación, haga clic en el tipo de puerto que desea crear.  
  
4.  En el **propiedades de puertos de envío** ventana, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escribir el nombre del nuevo puerto de envío. Este nombre debe ser único en el grupo de BizTalk.|  
    |**Tipo de transporte**|En la lista desplegable, seleccionar el tipo de transporte, o protocolo de transporte, correspondiente. Si el puerto solo es de petición-respuesta, solo están disponibles en la lista los tipos de transporte que admiten petición-respuesta. Esta propiedad sólo resulta visible para puertos estáticos.|  
    |**Configurar**|Después de seleccionar el tipo de transporte, haga clic en **configurar** para mostrar la **propiedades de transporte** cuadro de diálogo que proporciona opciones de configuración específica del transporte. Esta propiedad sólo resulta visible para puertos estáticos. Haga clic en **ayuda** en el cuadro de diálogo para obtener instrucciones de configuración.|  
    |**Controlador de envío**|En la lista desplegable, seleccionar la instancia de host en la que se está ejecutando el adaptador de envío. Esta propiedad sólo resulta visible para puertos estáticos.|  
    |**Canalización de envío**|En la lista desplegable, seleccionar la canalización que procesa los mensajes enviados a través de este puerto. Después de seleccionar la canalización, haga clic en el botón de puntos suspensivos adyacente (**...** ) botón para mostrar el **configurar canalización** cuadro de diálogo donde configurar propiedades de canalización por instancia para este puerto específico. Haga clic en **ayuda** en el cuadro de diálogo para obtener instrucciones de configuración.|  
    |**La canalización de recepción**|En la lista desplegable, seleccionar la canalización que procesa los mensajes recibidos a través de este puerto. Las respuestas a los mensajes recibidos a través de esta canalización también se enviarán a través de esta canalización. Después de seleccionar la canalización, haga clic en el botón de puntos suspensivos adyacente (**...** ) botón para mostrar el **configurar canalización** cuadro de diálogo donde configurar propiedades de canalización por instancia para este puerto específico. Esta propiedad sólo está visible para puertos de petición-respuesta.|  
  
5.  Si va a crear un puerto de envío de petición-respuesta, en el panel izquierdo, haga clic en **asignaciones de entrada** y haga lo siguiente, efectuando las repeticiones según sea necesario si va a agregar varias asignaciones:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Documento de origen**|En la lista desplegable, seleccionar el documento origen para la asignación de entrada. Un puerto de envío puede tener más de una asignación pero cada asignación debe tener un documento origen único.|  
    |**Mapa**|En la lista desplegable, seleccionar la asignación para asociarla con los documentos de origen y de destino.|  
    |**Documento de destino**|En la lista desplegable, seleccionar el documento destino para la asignación de entrada.|  
  
6.  En el panel izquierdo, haga clic en **asignaciones de salida** y haga lo siguiente, efectuando las repeticiones según sea necesario si va a agregar varias asignaciones:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Documento de origen**|En la lista desplegable, seleccionar el documento origen para la asignación de salida.|  
    |**Mapa**|En la lista desplegable, seleccionar la asignación para asociarla con los documentos de origen y de destino.|  
    |**Documento de destino**|En la lista desplegable, seleccionar el documento destino para la asignación de salida.|  
  
7.  Cuando termine de configurar el puerto de envío, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)   
 [Administrar canalizaciones](../core/managing-pipelines.md)   
 [Administración de mapas](../core/managing-maps.md)