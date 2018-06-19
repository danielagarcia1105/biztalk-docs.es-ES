---
title: No se puede crear el elemento de configuración de comportamiento de punto de conexión de configuración XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89d906a4-ea85-42d8-8e9e-0a3a7774bcd8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc10a737f2c0a2f344a106868c910a2ecb8144bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286836"
---
# <a name="unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration"></a><span data-ttu-id="a28ca-102">No se puede crear el elemento de configuración de comportamiento del extremo a partir de la configuración XML.</span><span class="sxs-lookup"><span data-stu-id="a28ca-102">Unable to create endpoint behavior configuration element from XML configuration</span></span>
## <a name="details"></a><span data-ttu-id="a28ca-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a28ca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a28ca-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a28ca-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a28ca-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a28ca-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="a28ca-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a28ca-106">Event ID</span></span>|<span data-ttu-id="a28ca-107">0</span><span class="sxs-lookup"><span data-stu-id="a28ca-107">0</span></span>|  
|<span data-ttu-id="a28ca-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a28ca-108">Event Source</span></span>|<span data-ttu-id="a28ca-109">0</span><span class="sxs-lookup"><span data-stu-id="a28ca-109">0</span></span>|  
|<span data-ttu-id="a28ca-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a28ca-110">Component</span></span>|<span data-ttu-id="a28ca-111">0</span><span class="sxs-lookup"><span data-stu-id="a28ca-111">0</span></span>|  
|<span data-ttu-id="a28ca-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a28ca-112">Symbolic Name</span></span>|<span data-ttu-id="a28ca-113">0</span><span class="sxs-lookup"><span data-stu-id="a28ca-113">0</span></span>|  
|<span data-ttu-id="a28ca-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a28ca-114">Message Text</span></span>|<span data-ttu-id="a28ca-115">No se puede crear el elemento de configuración de comportamiento del extremo a partir de la configuración XML.</span><span class="sxs-lookup"><span data-stu-id="a28ca-115">Unable to create endpoint behavior configuration element from XML configuration</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a28ca-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a28ca-116">Explanation</span></span>  
 <span data-ttu-id="a28ca-117">Este error indica que el adaptador no cargó la configuración de comportamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="a28ca-117">This error indicates the adapter did not load the endpoint behavior configuration.</span></span> <span data-ttu-id="a28ca-118">Esta situación se produce principalmente con los adaptadores de WCF-Custom y WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="a28ca-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a28ca-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a28ca-119">User Action</span></span>  
 <span data-ttu-id="a28ca-120">Use el procedimiento siguiente para configurar el comportamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="a28ca-120">Use the following procedure to configure the endpoint behavior.</span></span>  
  
#### <a name="to-configure-the-endpoint-behavior"></a><span data-ttu-id="a28ca-121">Para configurar el comportamiento del extremo</span><span class="sxs-lookup"><span data-stu-id="a28ca-121">To configure the endpoint behavior</span></span>  
  
1.  <span data-ttu-id="a28ca-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a28ca-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a28ca-123">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a28ca-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="a28ca-124">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="a28ca-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="a28ca-125">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="a28ca-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="a28ca-126">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a28ca-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="a28ca-127">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="a28ca-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="a28ca-128">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a28ca-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="a28ca-129">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **comportamiento** ficha.</span><span class="sxs-lookup"><span data-stu-id="a28ca-129">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
9. <span data-ttu-id="a28ca-130">En el **comportamiento** sección, compruebe el **EndpointBehavior** configuración.</span><span class="sxs-lookup"><span data-stu-id="a28ca-130">In the **Behavior** section, check the **EndpointBehavior** configuration.</span></span>