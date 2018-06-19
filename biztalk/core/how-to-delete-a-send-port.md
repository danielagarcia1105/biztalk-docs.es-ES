---
title: Cómo eliminar un puerto de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], deleting
- send ports, deleting
- deleting, send ports
ms.assetid: aff5980e-57bf-400c-82bd-3d02e143f227
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63355f742f12fbbaf57ccde7a1406dbb694ee073
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006173"
---
# <a name="how-to-delete-a-send-port"></a>Cómo eliminar un puerto de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para eliminar un puerto de envío de una aplicación de BizTalk. Al hacerlo, el puerto de envío también se eliminará de la base de datos de administración de BizTalk del grupo.  
  
> [!IMPORTANT]
>  Al eliminar un puerto de envío, todas las instancias de servicio en ejecución asociadas con ese puerto dejarán de obtener información de configuración relacionada con él (como su nombre). Aunque esta información se almacena en caché, si la instancia de servicio tiene que reenviar un mensaje, no será posible completar el proceso y el mensaje se suspenderá. Antes de eliminar un puerto de envío, debe comprobar que no hay ninguna ejecución servicio instancias, tal y como se describe en [cómo ver información de instancia para un puerto de envío](../core/how-to-view-instance-information-for-a-send-port.md).  
  
 Solo es posible eliminar un puerto de envío si se cumplen las condiciones siguientes:  
  
-   Ninguna orquestación se encuentra enlazada al puerto de envío. Si este es el caso, puede quitar el enlace siguiendo las instrucciones de [cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md).  
  
-   Se ha detenido y dado de baja el puerto de envío. Para obtener instrucciones acerca de detener y dar de baja un puerto de envío, consulte [cómo dar de baja un puerto de envío o grupo de puertos de envío](../core/how-to-unenlist-a-send-port-or-send-port-group.md) y [cómo detener un puerto de envío o un grupo de puertos de envío](../core/how-to-stop-a-send-port-or-send-port-group.md).  
  
-   Ninguna entidad hace referencia al puerto de envío. Para obtener instrucciones acerca de cómo quitar una referencia a un puerto de envío de una entidad, consulte [cómo ver o editar una entidad](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).  
  
-   El puerto de envío no está incluido en un grupo de puertos de envío. Para obtener instrucciones acerca de cómo quitar un puerto de envío de un grupo de puertos de envío, consulte [cómo quitar un puerto de envío de un grupo de puertos de envío](../core/how-to-remove-a-send-port-from-a-send-port-group.md).  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede eliminar un puerto de envío durante el proceso de desarrollo mediante el procedimiento de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-delete-a-send-port"></a>Para eliminar un puerto de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk, expanda aplicaciones y, a continuación, expanda la aplicación que contiene el puerto de envío que desea eliminar  
  
3.  Haga clic en **puertos de envío**, haga clic en el puerto de envío y, a continuación, haga clic en **eliminar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y configuración de puertos de envío](../core/creating-and-configuring-send-ports.md)