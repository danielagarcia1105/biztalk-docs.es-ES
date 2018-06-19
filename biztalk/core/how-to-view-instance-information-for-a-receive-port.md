---
title: Cómo ver información de instancia de un puerto de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], viewing
- receive ports, viewing
- viewing, receive ports
ms.assetid: dad038bc-1202-489b-b144-a93bf1f53c0c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e46da8bfb99246b67f93c02fa19689099f8acb24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256804"
---
# <a name="how-to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="2f217-102">Cómo ver información de instancia de un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="2f217-102">How to View Instance Information for a Receive Port</span></span>
<span data-ttu-id="2f217-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para ver instancias de servicio de un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="2f217-103">This topic describes how to use the BizTalk Server Administration console to view the service instances for a receive port.</span></span> <span data-ttu-id="2f217-104">Siempre que el puerto de recepción recibe un mensaje, se crea una instancia de servicio para procesar ese mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f217-104">Each time the receive port receives a message, a service instance is created to process the message.</span></span> <span data-ttu-id="2f217-105">Al seguir el procedimiento que se detalla en este tema, la información de instancia se muestra en la página Información general del grupo del puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="2f217-105">When you follow the procedure in this topic, instance information displays in the Group Overview page for the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2f217-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2f217-106">Prerequisites</span></span>  
 <span data-ttu-id="2f217-107">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2f217-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="2f217-108">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="2f217-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="2f217-109">Para ver información de instancia de un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="2f217-109">To view instance information for a receive port</span></span>  
  
1.  <span data-ttu-id="2f217-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2f217-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2f217-111">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee ver la información de instancia de un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="2f217-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to view instance information for a receive port.</span></span>  
  
3.  <span data-ttu-id="2f217-112">Haga clic en **puertos de recepción**, seleccione el puerto de recepción, haga clic en **vista**y, a continuación, haga clic en **información de instancia**.</span><span class="sxs-lookup"><span data-stu-id="2f217-112">Click **Receive Ports**, select the receive port, click **View**, and then click **Instance Information**.</span></span>  
  
     <span data-ttu-id="2f217-113">En el panel de resultados de consulta de la sección inferior de la página, se muestran todas las instancias del puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="2f217-113">The query results panel in the lower section of the page displays all instances of the receive port.</span></span>  
  
4.  <span data-ttu-id="2f217-114">Para refinar la consulta y ver la información de instancia diferente para el puerto de recepción, active la casilla situada bajo **valor** para el **buscar** , a continuación, seleccione el tipo de instancia desea ver y, a continuación, haga clic en **ejecutar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2f217-114">To refine the query and view different instance information for the receive port, click the box under **Value** for the **Search For** field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="2f217-115">Para obtener más información acerca de la creación de consultas, vea los temas que aparecen en Vea también al ejecutar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2f217-115">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f217-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f217-116">See Also</span></span>  
 <span data-ttu-id="2f217-117">[Administrar puertos de recepción](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="2f217-117">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 <span data-ttu-id="2f217-118">[Búsqueda de instancias de servicio en ejecución](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="2f217-118">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="2f217-119">[Cómo buscar instancias de servicio suspendidas](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="2f217-119">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="2f217-120">[Cómo buscar mensajes](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="2f217-120">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="2f217-121">Cómo buscar suscripciones</span><span class="sxs-lookup"><span data-stu-id="2f217-121">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)