---
title: "El proceso de aprobación y dar de alta de Auto | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfd3e72e-e28b-4ee3-bc4a-89ef3f64e6d5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333e1403ffd45f80a98d3eb17f5d3aa2b63c7798
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-auto-enlist-and-approval-process"></a>El proceso de aprobación y dar de alta de automática
Puede configurar el Portal de administración de ESB para publicar puntos de conexión de Microsoft BizTalk Server de dos maneras:  
  
-   Se puede configurar a través del proceso de aprobación, donde un administrador debe confirmar y aprobar la solicitud de registro.  
  
-   Se puede configurar mediante el uso de publicación automática, donde el portal publica automáticamente la solicitud en el registro de Universal Description, Discovery y Integration (UDDI) sin necesidad de intervención del administrador.  
  
 También puede especificar otras opciones de las características de integración de UDDI del portal, como se describe en los dos procedimientos siguientes.  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a>Para configurar la aprobación automática y la publicación en el Portal de administración de ESB  
  
1.  Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo Administradores de BizTalk Server.  
  
2.  Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración del registro** para abrir el portal [página de configuración del registro](../esb-toolkit/registry-settings-page.md).  
  
3.  Para habilitar la publicación y aprobación automática, escriba la dirección URL del servidor UDDI en el cuadro de texto en la parte superior de la **detalles de UDDI** sección de la página y, a continuación, seleccione la **publicación automática** casilla de verificación.  
  
4.  Para deshabilitar la publicación y aprobación automática, desactive la **publicar automática** casilla de verificación.  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a>Para configurar opciones de correo electrónico y el registro para las características de integración de UDDI  
  
1.  Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo de cuenta de administradores de BizTalk Server.  
  
2.  Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración del registro** para abrir el portal [página de configuración del registro](../esb-toolkit/registry-settings-page.md).  
  
3.  Edite la dirección URL del servidor UDDI en el cuadro de texto en la parte superior de la **detalles de UDDI** sección de la página. El servicio UDDI predeterminado es el servicio de Microsoft UDDI local.  
  
4.  Seleccione el **Anonymous** casilla de verificación si desea que el portal para usar la autenticación anónima para tener acceso el servidor UDDI.  
  
5.  Si desea que el portal para recibir notificaciones por correo electrónico cuando una publicación de UDDI solicitud está pendiente de aprobación, seleccione la **notificación habilitada** casilla de verificación en la **notificación por correo electrónico** sección de la página. A continuación, escriba los detalles del servidor de correo electrónico, la dirección para la entrega de mensajes de correo electrónico, un "de" dirección de correo electrónico adecuado, el asunto del mensaje y el cuerpo del mensaje.  
  
6.  Escriba el nombre de contacto del administrador y la dirección de correo electrónico para la recepción de UDDI solicitar mensajes de correo electrónico en el **la configuración predeterminada de** sección de la página.  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a>Para aprobar o rechazar una solicitud de registro como administrador  
  
1.  Asegúrese de que iniciar sesión en el portal con una cuenta que sea miembro del grupo Administradores de BizTalk Server.  
  
2.  Seleccione el **registro** pestaña en el menú principal portal y, a continuación, haga clic en **administrar solicitudes pendientes** para abrir el portal [administrar la página de solicitudes pendientes](../esb-toolkit/manage-pending-requests-page.md).  
  
3.  Para aprobar una solicitud pendiente, haga clic en el **aprobar** icono (la marca de verificación) situado junto a esa solicitud en la lista.  
  
4.  Para rechazar una solicitud pendiente, haga clic en el **rechazar** icono (la marca cruzada) situado junto a esa solicitud en la lista.  
  
5.  Para ver los detalles de una solicitud pendiente, haga clic en el **ver detalles** icono (la lupa) para abrir el [página de detalles de registro](../esb-toolkit/registry-details-page.md). Puede publicar, eliminar o actualizar la solicitud en esta página.  
  
6.  Para revisar el estado de las solicitudes y ver una lista de las solicitudes anteriores, haga clic en el **ver el historial de solicitudes** vínculo.