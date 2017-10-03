---
title: "Crear y configurar grupos de puertos de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6dd1ac37-a6e4-4ea0-9eff-ee400b3f3d74
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 987b1e9fe780ad6841a13a477678d3b61556fac7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-configuring-send-port-groups"></a><span data-ttu-id="df6b4-102">Crear y configurar grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="df6b4-102">Creating and Configuring Send Port Groups</span></span>

## <a name="overview"></a><span data-ttu-id="df6b4-103">Información general</span><span class="sxs-lookup"><span data-stu-id="df6b4-103">Overview</span></span>
<span data-ttu-id="df6b4-104">En esta sección se proporcionan instrucciones acerca del uso de la consola de administración de BizTalk Server para agregar grupos de puertos de envío a una aplicación de BizTalk, así como para configurar y eliminar grupos de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="df6b4-104">This section provides instructions on using the BizTalk Server Administration console to add send port groups to a BizTalk application as well as to configure and delete send port groups.</span></span> <span data-ttu-id="df6b4-105">Un grupo de puertos de envío es una colección de puertos de envío con nombre que puede utilizarse para enviar el mismo mensaje a varios destinos.</span><span class="sxs-lookup"><span data-stu-id="df6b4-105">A send port group is a named collection of send ports that can be used to send the same message to multiple destinations.</span></span> <span data-ttu-id="df6b4-106">Es posible enlazar grupos de puertos de envío con puertos de orquestación o utilizarlos para el enrutamiento basado en contenidos (CBR) del mismo modo que un puerto de envío individual.</span><span class="sxs-lookup"><span data-stu-id="df6b4-106">You can bind send port groups to orchestration ports or use them for content-based routing (CBR) just as you can for a single send port.</span></span> <span data-ttu-id="df6b4-107">Para obtener información general de grupos de puertos de envío, consulte [puertos de envío y grupos de puertos de envío](../core/send-ports-and-send-port-groups.md).</span><span class="sxs-lookup"><span data-stu-id="df6b4-107">For background information on send port groups, see [Send Ports and Send Port Groups](../core/send-ports-and-send-port-groups.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df6b4-108">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="df6b4-108">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="df6b4-109">Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="df6b4-109">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="df6b4-110">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="df6b4-110">Next steps</span></span>
  
-   [<span data-ttu-id="df6b4-111">Crear un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="df6b4-111">Create a Send Port Group</span></span>](../core/how-to-create-a-send-port-group.md)  
  
-   [<span data-ttu-id="df6b4-112">Agregar un puerto de envío a un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="df6b4-112">Add a Send Port to a Send Port Group</span></span>](../core/how-to-add-a-send-port-to-a-send-port-group.md)  
  
-   [<span data-ttu-id="df6b4-113">Quitar un puerto de envío de un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="df6b4-113">Remove a Send Port from a Send Port Group</span></span>](../core/how-to-remove-a-send-port-from-a-send-port-group.md)  
  
-   [<span data-ttu-id="df6b4-114">Configurar filtros para un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="df6b4-114">Configure Filters for a Send Port Group</span></span>](../core/how-to-configure-filters-for-a-send-port-group.md)  
  
-   [<span data-ttu-id="df6b4-115">Eliminar un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="df6b4-115">Delete a Send Port Group</span></span>](../core/how-to-delete-a-send-port-group.md)