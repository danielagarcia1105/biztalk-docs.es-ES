---
title: "Cómo configurar el seguimiento de un puerto de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- configuring, tracking
- tracking, send ports
- configuring [HAT tracking], send ports
- send ports, tracking
- managing [send ports], configuring
- tracking, configuring
- send ports, configuring
- managing [send ports], tracking
- HAT, send ports
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60ba83b7d3451599a0422ec370fed41eeba94407
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-send-port"></a><span data-ttu-id="4e112-102">Cómo configurar el seguimiento de un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="4e112-102">How to Configure Tracking for a Send Port</span></span>
<span data-ttu-id="4e112-103">En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar el seguimiento de un puerto de envío, tales como las opciones para ver los cuerpos de mensajes y las propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="4e112-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a send port, such as options to view message bodies and promoted properties.</span></span> <span data-ttu-id="4e112-104">Esto le ayuda supervisar el estado de su implementación de BizTalk e identificar cualquier cuello de botella.</span><span class="sxs-lookup"><span data-stu-id="4e112-104">This helps you monitor the health of your BizTalk implementation and identify any bottlenecks.</span></span> <span data-ttu-id="4e112-105">La configuración de seguimiento que haya definido se aplicará a todas las instancias del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="4e112-105">The tracking settings that you configure apply to all of the instances of the send port.</span></span>  
  
 <span data-ttu-id="4e112-106">Para obtener más información acerca de la instancia de servicio y eventos de mensaje seguimiento características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="4e112-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4e112-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4e112-107">Prerequisites</span></span>  
 <span data-ttu-id="4e112-108">Para llevar a cabo el procedimiento de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="4e112-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="4e112-109">Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="4e112-109">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-send-port"></a><span data-ttu-id="4e112-110">Para configurar el seguimiento de un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="4e112-110">To configure tracking for a send port</span></span>  
  
1.  <span data-ttu-id="4e112-111">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="4e112-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4e112-112">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar el seguimiento de un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="4e112-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a send port.</span></span>  
  
3.  <span data-ttu-id="4e112-113">Haga clic en **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="4e112-113">Click **Send Ports**, right-click the send port, click **Properties**, and then click **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4e112-114">Un puerto de envío solo se puede asociar a una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="4e112-114">One send port can be associated with only one send pipeline.</span></span> <span data-ttu-id="4e112-115">Si el seguimiento de cuerpos de mensaje está deshabilitado en la canalización de envío, tampoco se puede supervisar nada en el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="4e112-115">If message body tracking is disabled on the send pipeline, nothing can be tracked on the send port as well.</span></span> <span data-ttu-id="4e112-116">En un escenario como este, puede deshabilitar las opciones de "Seguimiento" en ese puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="4e112-116">In such a scenario, you can disable the "Tracking" options on that send port.</span></span>  
  
4.  <span data-ttu-id="4e112-117">Configurar las opciones de seguimiento que desee, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4e112-117">Configure the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="4e112-118">Use</span><span class="sxs-lookup"><span data-stu-id="4e112-118">Use this</span></span>|<span data-ttu-id="4e112-119">Para</span><span class="sxs-lookup"><span data-stu-id="4e112-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4e112-120">**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud antes de procesamiento de puerto**</span><span class="sxs-lookup"><span data-stu-id="4e112-120">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="4e112-121">Activar esta casilla para guardar y hacer un seguimiento del contenido del mensaje antes de recibirlo.</span><span class="sxs-lookup"><span data-stu-id="4e112-121">Select this check box to enable you to save and track message content before the message is received.</span></span> <span data-ttu-id="4e112-122">**Nota:** debe habilitar el seguimiento de canalización partes de mensaje realizar el seguimiento correctamente el mensaje de respuesta antes de procesamiento de puerto.</span><span class="sxs-lookup"><span data-stu-id="4e112-122">**Note:**  You must enable message body pipeline tracking to successfully track the response message before port processing.</span></span>|  
    |<span data-ttu-id="4e112-123">**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud después del procesamiento de puerto**</span><span class="sxs-lookup"><span data-stu-id="4e112-123">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="4e112-124">Activar esta casilla para guardar y realizar un seguimiento del contenido del mensaje después de recibirlo.</span><span class="sxs-lookup"><span data-stu-id="4e112-124">Select this check box to enable you to save and track message content after the message is received.</span></span>|  
    |||  
    |||  
    |<span data-ttu-id="4e112-125">**Seguimiento de propiedades de mensaje - mensaje de solicitud antes de procesamiento de puerto**</span><span class="sxs-lookup"><span data-stu-id="4e112-125">**Track Message Properties - Request message before port processing**</span></span>|<span data-ttu-id="4e112-126">Activar esta casilla para realizar un seguimiento de las propiedades promocionadas de un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="4e112-126">Select this check box to track the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="4e112-127">**Seguimiento de propiedades de mensaje - mensaje de solicitud después del procesamiento de puerto**</span><span class="sxs-lookup"><span data-stu-id="4e112-127">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="4e112-128">Activar esta casilla si se desea realizar un seguimiento de las propiedades promocionadas de un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="4e112-128">Select this check box if you want to track the promoted properties of an outbound message.</span></span>|  
    |||  
    |||  
  
## <a name="see-also"></a><span data-ttu-id="4e112-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e112-129">See Also</span></span>  
 [<span data-ttu-id="4e112-130">Crear y configurar puertos de envío</span><span class="sxs-lookup"><span data-stu-id="4e112-130">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)