---
title: "El Portal de administración de ESB y error mensaje Visor | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4a1636c-2e45-4ee5-92c2-81c976582da3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9a6e7272e7b707b6ba7650cfb93506c3a54a00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-management-portal-and-fault-message-viewer"></a><span data-ttu-id="054dc-102">El Portal de administración de ESB y el Visor de mensajes de error</span><span class="sxs-lookup"><span data-stu-id="054dc-102">The ESB Management Portal and Fault Message Viewer</span></span>
<span data-ttu-id="054dc-103">Un componente importante de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] está basado en Web portal que proporciona una amplia gama de excepción características de notificación de alerta y administración; además, actúa como la administración de configuración útil y Universal Description, Discovery and Integration ( Interfaz de registro UDDI).</span><span class="sxs-lookup"><span data-stu-id="054dc-103">A major component of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is a Web-based portal that provides a wide range of exception management and alert notification features; in addition, it acts as a useful configuration management and Universal Description, Discovery, and Integration (UDDI) registration interface.</span></span> <span data-ttu-id="054dc-104">La figura 1 muestra la página principal del portal, que proporciona información general sobre el estado de las aplicaciones que se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="054dc-104">Figure 1 shows the home page of the portal, which provides an overview of the health of the currently running applications.</span></span>  
  
 <span data-ttu-id="054dc-105">![Página principal del portal](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")</span><span class="sxs-lookup"><span data-stu-id="054dc-105">![Portal Home Page](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")</span></span>  
  
 <span data-ttu-id="054dc-106">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="054dc-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="054dc-107">**La página principal del Portal de administración de ESB**</span><span class="sxs-lookup"><span data-stu-id="054dc-107">**The home page of the ESB Management Portal**</span></span>  
  
 <span data-ttu-id="054dc-108">Los usuarios pueden seleccionar un mensaje de error aparece en el Portal de administración de ESB para ver las propiedades de ambiente y estáticas del error y una lista de los mensajes originales contenida en el mensaje de error, tal como se muestra en la figura 2.</span><span class="sxs-lookup"><span data-stu-id="054dc-108">Users can select a fault message displayed in the ESB Management Portal to view the ambient and static properties of the fault and a list of the original messages contained in the fault message, as shown in Figure 2.</span></span>  
  
 <span data-ttu-id="054dc-109">![Página de Visor de errores](../esb-toolkit/media/ch4-faultviewerpage.gif "Ch4-FaultViewerPage")</span><span class="sxs-lookup"><span data-stu-id="054dc-109">![Faul tViewer Page](../esb-toolkit/media/ch4-faultviewerpage.gif "Ch4-FaultViewerPage")</span></span>  
  
 <span data-ttu-id="054dc-110">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="054dc-110">**Figure 2**</span></span>  
  
 <span data-ttu-id="054dc-111">**La página del Visor de errores de ESB del Portal de administración de ESB**</span><span class="sxs-lookup"><span data-stu-id="054dc-111">**The ESB Fault Viewer page of the ESB Management Portal**</span></span>  
  
 <span data-ttu-id="054dc-112">Mensajes de error de ESB aparece en el Portal de administración de ESB pueden ser el resultado de un error en los valores del mensaje original cuando se envían para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="054dc-112">ESB Fault messages displayed in the ESB Management Portal may be the result of an error in the values of the original message when submitted for processing.</span></span> <span data-ttu-id="054dc-113">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la funcionalidad "reparar y volver a enviar", que permite a los administradores y usuarios para editar mensajes con errores y enviarlos a en rampa para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="054dc-113">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports "repair and resubmit" functionality, which allows administrators or users to edit failed messages and to submit them to an on-ramp for processing.</span></span>  
  
 <span data-ttu-id="054dc-114">Seleccionar entre el contenido mensajes, se abre la página de vista de mensajes en la vista de detalles del mensaje, tal como se muestra en la figura 3.</span><span class="sxs-lookup"><span data-stu-id="054dc-114">Selecting one of the contained messages opens the Message View page in Message Details view, as shown in Figure 3.</span></span> <span data-ttu-id="054dc-115">En esta vista, los usuarios pueden ver el mensaje de contenido, para descargar el mensaje o haga clic en **editar** para cambiar a vista de edición, donde pueden reparar y volver a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="054dc-115">In this view, users can see the message content, download the message, or click **Edit** to switch to Edit view, where they can repair and resubmit the message.</span></span>  
  
 <span data-ttu-id="054dc-116">![Página del Visor de mensajes](../esb-toolkit/media/ch4-messageviewerpage.gif "Ch4-MessageViewerPage")</span><span class="sxs-lookup"><span data-stu-id="054dc-116">![Message Viewer Page](../esb-toolkit/media/ch4-messageviewerpage.gif "Ch4-MessageViewerPage")</span></span>  
  
 <span data-ttu-id="054dc-117">**Figura 3**</span><span class="sxs-lookup"><span data-stu-id="054dc-117">**Figure 3**</span></span>  
  
 <span data-ttu-id="054dc-118">**El Visor de mensajes de ESB que muestra la vista de detalles del error**</span><span class="sxs-lookup"><span data-stu-id="054dc-118">**The ESB Message Viewer showing the Fault Details view**</span></span>  
  
 <span data-ttu-id="054dc-119">Para obtener una descripción completa y las opciones de uso del Portal de administración de ESB, incluidos el Visor de error, el proceso de reenvío de mensajes y las técnicas usadas para obtener una lista, ordenar y analizar los errores, vea [administración de BizTalk ESB Kit de herramientas](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md).</span><span class="sxs-lookup"><span data-stu-id="054dc-119">For a complete description and usage options of the ESB Management Portal, including the Fault Viewer, the message resubmission process, and the techniques used for listing, sorting, and analyzing faults, see [Administration with the BizTalk ESB Toolkit](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md).</span></span>