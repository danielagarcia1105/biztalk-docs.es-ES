---
title: "Comunicación entre OrderBroker y OrderManager | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, publishing [MessageBox database]
- MessageBox database, publishing
ms.assetid: 1b77dcd2-f7a5-4013-b9a2-c06ace161792
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f438b0dfe744aae5867943f4b1493bb163994f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="communication-between-orderbroker-and-ordermanager"></a><span data-ttu-id="ccb50-102">Comunicación entre OrderBroker y OrderManager</span><span class="sxs-lookup"><span data-stu-id="ccb50-102">Communication between OrderBroker and OrderManager</span></span>
<span data-ttu-id="ccb50-103">El agente de pedido y las orquestaciones de administrador de pedidos (**OrderBroker**, **OrderManager**) se comunican a través del cuadro de mensajes base de datos en lugar de estar directamente enlazadas.</span><span class="sxs-lookup"><span data-stu-id="ccb50-103">The order broker and the order manager orchestrations (**OrderBroker**, **OrderManager**) communicate through the MessageBox database rather than being direct partner bound.</span></span> <span data-ttu-id="ccb50-104">Esto garantiza que el agente y el administrador estén flexiblemente acoplados de modo que, si fuera necesario, puedan ubicarse en grupos separados de BizTalk y ubicaciones geográficamente separadas.</span><span class="sxs-lookup"><span data-stu-id="ccb50-104">This ensures that the broker and manager are loosely coupled so that they can, if necessary, be located in separate BizTalk groups and in geographically-separated locations.</span></span> <span data-ttu-id="ccb50-105">Separar las orquestaciones de esta forma requiere sólo configuración administrativa y no requiere ningún cambio de código.</span><span class="sxs-lookup"><span data-stu-id="ccb50-105">Separating the orchestrations this way requires only administrative configuration and does not require any code changes.</span></span>  
  
 <span data-ttu-id="ccb50-106">En la solución configurada actualmente, el agente de pedidos marca mensajes para un administrador de pedidos determinado y los envía a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ccb50-106">In the solution as presently configured, the order broker marks messages for a particular order manager and sends them to the MessageBox.</span></span> <span data-ttu-id="ccb50-107">A su vez, el administrador de pedidos filtra los mensajes destinados a él y toma los mensajes del cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ccb50-107">In turn, the order manager filters for messages intended for it and takes those messages from the MessageBox.</span></span> <span data-ttu-id="ccb50-108">Este direccionamiento indirecto: comunicarse a través del cuadro de mensajes, en lugar de enlazar directamente — facilita el proceso mover el agente y el administrador para separar grupos.</span><span class="sxs-lookup"><span data-stu-id="ccb50-108">This indirection—communicating through the MessageBox rather than direct binding—makes it easy to move the broker and manager to separate groups.</span></span>  
  
 <span data-ttu-id="ccb50-109">Si hay grupos diferentes responsables de mantener al agente y al administrador, o si deben estar en ubicaciones geográficamente separadas, este diseño lo facilita.</span><span class="sxs-lookup"><span data-stu-id="ccb50-109">If there are different groups responsible for maintaining the broker and manager or if they need to be in geographically separate locations, the design makes it easy to accommodate this.</span></span> <span data-ttu-id="ccb50-110">Lo único que necesita es mover las orquestaciones a diferentes grupos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ccb50-110">All you need to do is move the orchestrations to different BizTalk groups.</span></span> <span data-ttu-id="ccb50-111">Una vez que las orquestaciones están en grupos separados, para volver a conectarlas basta con crear puertos.</span><span class="sxs-lookup"><span data-stu-id="ccb50-111">After the orchestrations are in separate groups, reconnecting them only requires creating ports.</span></span> <span data-ttu-id="ccb50-112">En el grupo del agente de pedidos, debe crear un puerto de envío que tenga el mismo filtro que el del administrador de pedidos, pero que reenvíe el mensaje al nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="ccb50-112">In the order broker group, you must create a send port that has the same filter as the order manager, but that forwards the message to the new group.</span></span> <span data-ttu-id="ccb50-113">En el grupo del administrador de pedidos, debe crear un puerto de recepción que reciba el mensaje y lo coloque en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ccb50-113">In the order manager group, you must create a receive port that receives the message and puts it in the MessageBox database.</span></span>  
  
 <span data-ttu-id="ccb50-114">Puede mover las aplicaciones exportándolas para crear archivos MSI, una para el agente y otra para el administrador.</span><span class="sxs-lookup"><span data-stu-id="ccb50-114">You can move the applications by exporting them to create MSI files, one each for the broker and manager.</span></span> <span data-ttu-id="ccb50-115">Para obtener más información acerca de cómo exportar aplicaciones, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="ccb50-115">For more information about exporting applications, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb50-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccb50-116">See Also</span></span>  
 [<span data-ttu-id="ccb50-117">Aspectos destacados de la implementación de la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="ccb50-117">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)