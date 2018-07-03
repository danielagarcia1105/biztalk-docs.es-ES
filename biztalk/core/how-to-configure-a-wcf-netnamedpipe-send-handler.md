---
title: Cómo configurar un controlador de envío WCF-NetNamedPipe | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, global adapters
- configuring [WCF-NetNamedPipe adapters], global adapters
- send handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], send handlers
ms.assetid: 1f281649-d09f-44eb-8af5-1f83233fab60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc9ef8086ae0cda04da3ecdc7eacbfcb6d01f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970229"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-send-handler"></a><span data-ttu-id="4ca46-102">Cómo configurar un controlador de envío WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="4ca46-102">How to Configure a WCF-NetNamedPipe Send Handler</span></span>
<span data-ttu-id="4ca46-103">Utilice el siguiente procedimiento para configurar un controlador de envío WCF-NetNamedPipe.</span><span class="sxs-lookup"><span data-stu-id="4ca46-103">Use the following procedure to configure a WCF-NetNamedPipe send handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-send-handler"></a><span data-ttu-id="4ca46-104">Para cambiar las variables globales del controlador de envío WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="4ca46-104">To change global variables for a WCF-NetNamedPipe send handler</span></span>  

1. <span data-ttu-id="4ca46-105">En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="4ca46-105">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="4ca46-106">En la lista de adaptadores expandida, haga clic en **WCF-NetNamedPipe**, en el panel derecho, el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4ca46-106">In the expanded adapter list, click **WCF-NetNamedPipe**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="4ca46-107">En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="4ca46-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  

4. <span data-ttu-id="4ca46-108">En el **General** , haga clic **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4ca46-108">In the **General** tab, click **Properties**.</span></span> <span data-ttu-id="4ca46-109">En el **controlador de envío** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ca46-109">On the **Send handler** tab, do the following:</span></span>  


   |        <span data-ttu-id="4ca46-110">Use</span><span class="sxs-lookup"><span data-stu-id="4ca46-110">Use this</span></span>         |                                                                                                                                                                                                                                                                             <span data-ttu-id="4ca46-111">Para</span><span class="sxs-lookup"><span data-stu-id="4ca46-111">To do this</span></span>                                                                                                                                                                                                                                                                             |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="4ca46-112">**Número máximo de conexiones**</span><span class="sxs-lookup"><span data-stu-id="4ca46-112">**Maximum connections**</span></span> | <span data-ttu-id="4ca46-113">Especificar el número máximo de conexiones salientes para cada extremo almacenado en la caché del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="4ca46-113">Specify the maximum number of outbound connections for each endpoint that is cached in the connection pool.</span></span> <span data-ttu-id="4ca46-114">Esto limita el número de conexiones que se almacena en la caché para cada extremo remoto único.</span><span class="sxs-lookup"><span data-stu-id="4ca46-114">This limits the number of connections that are cached for each unique remote endpoint.</span></span> <span data-ttu-id="4ca46-115">Es conveniente establecer un valor que sea mayor que el número máximo de conexiones que espera que se almacene en la caché de cualquier extremo remoto único.</span><span class="sxs-lookup"><span data-stu-id="4ca46-115">You should set this value to be greater than the maximum number of connections that you expect to be cached for any unique remote endpoint.</span></span> <span data-ttu-id="4ca46-116">Si el número de conexiones salientes activas supera el valor máximo, puede parecer que el servicio no responde a los puertos de envío WCF-NetNamedPipe que se ejecutan en este controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="4ca46-116">If the number of active outbound connections exceeds this maximum value, then the service may appear unresponsive to the WCF-NetNamedPipe send ports running under this send hander.</span></span><br /><br /> <span data-ttu-id="4ca46-117">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="4ca46-117">The default is 10.</span></span> |


5. <span data-ttu-id="4ca46-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ca46-118">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4ca46-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ca46-119">See Also</span></span>  
 <span data-ttu-id="4ca46-120">[Consumir servicios WCF](../core/consuming-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="4ca46-120">[Consuming WCF Services](../core/consuming-wcf-services.md) </span></span>  
 [<span data-ttu-id="4ca46-121">Configuración del adaptador de WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="4ca46-121">Configuring the WCF-NetNamedPipe Adapter</span></span>](../core/configuring-the-wcf-netnamedpipe-adapter.md)