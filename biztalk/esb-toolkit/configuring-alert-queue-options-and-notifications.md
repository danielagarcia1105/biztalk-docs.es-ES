---
title: Configurar las opciones de cola de alertas y notificaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914af88b989c73444e16acedf43b9a236897859d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290156"
---
# <a name="configuring-alert-queue-options-and-notifications"></a>Configurar opciones de cola de alertas y notificaciones
El Portal de administración de ESB usa el servicio de alerta de ESB para generar alertas cuando llegan los mensajes de error en el portal y usa el servicio de notificación de ESB para poner en cola y enviar notificaciones de alerta a los usuarios que se suscriben a alertas. Puede editar la configuración utilizada por estos servicios en el Portal de administración de ESB.  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a>Para configurar las opciones para el servicio de alertas de ESB  
  
1.  Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo de cuenta de administradores de Microsoft BizTalk Server (de los cuales los administradores del portal están automáticamente miembro).  
  
2.  Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración de error** para abrir el portal [página de configuración de error](../esb-toolkit/fault-settings-page.md).  
  
3.  En el **opciones de alerta de cola** sección, active o desactive el **habilitar el servicio de cola de alertas** casilla de verificación para habilitar o deshabilitar el servicio.  
  
4.  Si habilita el servicio, edite los valores en el resto de los controles para satisfacer los requisitos. El servicio interactúa con Microsoft Active Directory, por lo que debe especificar la cadena de conexión de LDAP (Protocolo ligero de acceso a directorios) adecuada. También puede especificar el tamaño de lote de la cola y el intervalo de sondeo.  
  
5.  Haga clic en **guardar** para guardar la nueva configuración.  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a>Para configurar las opciones para el servicio de notificación de correo electrónico de alerta de ESB  
  
1.  Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo de cuenta de administradores de BizTalk Server (de los cuales los administradores del portal están automáticamente miembro).  
  
2.  Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración de error** para abrir el portal [página de configuración de error](../esb-toolkit/fault-settings-page.md).  
  
3.  En el **opciones de alerta de correo electrónico** sección, active o desactive el **habilitar el servicio de correo electrónico de alerta** casilla de verificación para habilitar o deshabilitar el servicio.  
  
4.  Si habilita el servicio, edite los valores en el resto de los controles para satisfacer los requisitos. Especifica el nombre del servidor de correo electrónico y la dirección "de", cambiar el tamaño de lote y de intervalo de sondeo según sea necesario y especifique la ruta de acceso a archivos de Extensible Stylesheet Language Transformations (XSLT) que utiliza el servicio.  
  
5.  Haga clic en **guardar** para guardar la nueva configuración.