---
title: Reparar y volver a enviar un mensaje | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccd720b4-44a2-4c44-bf6e-8cf5e9ded1aa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e524ffca1b79032dce55f74e195032d14ec1bf9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="repairing-and-resubmitting-a-message"></a><span data-ttu-id="5c24a-102">Reparar y volver a enviar un mensaje</span><span class="sxs-lookup"><span data-stu-id="5c24a-102">Repairing and Resubmitting a Message</span></span>
<span data-ttu-id="5c24a-103">Para reparar y volver a enviar un mensaje de error, use la página de errores del Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="5c24a-103">To repair and resubmit a failed message, use the Faults page of the ESB Management Portal.</span></span>  
  
### <a name="to-repair-and-resubmit-a-message-for-processing"></a><span data-ttu-id="5c24a-104">Reparar y volver a enviar un mensaje para el procesamiento</span><span class="sxs-lookup"><span data-stu-id="5c24a-104">To repair and resubmit a message for processing</span></span>  
  
1.  <span data-ttu-id="5c24a-105">Busque el mensaje de error deseada en el [Portal errores de página](../esb-toolkit/portal-faults-page.md) página del Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="5c24a-105">Locate the desired fault message on the [Portal Faults Page](../esb-toolkit/portal-faults-page.md) page of the ESB Management Portal.</span></span> <span data-ttu-id="5c24a-106">Use las capacidades de filtrado en la página de errores para buscar un mensaje específico.</span><span class="sxs-lookup"><span data-stu-id="5c24a-106">Use the filtering capabilities on the Faults page to search for a specific message.</span></span> <span data-ttu-id="5c24a-107">Deje cualquiera de los controles en blanco para recuperar todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5c24a-107">Leave any of the controls empty to retrieve all messages.</span></span> <span data-ttu-id="5c24a-108">Tenga en cuenta que el filtrado en una base de datos de errores muy grandes puede tardar varios segundos para mostrar los resultados adecuados.</span><span class="sxs-lookup"><span data-stu-id="5c24a-108">Note that filtering on a very large fault database may take several seconds to display the appropriate results.</span></span> <span data-ttu-id="5c24a-109">La figura 1 muestra la página de errores.</span><span class="sxs-lookup"><span data-stu-id="5c24a-109">Figure 1 illustrates the Faults page.</span></span>  
  
     <span data-ttu-id="5c24a-110">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span><span class="sxs-lookup"><span data-stu-id="5c24a-110">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span></span>  
  
     <span data-ttu-id="5c24a-111">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="5c24a-111">**Figure 1**</span></span>  
  
     <span data-ttu-id="5c24a-112">**La página de errores del Portal de administración de ESB**</span><span class="sxs-lookup"><span data-stu-id="5c24a-112">**The Faults page of the ESB Management Portal**</span></span>  
  
2.  <span data-ttu-id="5c24a-113">Haga clic en cualquier parte en la fila del mensaje de error deseada para abrir la [Visor de mensajes de error de Portal](../esb-toolkit/portal-fault-message-viewer.md) página [vista de detalles de error](../esb-toolkit/fault-details-view.md).</span><span class="sxs-lookup"><span data-stu-id="5c24a-113">Click anywhere in the row of the desired fault message to open the [Portal Fault Message Viewer](../esb-toolkit/portal-fault-message-viewer.md) page in [Fault Details View](../esb-toolkit/fault-details-view.md).</span></span>  
  
3.  <span data-ttu-id="5c24a-114">Desplácese hasta la parte inferior de la vista de detalles del error a la lista de mensajes contenidos en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="5c24a-114">Scroll to the bottom of the Fault Details view to the list of messages contained within the fault message.</span></span> <span data-ttu-id="5c24a-115">La figura 2 muestra la **mensajes** sección de la página del Visor de error.</span><span class="sxs-lookup"><span data-stu-id="5c24a-115">Figure 2 illustrates the **Messages** section of the Fault Viewer page.</span></span>  
  
     <span data-ttu-id="5c24a-116">![Mensajes de sección](../esb-toolkit/media/ch8-messagessection.gif "Ch8-MessagesSection")</span><span class="sxs-lookup"><span data-stu-id="5c24a-116">![Messages Section](../esb-toolkit/media/ch8-messagessection.gif "Ch8-MessagesSection")</span></span>  
  
     <span data-ttu-id="5c24a-117">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="5c24a-117">**Figure 2**</span></span>  
  
     <span data-ttu-id="5c24a-118">**La sección de mensajes de la página de error Visor del Portal de administración de ESB**</span><span class="sxs-lookup"><span data-stu-id="5c24a-118">**The Messages section of the Fault Viewer page of the ESB Management Portal**</span></span>  
  
4.  <span data-ttu-id="5c24a-119">Haga clic en el identificador del mensaje del mensaje que desea reenviar.</span><span class="sxs-lookup"><span data-stu-id="5c24a-119">Click the message identifier of the message you want to resubmit.</span></span> <span data-ttu-id="5c24a-120">Se abrirá el mensaje en [vista Detalles de mensajes](../esb-toolkit/message-details-view.md), que muestra los detalles del mensaje individual y el contenido del mensaje, como se muestra en la figura 3.</span><span class="sxs-lookup"><span data-stu-id="5c24a-120">This opens the message in [Message Details View](../esb-toolkit/message-details-view.md), which shows details of the individual message and the message content, as illustrated in Figure 3.</span></span>  
  
     <span data-ttu-id="5c24a-121">![Visor de mensajes](../esb-toolkit/media/ch8-messageviewer.gif "Ch8-MessageViewer")</span><span class="sxs-lookup"><span data-stu-id="5c24a-121">![Message Viewer](../esb-toolkit/media/ch8-messageviewer.gif "Ch8-MessageViewer")</span></span>  
  
     <span data-ttu-id="5c24a-122">**Figura 3**</span><span class="sxs-lookup"><span data-stu-id="5c24a-122">**Figure 3**</span></span>  
  
     <span data-ttu-id="5c24a-123">**La página del Visor de mensajes del Portal de administración de ESB**</span><span class="sxs-lookup"><span data-stu-id="5c24a-123">**The Message Viewer page of the ESB Management Portal**</span></span>  
  
5.  <span data-ttu-id="5c24a-124">Haga clic en el **editar** vínculo que figura en el cuadro de texto que contiene el contenido del mensaje para cambiar a modo de edición y, a continuación, edite el contenido del mensaje según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5c24a-124">Click the **Edit** link under the text box that contains the message content to switch to edit mode, and then edit the message contents as required.</span></span> <span data-ttu-id="5c24a-125">Por ejemplo, necesite cambiar los parámetros para las invocaciones de método de servicio dentro del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5c24a-125">For example, you may need to change the parameters for service method invocations contained within the message.</span></span> <span data-ttu-id="5c24a-126">Tenga en cuenta que debe cumplir el estilo de documento nativo (por ejemplo, formato de archivo sin formato o XML) para evitar el rechazo del mensaje cuando se vuelven a enviar.</span><span class="sxs-lookup"><span data-stu-id="5c24a-126">Note that you must adhere to the native document style (such as XML or flat file format) to prevent rejection of the message when resubmitted.</span></span> <span data-ttu-id="5c24a-127">Figura 4 se ilustran la **detalles del mensaje** sección de la página Editor de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5c24a-127">Figure 4 illustrates the **Message Details** section of the Message Editor page.</span></span>  
  
     <span data-ttu-id="5c24a-128">![Detalles del mensaje](../esb-toolkit/media/ch8-messagedetails.gif "Ch8-MessageDetails")</span><span class="sxs-lookup"><span data-stu-id="5c24a-128">![Message Details](../esb-toolkit/media/ch8-messagedetails.gif "Ch8-MessageDetails")</span></span>  
  
     <span data-ttu-id="5c24a-129">**Figura 4**</span><span class="sxs-lookup"><span data-stu-id="5c24a-129">**Figure 4**</span></span>  
  
     <span data-ttu-id="5c24a-130">**La sección de detalles del mensaje de la página del Visor de mensajes del Portal de administración de ESB**</span><span class="sxs-lookup"><span data-stu-id="5c24a-130">**The Message Details section of the Message Viewer page of the ESB Management Portal**</span></span>  
  
6.  <span data-ttu-id="5c24a-131">Después de editar el mensaje, seleccione una ubicación de reenvío en la lista desplegable en el cuadro de texto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5c24a-131">After editing the message, select a resubmission location in the drop-down list under the message text box.</span></span> <span data-ttu-id="5c24a-132">Esta lista muestra la lista dinámicamente recuperada de los extremos disponibles.</span><span class="sxs-lookup"><span data-stu-id="5c24a-132">This list shows the dynamically retrieved list of available endpoints.</span></span> <span data-ttu-id="5c24a-133">Debe seleccionar un extremo configurado como un punto de conexión de reenvío.</span><span class="sxs-lookup"><span data-stu-id="5c24a-133">You must select an endpoint configured as a resubmission endpoint.</span></span> <span data-ttu-id="5c24a-134">Los siguientes extremos son adecuados para reenvío:</span><span class="sxs-lookup"><span data-stu-id="5c24a-134">The following endpoints are suitable for resubmission:</span></span>  
  
    -   <span data-ttu-id="5c24a-135">**WCF en rampa**.</span><span class="sxs-lookup"><span data-stu-id="5c24a-135">**WCF On-Ramp**.</span></span> <span data-ttu-id="5c24a-136">Este extremo es la servicios WCF de ESB itinerario en rampa y solo está disponible para archivos XML.</span><span class="sxs-lookup"><span data-stu-id="5c24a-136">This endpoint is the ESB Itinerary Services WCF on-ramp and is available only for XML files.</span></span> <span data-ttu-id="5c24a-137">El archivo Web.config portal define la dirección URL para este aumento.</span><span class="sxs-lookup"><span data-stu-id="5c24a-137">The portal Web.config file defines the URL for this on-ramp.</span></span>  
  
    -   <span data-ttu-id="5c24a-138">**SOAP en rampa**.</span><span class="sxs-lookup"><span data-stu-id="5c24a-138">**SOAP On-Ramp**.</span></span> <span data-ttu-id="5c24a-139">Este extremo es la servicios ASMX de ESB itinerario en rampa y solo está disponible para archivos XML.</span><span class="sxs-lookup"><span data-stu-id="5c24a-139">This endpoint is the ESB Itinerary Services ASMX on-ramp and is available only for XML files.</span></span> <span data-ttu-id="5c24a-140">El archivo Web.config portal define la dirección URL para este aumento.</span><span class="sxs-lookup"><span data-stu-id="5c24a-140">The portal Web.config file defines the URL for this on-ramp.</span></span>  
  
    -   <span data-ttu-id="5c24a-141">**Cualquier ubicación de recepción mediante el adaptador de HTTP de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="5c24a-141">**Any receive location using the BizTalk HTTP adapter**.</span></span> <span data-ttu-id="5c24a-142">Esta opción está disponible para los archivos XML y archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="5c24a-142">This option is available for XML files and flat files.</span></span>  
  
7.  <span data-ttu-id="5c24a-143">Haga clic en el **reenviar** vínculo para volver a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5c24a-143">Click the **Resubmit** link to resubmit the message.</span></span> <span data-ttu-id="5c24a-144">Un mensaje que indica la **estado de reenvío** aparece en el cuadro de texto del contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5c24a-144">A message indicating the **Resubmission Status** appears under the message content text box.</span></span>  
  
8.  <span data-ttu-id="5c24a-145">Si es necesario, abra el [página de registro de auditoría](../esb-toolkit/audit-log-page.md) desde el **administrador** para confirmar el reenvío de mensajes, como se muestra en la figura 5.</span><span class="sxs-lookup"><span data-stu-id="5c24a-145">If required, open the [Audit Log Page](../esb-toolkit/audit-log-page.md) from the **Admin** tab to confirm message resubmission, as illustrated in Figure 5.</span></span>  
  
     <span data-ttu-id="5c24a-146">![Vista de página auditlog de tamaño reducido](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8-AuditLogPageSmallView")</span><span class="sxs-lookup"><span data-stu-id="5c24a-146">![AuditLog Page Small View](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8-AuditLogPageSmallView")</span></span>  
  
     <span data-ttu-id="5c24a-147">**Figura 5**</span><span class="sxs-lookup"><span data-stu-id="5c24a-147">**Figure 5**</span></span>  
  
     <span data-ttu-id="5c24a-148">**La página de registro de auditoría del Portal de administración de ESB**</span><span class="sxs-lookup"><span data-stu-id="5c24a-148">**The Audit Log page of the ESB Management Portal**</span></span>