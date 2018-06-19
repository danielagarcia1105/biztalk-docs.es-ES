---
title: Cómo eliminar un puerto de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], deleting
- send ports, deleting
- deleting, send ports
ms.assetid: aff5980e-57bf-400c-82bd-3d02e143f227
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63355f742f12fbbaf57ccde7a1406dbb694ee073
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006173"
---
# <a name="how-to-delete-a-send-port"></a><span data-ttu-id="ba27b-102">Cómo eliminar un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="ba27b-102">How to Delete a Send Port</span></span>
<span data-ttu-id="ba27b-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para eliminar un puerto de envío de una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ba27b-103">This topic describes how to use the BizTalk Server Administration console to delete a send port from a BizTalk application.</span></span> <span data-ttu-id="ba27b-104">Al hacerlo, el puerto de envío también se eliminará de la base de datos de administración de BizTalk del grupo.</span><span class="sxs-lookup"><span data-stu-id="ba27b-104">When you do this, the send port is also deleted from the BizTalk Management database for the group.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba27b-105">Al eliminar un puerto de envío, todas las instancias de servicio en ejecución asociadas con ese puerto dejarán de obtener información de configuración relacionada con él (como su nombre).</span><span class="sxs-lookup"><span data-stu-id="ba27b-105">When you delete a send port, any running service instances associated with that port can no longer obtain configuration information about the send port, such as its name.</span></span> <span data-ttu-id="ba27b-106">Aunque esta información se almacena en caché, si la instancia de servicio tiene que reenviar un mensaje, no será posible completar el proceso y el mensaje se suspenderá.</span><span class="sxs-lookup"><span data-stu-id="ba27b-106">Although this information is cached, if the service instance must resend a message, it will not be able to complete, and the message will be suspended.</span></span> <span data-ttu-id="ba27b-107">Antes de eliminar un puerto de envío, debe comprobar que no hay ninguna ejecución servicio instancias, tal y como se describe en [cómo ver información de instancia para un puerto de envío](../core/how-to-view-instance-information-for-a-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="ba27b-107">Before deleting a send port, you should verify that there are no running service instances, as described in [How to View Instance Information for a Send Port](../core/how-to-view-instance-information-for-a-send-port.md).</span></span>  
  
 <span data-ttu-id="ba27b-108">Solo es posible eliminar un puerto de envío si se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba27b-108">You can delete a send port only if it meets the following conditions:</span></span>  
  
-   <span data-ttu-id="ba27b-109">Ninguna orquestación se encuentra enlazada al puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ba27b-109">An orchestration is not bound to the send port.</span></span> <span data-ttu-id="ba27b-110">Si este es el caso, puede quitar el enlace siguiendo las instrucciones de [cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="ba27b-110">If this is the case, you can remove the binding by following the instructions in [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="ba27b-111">Se ha detenido y dado de baja el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ba27b-111">The send port is both stopped and unenlisted.</span></span> <span data-ttu-id="ba27b-112">Para obtener instrucciones acerca de detener y dar de baja un puerto de envío, consulte [cómo dar de baja un puerto de envío o grupo de puertos de envío](../core/how-to-unenlist-a-send-port-or-send-port-group.md) y [cómo detener un puerto de envío o un grupo de puertos de envío](../core/how-to-stop-a-send-port-or-send-port-group.md).</span><span class="sxs-lookup"><span data-stu-id="ba27b-112">For instructions on stopping and unenlisting a send port, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md) and [How to Stop a Send Port or Send Port Group](../core/how-to-stop-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="ba27b-113">Ninguna entidad hace referencia al puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ba27b-113">The send port is not referenced by a party.</span></span> <span data-ttu-id="ba27b-114">Para obtener instrucciones acerca de cómo quitar una referencia a un puerto de envío de una entidad, consulte [cómo ver o editar una entidad](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span><span class="sxs-lookup"><span data-stu-id="ba27b-114">For instructions on removing a reference to a send port from a party, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span></span>  
  
-   <span data-ttu-id="ba27b-115">El puerto de envío no está incluido en un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="ba27b-115">The send port is not included in a send port group.</span></span> <span data-ttu-id="ba27b-116">Para obtener instrucciones acerca de cómo quitar un puerto de envío de un grupo de puertos de envío, consulte [cómo quitar un puerto de envío de un grupo de puertos de envío](../core/how-to-remove-a-send-port-from-a-send-port-group.md).</span><span class="sxs-lookup"><span data-stu-id="ba27b-116">For instructions on removing a send port from a send port group, see [How to Remove a Send Port from a Send Port Group](../core/how-to-remove-a-send-port-from-a-send-port-group.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba27b-117">El desarrollador de aplicaciones puede eliminar un puerto de envío durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="ba27b-117">The application developer can delete a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ba27b-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ba27b-118">Prerequisites</span></span>  
 <span data-ttu-id="ba27b-119">Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ba27b-119">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ba27b-120">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="ba27b-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-send-port"></a><span data-ttu-id="ba27b-121">Para eliminar un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="ba27b-121">To delete a send port</span></span>  
  
1.  <span data-ttu-id="ba27b-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ba27b-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ba27b-123">En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk, expanda aplicaciones y, a continuación, expanda la aplicación que contiene el puerto de envío que desea eliminar</span><span class="sxs-lookup"><span data-stu-id="ba27b-123">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand Applications, and then expand the application containing the send port that you want to delete</span></span>  
  
3.  <span data-ttu-id="ba27b-124">Haga clic en **puertos de envío**, haga clic en el puerto de envío y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ba27b-124">Click **Send Ports**, right-click the send port, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba27b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba27b-125">See Also</span></span>  
 [<span data-ttu-id="ba27b-126">Creación y configuración de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="ba27b-126">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)