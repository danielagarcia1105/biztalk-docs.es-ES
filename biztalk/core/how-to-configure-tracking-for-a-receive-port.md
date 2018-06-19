---
title: Cómo configurar el seguimiento de un puerto de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring [HAT tracking], receive ports
- tracking, receive ports
- receive ports, tracking
- configuring, tracking
- receive ports, configuring
- tracking, configuring
- HAT, receive ports
- configuring, receive ports
- managing [receive ports], tracking
ms.assetid: dd569e84-cb1c-4191-912a-0c2eb2781a85
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e18748a5d9ff8088d09dfe28bf23c7b729b6afc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249108"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="c4849-102">Cómo configurar el seguimiento de un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="c4849-102">How to Configure Tracking for a Receive Port</span></span>
<span data-ttu-id="c4849-103">En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar el seguimiento de un puerto de recepción, tales como las opciones para ver los cuerpos de mensajes y las propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="c4849-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a receive port, such as options to view message bodies and promoted properties..</span></span> <span data-ttu-id="c4849-104">Esto le ayuda supervisar el estado de su implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e identificar los cuellos de botella.</span><span class="sxs-lookup"><span data-stu-id="c4849-104">This helps you monitor the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementation and identify any bottlenecks.</span></span> <span data-ttu-id="c4849-105">La configuración de seguimiento que configure se aplica a todas las instancias del puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="c4849-105">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
 <span data-ttu-id="c4849-106">Para obtener más información acerca de la instancia de servicio y eventos de mensaje seguimiento características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [lista de comprobación: mensaje y seguimiento de datos de instancia](../core/checklist-message-and-instance-data-tracking.md)</span><span class="sxs-lookup"><span data-stu-id="c4849-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Message and Instance Data Tracking](../core/checklist-message-and-instance-data-tracking.md)</span></span>  
  
 <span data-ttu-id="c4849-107">La configuración de seguimiento que configure se aplica a todas las instancias del puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="c4849-107">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c4849-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c4849-108">Prerequisites</span></span>  
 <span data-ttu-id="c4849-109">Para llevar a cabo el procedimiento de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="c4849-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="c4849-110">Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="c4849-110">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="c4849-111">Para configurar el seguimiento de un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="c4849-111">To configure tracking for a receive port</span></span>  
  
1.  <span data-ttu-id="c4849-112">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c4849-112">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c4849-113">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee configurar el seguimiento de un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="c4849-113">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a receive port.</span></span>  
  
3.  <span data-ttu-id="c4849-114">Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y haga clic en **seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="c4849-114">Click **Receive Ports**, right-click the receive port and click **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4849-115">Antes de habilitar el seguimiento de cuerpos de mensaje en un puerto de recepción, asegúrese de que desea hacer el seguimiento del puerto de recepción; puede sobrecargarse.</span><span class="sxs-lookup"><span data-stu-id="c4849-115">Before enabling the message body tracking on a receive port, ensure if you want to track the receive port at all; it could be an overhead.</span></span> <span data-ttu-id="c4849-116">Por ejemplo, la canalización de recepción RcvPipe se usa en varias ubicaciones de recepción de diferentes puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="c4849-116">For example, a receive pipeline RcvPipe is used at several receive locations in different receive ports.</span></span> <span data-ttu-id="c4849-117">Si habilita el cuerpo del mensaje de seguimiento opción en RcvPipe, se producirá al cuerpo del mensaje de seguimiento en todas las ubicaciones de recepción, que no puedan ser necesarios.</span><span class="sxs-lookup"><span data-stu-id="c4849-117">If you enable the message body tracking option on RcvPipe, it leads to message body tracking on all the receive locations, which you might not want to do.</span></span> <span data-ttu-id="c4849-118">Por lo tanto, establecer el mensaje de seguimiento de cuerpos en los puertos según sus requisitos de recepción.</span><span class="sxs-lookup"><span data-stu-id="c4849-118">Hence, set the message body tracking on receive ports as per your requirement.</span></span>  
  
4.  <span data-ttu-id="c4849-119">Configurar las opciones de seguimiento que desee, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c4849-119">Configure the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="c4849-120">Use</span><span class="sxs-lookup"><span data-stu-id="c4849-120">Use this</span></span>|<span data-ttu-id="c4849-121">Para</span><span class="sxs-lookup"><span data-stu-id="c4849-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c4849-122">**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud antes de procesamiento de puerto**</span><span class="sxs-lookup"><span data-stu-id="c4849-122">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="c4849-123">Active esta casilla de verificación para guardar el contenido del mensaje y realizar un seguimiento de éste antes de la recepción del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c4849-123">Select this check box to save and track message content before the message is received.</span></span>|  
    |<span data-ttu-id="c4849-124">**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud después del procesamiento de puerto**</span><span class="sxs-lookup"><span data-stu-id="c4849-124">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="c4849-125">Active esta casilla de verificación para guardar el contenido del mensaje y realizar un seguimiento de éste después de la recepción del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c4849-125">Select this check box to save and track message content after the message is received.</span></span>|  
    |||  
    |||  
    |<span data-ttu-id="c4849-126">**Seguimiento de propiedades de mensaje - mensaje de solicitud antes de procesamiento de puerto**</span><span class="sxs-lookup"><span data-stu-id="c4849-126">**Track Message Properties - Request message before port processing**</span></span>|<span data-ttu-id="c4849-127">Activar esta casilla para realizar un seguimiento de las propiedades promocionadas de un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="c4849-127">Select this check box to track the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="c4849-128">**Seguimiento de propiedades de mensaje - mensaje de solicitud después del procesamiento de puerto**</span><span class="sxs-lookup"><span data-stu-id="c4849-128">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="c4849-129">Activar esta casilla si se desea realizar un seguimiento de las propiedades promocionadas de un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="c4849-129">Select this check box if you want to track the promoted properties of an outbound message.</span></span>|  
    |||  
    |||  
  
## <a name="see-also"></a><span data-ttu-id="c4849-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4849-130">See Also</span></span>  
 [<span data-ttu-id="c4849-131">Administrar puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="c4849-131">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)