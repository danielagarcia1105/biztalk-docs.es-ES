---
title: Cómo configurar un controlador de envío WCF-NetTcp | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], send handlers
- WCF-NetTcp adapters, global variables
- configuring [WCF-NetTcp adapters], global variables
ms.assetid: c60fe03d-7e11-4e08-9a24-8ff443eee9c1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5855c7405437d7958f53d679ad2eafc670608c7a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014109"
---
# <a name="how-to-configure-a-wcf-nettcp-send-handler"></a><span data-ttu-id="a54de-102">Cómo configurar un controlador de envío WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="a54de-102">How to Configure a WCF-NetTcp Send Handler</span></span>
<span data-ttu-id="a54de-103">Para configurar el controlador de envío WCF-NetTcp, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="a54de-103">Use the following procedure to configure a WCF-NetTcp send handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-nettcp-send-handler"></a><span data-ttu-id="a54de-104">Para cambiar las variables globales de un controlador de envío WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="a54de-104">To change global variables for a WCF-NetTcp send handler</span></span>  

1. <span data-ttu-id="a54de-105">En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="a54de-105">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="a54de-106">En la lista de adaptadores expandida, haga clic en **WCF-NetTcp**, en el panel derecho, el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a54de-106">In the expanded adapter list, click **WCF-NetTcp**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="a54de-107">En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="a54de-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  

4. <span data-ttu-id="a54de-108">En el **General** , haga clic **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a54de-108">On the **General** tab, click **Properties**.</span></span> <span data-ttu-id="a54de-109">En el **controlador de envío** ficha, realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a54de-109">On the **Send handler** tab, do the following.</span></span>  


   |        <span data-ttu-id="a54de-110">Use</span><span class="sxs-lookup"><span data-stu-id="a54de-110">Use this</span></span>         |                                                                                                                                                                                                                                                                          <span data-ttu-id="a54de-111">Para</span><span class="sxs-lookup"><span data-stu-id="a54de-111">To do this</span></span>                                                                                                                                                                                                                                                                          |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="a54de-112">**Número máximo de conexiones**</span><span class="sxs-lookup"><span data-stu-id="a54de-112">**Maximum connections**</span></span> | <span data-ttu-id="a54de-113">Especificar el número máximo de conexiones salientes para cada extremo almacenado en la caché del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="a54de-113">Specify the maximum number of outbound connections for each endpoint that is cached in the connection pool.</span></span> <span data-ttu-id="a54de-114">Esto limita el número de conexiones que se almacena en la caché para cada extremo remoto único.</span><span class="sxs-lookup"><span data-stu-id="a54de-114">This limits the number of connections that are cached for each unique remote endpoint.</span></span> <span data-ttu-id="a54de-115">Es conveniente establecer un valor que sea mayor que el número máximo de conexiones que espera que se almacene en la caché de cualquier extremo remoto único.</span><span class="sxs-lookup"><span data-stu-id="a54de-115">You should set this value to be greater than the maximum number of connections that you expect to be cached for any unique remote endpoint.</span></span> <span data-ttu-id="a54de-116">Si el número de conexiones salientes activas supera el valor máximo, puede parecer que el servicio no responde a los puertos de envío WCF-NetTcp que se ejecutan en este controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="a54de-116">If the number of active outbound connections exceeds this maximum value, then the service may appear unresponsive to the WCF-NetTcp send ports running under this send hander.</span></span><br /><br /> <span data-ttu-id="a54de-117">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="a54de-117">The default is 10.</span></span> |


5. <span data-ttu-id="a54de-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a54de-118">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a54de-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a54de-119">See Also</span></span>  
 <span data-ttu-id="a54de-120">[Consumir servicios WCF](../core/consuming-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="a54de-120">[Consuming WCF Services](../core/consuming-wcf-services.md) </span></span>  
 [<span data-ttu-id="a54de-121">Configuración del adaptador de WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="a54de-121">Configuring the WCF-NetTcp Adapter</span></span>](../core/configuring-the-wcf-nettcp-adapter.md)