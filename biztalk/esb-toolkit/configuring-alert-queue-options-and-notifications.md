---
title: Configurar las opciones de cola de alertas y notificaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914af88b989c73444e16acedf43b9a236897859d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-alert-queue-options-and-notifications"></a><span data-ttu-id="38d10-102">Configurar opciones de cola de alertas y notificaciones</span><span class="sxs-lookup"><span data-stu-id="38d10-102">Configuring Alert Queue Options and Notifications</span></span>
<span data-ttu-id="38d10-103">El Portal de administración de ESB usa el servicio de alerta de ESB para generar alertas cuando llegan los mensajes de error en el portal y usa el servicio de notificación de ESB para poner en cola y enviar notificaciones de alerta a los usuarios que se suscriben a alertas.</span><span class="sxs-lookup"><span data-stu-id="38d10-103">The ESB Management Portal uses the ESB Alert Service to generate alerts as fault messages arrive at the portal, and it uses the ESB Notification Service to queue and send alert notifications to users that subscribe to alerts.</span></span> <span data-ttu-id="38d10-104">Puede editar la configuración utilizada por estos servicios en el Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="38d10-104">You can edit the settings used by these services in the ESB Management Portal.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a><span data-ttu-id="38d10-105">Para configurar las opciones para el servicio de alertas de ESB</span><span class="sxs-lookup"><span data-stu-id="38d10-105">To configure the settings for the ESB Alert Service</span></span>  
  
1.  <span data-ttu-id="38d10-106">Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo de cuenta de administradores de Microsoft BizTalk Server (de los cuales los administradores del portal están automáticamente miembro).</span><span class="sxs-lookup"><span data-stu-id="38d10-106">Ensure that you log on to the portal using an account that is a member of the Microsoft BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="38d10-107">Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración de error** para abrir el portal [página de configuración de error](../esb-toolkit/fault-settings-page.md).</span><span class="sxs-lookup"><span data-stu-id="38d10-107">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="38d10-108">En el **opciones de alerta de cola** sección, active o desactive el **habilitar el servicio de cola de alertas** casilla de verificación para habilitar o deshabilitar el servicio.</span><span class="sxs-lookup"><span data-stu-id="38d10-108">In the **Alert Queue Options** section, select or clear the **Enable Alert Queue Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="38d10-109">Si habilita el servicio, edite los valores en el resto de los controles para satisfacer los requisitos.</span><span class="sxs-lookup"><span data-stu-id="38d10-109">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="38d10-110">El servicio interactúa con Microsoft Active Directory, por lo que debe especificar la cadena de conexión de LDAP (Protocolo ligero de acceso a directorios) adecuada.</span><span class="sxs-lookup"><span data-stu-id="38d10-110">The service interacts with Microsoft Active Directory, so you must specify the appropriate LDAP (Lightweight Directory Access Protocol) connection string.</span></span> <span data-ttu-id="38d10-111">También puede especificar el tamaño de lote de la cola y el intervalo de sondeo.</span><span class="sxs-lookup"><span data-stu-id="38d10-111">You can also specify the queue batch size and polling interval.</span></span>  
  
5.  <span data-ttu-id="38d10-112">Haga clic en **guardar** para guardar la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="38d10-112">Click **Save** to save the new settings.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a><span data-ttu-id="38d10-113">Para configurar las opciones para el servicio de notificación de correo electrónico de alerta de ESB</span><span class="sxs-lookup"><span data-stu-id="38d10-113">To configure the settings for the ESB Alert Email Notification service</span></span>  
  
1.  <span data-ttu-id="38d10-114">Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo de cuenta de administradores de BizTalk Server (de los cuales los administradores del portal están automáticamente miembro).</span><span class="sxs-lookup"><span data-stu-id="38d10-114">Ensure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="38d10-115">Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración de error** para abrir el portal [página de configuración de error](../esb-toolkit/fault-settings-page.md).</span><span class="sxs-lookup"><span data-stu-id="38d10-115">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="38d10-116">En el **opciones de alerta de correo electrónico** sección, active o desactive el **habilitar el servicio de correo electrónico de alerta** casilla de verificación para habilitar o deshabilitar el servicio.</span><span class="sxs-lookup"><span data-stu-id="38d10-116">In the **Alert Email Options** section, select or clear the **Enable Alert Email Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="38d10-117">Si habilita el servicio, edite los valores en el resto de los controles para satisfacer los requisitos.</span><span class="sxs-lookup"><span data-stu-id="38d10-117">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="38d10-118">Especifica el nombre del servidor de correo electrónico y la dirección "de", cambiar el tamaño de lote y de intervalo de sondeo según sea necesario y especifique la ruta de acceso a archivos de Extensible Stylesheet Language Transformations (XSLT) que utiliza el servicio.</span><span class="sxs-lookup"><span data-stu-id="38d10-118">Specify the e-mail server name and the "from" address, change the polling interval and batch size as required, and specify the path to Extensible Stylesheet Language Transformations (XSLT) files that the service uses.</span></span>  
  
5.  <span data-ttu-id="38d10-119">Haga clic en **guardar** para guardar la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="38d10-119">Click **Save** to save the new settings.</span></span>