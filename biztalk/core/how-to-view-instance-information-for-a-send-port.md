---
title: Cómo ver información de instancia de un puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, viewing
- managing [send ports], viewing
- viewing, send ports
ms.assetid: 37cf6561-5341-4a05-b531-33ab0334966e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc1ae4401303845f92b95e6cdf7f4903c165b07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975149"
---
# <a name="how-to-view-instance-information-for-a-send-port"></a><span data-ttu-id="fced1-102">Cómo ver información de instancia de un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="fced1-102">How to View Instance Information for a Send Port</span></span>
<span data-ttu-id="fced1-103">En este tema, se describe cómo utilizar la consola de administración de BizTalk Server para ver una lista de las instancias de servicio en ejecución de un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="fced1-103">This topic describes how to use the BizTalk Server Administration console to view a list of the running service instances of a send port.</span></span> <span data-ttu-id="fced1-104">Una instancia de servicio es una instancia de servicio del puerto de envío que se crea al enviar un mensaje al puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="fced1-104">A service instance is an instance of the send port service that is created when a message is sent to the send port.</span></span> <span data-ttu-id="fced1-105">Al seguir el procedimiento que se detalla en este tema, la información de instancia se muestra en la página Información general del grupo del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="fced1-105">When you follow the procedure in this topic, instance information displays in the Group Overview page for the send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fced1-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fced1-106">Prerequisites</span></span>  
 <span data-ttu-id="fced1-107">Para llevar a cabo el procedimiento descrito en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fced1-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> <span data-ttu-id="fced1-108">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="fced1-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-a-send-port"></a><span data-ttu-id="fced1-109">Para ver información de instancia de un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="fced1-109">To view instance information for a send port</span></span>  
  
1. <span data-ttu-id="fced1-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="fced1-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="fced1-111">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea ver la información de instancia de servicio de un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="fced1-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to view service instance information for a send port.</span></span>  
  
3. <span data-ttu-id="fced1-112">Haga clic en **puertos de envío**, haga clic en el puerto de envío, seleccione **vista**y, a continuación, haga clic en **información de la instancia**.</span><span class="sxs-lookup"><span data-stu-id="fced1-112">Click **Send Ports**, right-click the send port, point to **View**, and then click **Instance Information**.</span></span>  
  
    <span data-ttu-id="fced1-113">En el panel de resultados de consulta de la sección inferior de la página, se muestran todas las instancias en ejecución del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="fced1-113">The query results panel in the lower section of the page displays all running instances of the send port.</span></span>  
  
4. <span data-ttu-id="fced1-114">Para refinar la consulta y ver la información de la instancia de servicio diferente para el puerto de envío, haga clic en el cuadro en **valor** para el campo Buscar y seleccionar el tipo de instancia para ver y, a continuación, haga clic en **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="fced1-114">To refine the query and view different service instance information for the send port, click the box under **Value** for the Search For field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="fced1-115">Para obtener más información acerca de la creación de consultas, vea los temas que aparecen en Vea también al ejecutar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fced1-115">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fced1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fced1-116">See Also</span></span>  
 <span data-ttu-id="fced1-117">[Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="fced1-117">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 <span data-ttu-id="fced1-118">[Cómo buscar instancias de servicio de ejecución](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="fced1-118">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="fced1-119">[Cómo buscar instancias de servicio suspendidas](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="fced1-119">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="fced1-120">[Cómo buscar mensajes](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="fced1-120">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="fced1-121">Cómo buscar suscripciones</span><span class="sxs-lookup"><span data-stu-id="fced1-121">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)