---
title: Cómo crear una ubicación de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createreceivelocation
helpviewer_keywords:
- receive locations, creating
- managing [receive locations], creating
- creating, receive locations
ms.assetid: ec0202cf-0e69-4ae2-aba6-8cd2c3c77e82
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe82afdc62a7ba2c10087c78a6a24c1722e5812a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249692"
---
# <a name="how-to-create-a-receive-location"></a>Cómo crear una ubicación de recepción
En este tema se describe cómo usar la consola de administración de BizTalk Server para crear una nueva ubicación de recepción y especificar el puerto de recepción al que pertenece. Una ubicación de recepción es una dirección a la que llegan los mensajes de entrada, así como la canalización de mensajería que procesa los mensajes recibidos en dicha dirección.  
  
 Para poder crear una ubicación de recepción, en la aplicación debe existir un puerto de recepción que sea del mismo tipo que la ubicación de recepción que desea crear. Para obtener instrucciones sobre cómo crear un puerto de recepción, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
 Puede crear los siguientes tipos de ubicaciones de recepción:  
  
-   Unidireccionales: se utilizan para aplicaciones que entregan un mensaje sin esperar una respuesta de forma sincrónica.  
  
-   Solicitud-respuesta: se utilizan con aplicaciones que requieren una respuesta a un mensaje.  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede crear una ubicación de recepción durante el proceso de desarrollo mediante el procedimiento de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md). Además, deberá disponer de los permisos apropiados en la base de datos de SSO.  
  
### <a name="to-create-a-receive-location"></a>Para crear una ubicación de recepción  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea crear una ubicación de recepción.  
  
3.  Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional** o **solicitud de respuesta de ubicación de recepción**, de acuerdo con el tipo de ubicación de recepción para crear.  
  
4.  En la ventana Seleccionar una puerto de recepción, haga clic en el puerto de recepción que contendrá esta ubicación de recepción y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **propiedades de la ubicación de recepción** ventana, realice lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escribir el nombre de la ubicación de recepción.|  
    |**Tipo**|Seleccionar el tipo de transporte, o protocolo de transporte, en la lista desplegable. Si cambia el tipo de transporte, debe configurar las propiedades de transporte como se describe a continuación.|  
    |**Configurar**|Después de seleccionar el tipo de transporte, haga clic en **configurar** para mostrar la **propiedades de transporte** diálogo cuadro y configure las propiedades de adaptador para la ubicación de recepción. Para obtener instrucciones, haga clic en **ayuda** en el cuadro de diálogo. Para obtener más información acerca de cómo configurar cada tipo de adaptador, vea el tema correspondiente en [usando adaptadores](../core/using-adapters.md).|  
    |**Controlador de recepción**|En la lista desplegable, seleccionar la instancia del host de BizTalk Server en la que se ejecutará la ubicación de recepción. El controlador de recepción debe estar en ejecución en este host.|  
    |**La canalización de recepción**|Seleccionar la canalización de recepción para recibir mensajes en esta ubicación de recepción en la lista desplegable.|  
    |**Canalización de envío**|Seleccionar la canalización de envío para enviar respuesta en esta ubicación de recepción en la lista desplegable. Esta lista sólo está disponible para una ubicación de recepción asociada a un puerto de recepción de solicitud-respuesta.|  
    |**Establecer esta ubicación como principal**|Activar esta casilla si tiene más de una ubicación de recepción para un puerto de recepción y desea que esta ubicación represente el puerto de recepción cuando el puerto deba transferirse a otra entidad, como un socio comercial, que debe enviar mensajes a la organización. La primera ubicación de recepción creada se selecciona automáticamente como la ubicación de recepción primaria. Esta propiedad sigue estando seleccionada y no disponible hasta que designe una ubicación de recepción diferente como primaria.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ubicaciones de recepción](../core/managing-receive-locations.md)