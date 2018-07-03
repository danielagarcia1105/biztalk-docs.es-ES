---
title: No se puede crear el elemento de configuración de comportamiento de servicio de configuración XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6732e5d2-bb4b-48ec-af59-467eede80f36
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e1668e7e9159ef7c922c68b54893c604b84c560
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017343"
---
# <a name="unable-to-create-service-behavior-configuration-element-from-xml-configuration"></a><span data-ttu-id="8e0d8-102">No se puede crear el elemento de configuración de comportamiento del servicio a partir de la configuración XML</span><span class="sxs-lookup"><span data-stu-id="8e0d8-102">Unable to create service behavior configuration element from XML configuration</span></span>
## <a name="details"></a><span data-ttu-id="8e0d8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8e0d8-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="8e0d8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8e0d8-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="8e0d8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8e0d8-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="8e0d8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8e0d8-106">Event ID</span></span>     |                                         <span data-ttu-id="8e0d8-107">0</span><span class="sxs-lookup"><span data-stu-id="8e0d8-107">0</span></span>                                          |
|  <span data-ttu-id="8e0d8-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8e0d8-108">Event Source</span></span>   |                                         <span data-ttu-id="8e0d8-109">0</span><span class="sxs-lookup"><span data-stu-id="8e0d8-109">0</span></span>                                          |
|    <span data-ttu-id="8e0d8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8e0d8-110">Component</span></span>    |                                         <span data-ttu-id="8e0d8-111">0</span><span class="sxs-lookup"><span data-stu-id="8e0d8-111">0</span></span>                                          |
|  <span data-ttu-id="8e0d8-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8e0d8-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="8e0d8-113">0</span><span class="sxs-lookup"><span data-stu-id="8e0d8-113">0</span></span>                                          |
|  <span data-ttu-id="8e0d8-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8e0d8-114">Message Text</span></span>   |  <span data-ttu-id="8e0d8-115">No se puede crear el elemento de configuración de comportamiento del servicio a partir de la configuración XML.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-115">Unable to create service behavior configuration element from XML configuration.</span></span>   |

## <a name="explanation"></a><span data-ttu-id="8e0d8-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="8e0d8-116">Explanation</span></span>  
 <span data-ttu-id="8e0d8-117">Este error indica que el adaptador no cargó la configuración de comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-117">This error indicates the adapter did not load the service behavior configuration.</span></span> <span data-ttu-id="8e0d8-118">Esta situación se produce principalmente con los adaptadores de WCF-Custom y WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8e0d8-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8e0d8-119">User Action</span></span>  
 <span data-ttu-id="8e0d8-120">Use el procedimiento siguiente para configurar el comportamiento de servicio.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-120">Use the following procedure to configure the service behavior.</span></span>  

#### <a name="to-configure-the-service-behavior"></a><span data-ttu-id="8e0d8-121">Para configurar el comportamiento de servicio</span><span class="sxs-lookup"><span data-stu-id="8e0d8-121">To configure the service behavior</span></span>  

1. <span data-ttu-id="8e0d8-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="8e0d8-123">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="8e0d8-124">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="8e0d8-125">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="8e0d8-126">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="8e0d8-127">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="8e0d8-128">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="8e0d8-129">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **comportamiento** ficha.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

9. <span data-ttu-id="8e0d8-130">En el **comportamiento** sección, compruebe el **ServiceBehavior** configuración.</span><span class="sxs-lookup"><span data-stu-id="8e0d8-130">In the **Behavior** section, check the **ServiceBehavior** configuration.</span></span>
