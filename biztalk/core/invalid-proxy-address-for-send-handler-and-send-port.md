---
title: Dirección de proxy no válido (para el puerto de envío y de controlador de envío) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccedd23e-7d44-4419-b519-e04511e1f176
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f509676b17a04fdbe0f0934225b5dc64546fed8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973549"
---
# <a name="invalid-proxy-address-for-send-handler-and-send-port"></a><span data-ttu-id="0abd7-102">Dirección de proxy no válida (para controlador de envío y puerto de envío)</span><span class="sxs-lookup"><span data-stu-id="0abd7-102">Invalid proxy address (for send handler and send port)</span></span>
## <a name="details"></a><span data-ttu-id="0abd7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0abd7-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="0abd7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0abd7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="0abd7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0abd7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="0abd7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0abd7-106">Event ID</span></span>     |                                         <span data-ttu-id="0abd7-107">0</span><span class="sxs-lookup"><span data-stu-id="0abd7-107">0</span></span>                                          |
|  <span data-ttu-id="0abd7-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0abd7-108">Event Source</span></span>   |                                         <span data-ttu-id="0abd7-109">0</span><span class="sxs-lookup"><span data-stu-id="0abd7-109">0</span></span>                                          |
|    <span data-ttu-id="0abd7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0abd7-110">Component</span></span>    |                                         <span data-ttu-id="0abd7-111">0</span><span class="sxs-lookup"><span data-stu-id="0abd7-111">0</span></span>                                          |
|  <span data-ttu-id="0abd7-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0abd7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="0abd7-113">0</span><span class="sxs-lookup"><span data-stu-id="0abd7-113">0</span></span>                                          |
|  <span data-ttu-id="0abd7-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0abd7-114">Message Text</span></span>   |                             <span data-ttu-id="0abd7-115">Dirección de proxy no válida: {0}</span><span class="sxs-lookup"><span data-stu-id="0abd7-115">Invalid proxy address: {0}</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="0abd7-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="0abd7-116">Explanation</span></span>  
 <span data-ttu-id="0abd7-117">No proporcionó un controlador de envío WCF o un puerto de envío WCF con una dirección de proxy válida.</span><span class="sxs-lookup"><span data-stu-id="0abd7-117">You did not provide a WCF send handler or a WCF send port with a valid proxy address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0abd7-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0abd7-118">User Action</span></span>  
 <span data-ttu-id="0abd7-119">Use el procedimiento siguiente para configurar una dirección de proxy.</span><span class="sxs-lookup"><span data-stu-id="0abd7-119">Use the following procedure to configure a proxy address.</span></span>  
  
#### <a name="to-configure-a-proxy-address"></a><span data-ttu-id="0abd7-120">Para configurar una dirección de proxy</span><span class="sxs-lookup"><span data-stu-id="0abd7-120">To configure a proxy address</span></span>  
  
1. <span data-ttu-id="0abd7-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="0abd7-121">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="0abd7-122">En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="0abd7-122">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="0abd7-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="0abd7-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="0abd7-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="0abd7-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="0abd7-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0abd7-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="0abd7-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="0abd7-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="0abd7-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="0abd7-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="0abd7-128">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **Proxy** ficha.</span><span class="sxs-lookup"><span data-stu-id="0abd7-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Proxy** tab.</span></span>  
  
9. <span data-ttu-id="0abd7-129">Compruebe que la dirección del proxy en el **configuración de Proxy** sección está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0abd7-129">Verify that the proxy address in the **Proxy settings** section is configured properly.</span></span>  
  
   <span data-ttu-id="0abd7-130">Para obtener más información sobre los puertos de envío y los controladores de envío, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0abd7-130">For additional information on send ports and send handlers, see the following resources:</span></span>  
  
-   [<span data-ttu-id="0abd7-131">Cómo configurar un puerto de envío WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0abd7-131">How to Configure a WCF-WSHttp Send Port</span></span>](../core/how-to-configure-a-wcf-wshttp-send-port.md)  
  
-   [<span data-ttu-id="0abd7-132">Cómo configurar un puerto de envío WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="0abd7-132">How to Configure a WCF-BasicHttp Send Port</span></span>](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)  
  
-   [<span data-ttu-id="0abd7-133">Cómo configurar un controlador de envío WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="0abd7-133">How to Configure a WCF-BasicHttp Send Handler</span></span>](http://msdn.microsoft.com/library/18dcc616-4732-42f8-bd64-e55a5ebbaa49)  
  
-   [<span data-ttu-id="0abd7-134">Cómo configurar un controlador de envío WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0abd7-134">How to Configure a WCF-WSHttp Send Handler</span></span>](../core/how-to-configure-a-wcf-wshttp-send-handler.md)  
  
-   [<span data-ttu-id="0abd7-135">Cómo configurar un puerto de envío WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="0abd7-135">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)