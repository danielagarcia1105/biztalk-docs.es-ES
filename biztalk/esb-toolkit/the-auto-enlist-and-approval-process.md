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
# <a name="the-auto-enlist-and-approval-process"></a><span data-ttu-id="d6baf-102">El proceso de aprobación y dar de alta de automática</span><span class="sxs-lookup"><span data-stu-id="d6baf-102">The Auto-Enlist and Approval Process</span></span>
<span data-ttu-id="d6baf-103">Puede configurar el Portal de administración de ESB para publicar puntos de conexión de Microsoft BizTalk Server de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="d6baf-103">You can configure the ESB Management Portal to publish Microsoft BizTalk Server endpoints in two ways:</span></span>  
  
-   <span data-ttu-id="d6baf-104">Se puede configurar a través del proceso de aprobación, donde un administrador debe confirmar y aprobar la solicitud de registro.</span><span class="sxs-lookup"><span data-stu-id="d6baf-104">It can be configured through the approval process, where an administrator must confirm and approve the registration request.</span></span>  
  
-   <span data-ttu-id="d6baf-105">Se puede configurar mediante el uso de publicación automática, donde el portal publica automáticamente la solicitud en el registro de Universal Description, Discovery y Integration (UDDI) sin necesidad de intervención del administrador.</span><span class="sxs-lookup"><span data-stu-id="d6baf-105">It can be configured by using auto-publish, where the portal automatically publishes the request into the Universal Description, Discovery, and Integration (UDDI) registry without requiring administrator intervention.</span></span>  
  
 <span data-ttu-id="d6baf-106">También puede especificar otras opciones de las características de integración de UDDI del portal, como se describe en los dos procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d6baf-106">You can also specify several other settings of the UDDI Integration features of the portal, as described in the following two procedures.</span></span>  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a><span data-ttu-id="d6baf-107">Para configurar la aprobación automática y la publicación en el Portal de administración de ESB</span><span class="sxs-lookup"><span data-stu-id="d6baf-107">To configure auto-approval and publishing in the ESB Management Portal</span></span>  
  
1.  <span data-ttu-id="d6baf-108">Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo Administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d6baf-108">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="d6baf-109">Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración del registro** para abrir el portal [página de configuración del registro](../esb-toolkit/registry-settings-page.md).</span><span class="sxs-lookup"><span data-stu-id="d6baf-109">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="d6baf-110">Para habilitar la publicación y aprobación automática, escriba la dirección URL del servidor UDDI en el cuadro de texto en la parte superior de la **detalles de UDDI** sección de la página y, a continuación, seleccione la **publicación automática** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="d6baf-110">To enable auto-approval and publishing, type the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page, and then select the **AutoPublish** check box.</span></span>  
  
4.  <span data-ttu-id="d6baf-111">Para deshabilitar la publicación y aprobación automática, desactive la **publicar automática** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="d6baf-111">To disable auto-approval and publishing, clear the **Auto Publish** check box.</span></span>  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a><span data-ttu-id="d6baf-112">Para configurar opciones de correo electrónico y el registro para las características de integración de UDDI</span><span class="sxs-lookup"><span data-stu-id="d6baf-112">To configure e-mail and registry settings for the UDDI Integration features</span></span>  
  
1.  <span data-ttu-id="d6baf-113">Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo de cuenta de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d6baf-113">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group.</span></span>  
  
2.  <span data-ttu-id="d6baf-114">Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración del registro** para abrir el portal [página de configuración del registro](../esb-toolkit/registry-settings-page.md).</span><span class="sxs-lookup"><span data-stu-id="d6baf-114">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="d6baf-115">Edite la dirección URL del servidor UDDI en el cuadro de texto en la parte superior de la **detalles de UDDI** sección de la página.</span><span class="sxs-lookup"><span data-stu-id="d6baf-115">Edit the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page.</span></span> <span data-ttu-id="d6baf-116">El servicio UDDI predeterminado es el servicio de Microsoft UDDI local.</span><span class="sxs-lookup"><span data-stu-id="d6baf-116">The default UDDI service is the local Microsoft UDDI service.</span></span>  
  
4.  <span data-ttu-id="d6baf-117">Seleccione el **Anonymous** casilla de verificación si desea que el portal para usar la autenticación anónima para tener acceso el servidor UDDI.</span><span class="sxs-lookup"><span data-stu-id="d6baf-117">Select the **Anonymous** check box if you want the portal to use anonymous authentication when accessing the UDDI server.</span></span>  
  
5.  <span data-ttu-id="d6baf-118">Si desea que el portal para recibir notificaciones por correo electrónico cuando una publicación de UDDI solicitud está pendiente de aprobación, seleccione la **notificación habilitada** casilla de verificación en la **notificación por correo electrónico** sección de la página.</span><span class="sxs-lookup"><span data-stu-id="d6baf-118">If you want the portal to notify you by e-mail when a UDDI publishing request is awaiting approval, select the **Notification Enabled** check box in the **Email Notification** section of the page.</span></span> <span data-ttu-id="d6baf-119">A continuación, escriba los detalles del servidor de correo electrónico, la dirección para la entrega de mensajes de correo electrónico, un "de" dirección de correo electrónico adecuado, el asunto del mensaje y el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d6baf-119">Then enter the details of your e-mail server, the address for delivery of e-mail messages, an appropriate "from" e-mail address, the message subject, and the message body.</span></span>  
  
6.  <span data-ttu-id="d6baf-120">Escriba el nombre de contacto del administrador y la dirección de correo electrónico para la recepción de UDDI solicitar mensajes de correo electrónico en el **la configuración predeterminada de** sección de la página.</span><span class="sxs-lookup"><span data-stu-id="d6baf-120">Enter the administrator contact name and e-mail address for the receipt of UDDI request e-mail messages in the **Default Settings** section of the page.</span></span>  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a><span data-ttu-id="d6baf-121">Para aprobar o rechazar una solicitud de registro como administrador</span><span class="sxs-lookup"><span data-stu-id="d6baf-121">To approve or decline a registration request as an administrator</span></span>  
  
1.  <span data-ttu-id="d6baf-122">Asegúrese de que iniciar sesión en el portal con una cuenta que sea miembro del grupo Administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d6baf-122">Make sure that you log into the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="d6baf-123">Seleccione el **registro** pestaña en el menú principal portal y, a continuación, haga clic en **administrar solicitudes pendientes** para abrir el portal [administrar la página de solicitudes pendientes](../esb-toolkit/manage-pending-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="d6baf-123">Point to the **Registry** tab on the portal main menu, and then click **Manage Pending Requests** to open the portal [Manage Pending Requests Page](../esb-toolkit/manage-pending-requests-page.md).</span></span>  
  
3.  <span data-ttu-id="d6baf-124">Para aprobar una solicitud pendiente, haga clic en el **aprobar** icono (la marca de verificación) situado junto a esa solicitud en la lista.</span><span class="sxs-lookup"><span data-stu-id="d6baf-124">To approve a pending request, click the **Approve** icon (the check mark) next to that request in the list.</span></span>  
  
4.  <span data-ttu-id="d6baf-125">Para rechazar una solicitud pendiente, haga clic en el **rechazar** icono (la marca cruzada) situado junto a esa solicitud en la lista.</span><span class="sxs-lookup"><span data-stu-id="d6baf-125">To reject a pending request, click the **Reject** icon (the cross mark) next to that request in the list.</span></span>  
  
5.  <span data-ttu-id="d6baf-126">Para ver los detalles de una solicitud pendiente, haga clic en el **ver detalles** icono (la lupa) para abrir el [página de detalles de registro](../esb-toolkit/registry-details-page.md).</span><span class="sxs-lookup"><span data-stu-id="d6baf-126">To view details of a pending request, click the **View Details** icon (the magnifying glass) to open the [Registry Details Page](../esb-toolkit/registry-details-page.md).</span></span> <span data-ttu-id="d6baf-127">Puede publicar, eliminar o actualizar la solicitud en esta página.</span><span class="sxs-lookup"><span data-stu-id="d6baf-127">You can publish, delete, or update the request in this page.</span></span>  
  
6.  <span data-ttu-id="d6baf-128">Para revisar el estado de las solicitudes y ver una lista de las solicitudes anteriores, haga clic en el **ver el historial de solicitudes** vínculo.</span><span class="sxs-lookup"><span data-stu-id="d6baf-128">To review the requests status and see a list of previous requests, click the **View Request History** link.</span></span>