---
title: Cómo configurar opciones de copia de seguridad de transporte para un puerto de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- managing [send ports], configuring
- configuring, backing up [send ports]
- managing [send ports], backup options
- send ports, configuring
- send ports, backup options
ms.assetid: f05f57a6-e62b-4640-a6e2-cb73e9de2a14
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ff8b1354772290ce9e04742a6130a6f6f2df627
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248380"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a><span data-ttu-id="8a444-102">Cómo configurar opciones de transporte de reserva para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="8a444-102">How to Configure Backup Transport Options for a Send Port</span></span>
<span data-ttu-id="8a444-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para configurar las opciones de transporte de reserva para un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="8a444-103">This topic describes how to use the BizTalk Server Administration console to configure backup transport options for a send port.</span></span> <span data-ttu-id="8a444-104">El transporte de reserva especificado surte efecto en caso de error del transporte principal.</span><span class="sxs-lookup"><span data-stu-id="8a444-104">The backup transport that you specify takes effect in the event the primary transport fails to function.</span></span> <span data-ttu-id="8a444-105">Configuración del transporte primario se describe en [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).</span><span class="sxs-lookup"><span data-stu-id="8a444-105">Configuring the primary transport is described in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a444-106">En el caso de los puertos dinámicos, no hay propiedades disponibles para efectuar la configuración, puesto que las opciones de transporte se determinan de forma automática en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8a444-106">For dynamic ports, there are not properties available to configure because transport options are automatically determined at run time.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8a444-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8a444-107">Prerequisites</span></span>  
 <span data-ttu-id="8a444-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8a444-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="8a444-109">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="8a444-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-specify-transport-options-for-a-send-port"></a><span data-ttu-id="8a444-110">Para especificar opciones de transporte para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="8a444-110">To specify transport options for a send port</span></span>  
  
1.  <span data-ttu-id="8a444-111">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="8a444-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="8a444-112">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar las opciones de transporte de reserva para un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="8a444-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure backup transport options for a send port.</span></span>  
  
3.  <span data-ttu-id="8a444-113">Expanda **puertos de envío**, haga clic en el puerto de envío para configurar, haga clic en **propiedades**y, a continuación, haga clic en **copia de seguridad de transporte**.</span><span class="sxs-lookup"><span data-stu-id="8a444-113">Expand **Send Ports**, right-click the send port to configure, click **Properties**, and then click **Backup Transport**.</span></span>  
  
4.  <span data-ttu-id="8a444-114">Configurar las propiedades de transporte de reserva como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8a444-114">Configure backup transport properties as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="8a444-115">Use</span><span class="sxs-lookup"><span data-stu-id="8a444-115">Use this</span></span>|<span data-ttu-id="8a444-116">Para</span><span class="sxs-lookup"><span data-stu-id="8a444-116">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8a444-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8a444-117">**Type**</span></span>|<span data-ttu-id="8a444-118">En la lista desplegable, seleccionar el tipo de transporte de reserva, o protocolo de transporte, correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8a444-118">From the drop-down list, select the appropriate backup transport type, or transport protocol.</span></span> <span data-ttu-id="8a444-119">Si el puerto solo es de petición-respuesta, solo están disponibles en la lista los tipos de transporte que admiten petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="8a444-119">If the port is a solicit-response port, only transport types that support solicit-response are available in the list.</span></span>|  
    |<span data-ttu-id="8a444-120">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="8a444-120">**Configure**</span></span>|<span data-ttu-id="8a444-121">Después de seleccionar el tipo de transporte de copia de seguridad, haga clic en **configurar**y, a continuación, configurar propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="8a444-121">After you select the backup transport type, click **Configure**, and then configure transport properties.</span></span> <span data-ttu-id="8a444-122">Para obtener más información acerca de cómo configurar las propiedades, haga clic en **ayuda**.</span><span class="sxs-lookup"><span data-stu-id="8a444-122">For more information about configuring the properties, click **Help**.</span></span>|  
    |<span data-ttu-id="8a444-123">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="8a444-123">**Send handler**</span></span>|<span data-ttu-id="8a444-124">En la lista desplegable, seleccionar la instancia de host en la que se está ejecutando el adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="8a444-124">From the drop-down list, select the host instance on which the send adapter is running.</span></span>|  
    |<span data-ttu-id="8a444-125">**Número de reintentos**</span><span class="sxs-lookup"><span data-stu-id="8a444-125">**Retry count**</span></span>|<span data-ttu-id="8a444-126">Especificar el número de veces que el puerto de envío intenta reenviar un mensaje en caso de error.</span><span class="sxs-lookup"><span data-stu-id="8a444-126">Specify the number of times for the send port to resend a message on message failure.</span></span> <span data-ttu-id="8a444-127">El valor predeterminado es 3; el intervalo permitido es de 0 a 1.000, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="8a444-127">The default is 3; the allowed range is from 0 to 1,000.</span></span>|  
    |<span data-ttu-id="8a444-128">**Intervalo de reintento**</span><span class="sxs-lookup"><span data-stu-id="8a444-128">**Retry interval**</span></span>|<span data-ttu-id="8a444-129">Especificar el intervalo de tiempo (en minutos) que media entre los intentos de reenvío de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="8a444-129">Specify the interval in minutes between message resend attempts.</span></span> <span data-ttu-id="8a444-130">El valor predeterminado es 5; el intervalo permitido es de 0 a 525.600.</span><span class="sxs-lookup"><span data-stu-id="8a444-130">The default is 5; the allowed range is from 0 to 525,600.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a444-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a444-131">See Also</span></span>  
 [<span data-ttu-id="8a444-132">Crear y configurar puertos de envío</span><span class="sxs-lookup"><span data-stu-id="8a444-132">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)