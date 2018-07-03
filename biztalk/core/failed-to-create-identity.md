---
title: No se pudo crear la identidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 531f1057-1b6d-40ae-bf2f-a36baf4e0341
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203257b261bba176b0a768da8242dad45366a923
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998117"
---
# <a name="failed-to-create-identity"></a><span data-ttu-id="b25bf-102">No se pudo crear la identidad</span><span class="sxs-lookup"><span data-stu-id="b25bf-102">Failed to create identity</span></span>
## <a name="details"></a><span data-ttu-id="b25bf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b25bf-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="b25bf-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b25bf-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="b25bf-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b25bf-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="b25bf-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b25bf-106">Event ID</span></span>     |                                         <span data-ttu-id="b25bf-107">0</span><span class="sxs-lookup"><span data-stu-id="b25bf-107">0</span></span>                                          |
|  <span data-ttu-id="b25bf-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b25bf-108">Event Source</span></span>   |                                         <span data-ttu-id="b25bf-109">0</span><span class="sxs-lookup"><span data-stu-id="b25bf-109">0</span></span>                                          |
|    <span data-ttu-id="b25bf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b25bf-110">Component</span></span>    |                                         <span data-ttu-id="b25bf-111">0</span><span class="sxs-lookup"><span data-stu-id="b25bf-111">0</span></span>                                          |
|  <span data-ttu-id="b25bf-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b25bf-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="b25bf-113">0</span><span class="sxs-lookup"><span data-stu-id="b25bf-113">0</span></span>                                          |
|  <span data-ttu-id="b25bf-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b25bf-114">Message Text</span></span>   |      <span data-ttu-id="b25bf-115">Este error indica que el adaptador no pudo crear la identidad de extremo.</span><span class="sxs-lookup"><span data-stu-id="b25bf-115">This error indicates the adapter failed to create the endpoint identity.</span></span>      |

## <a name="explanation"></a><span data-ttu-id="b25bf-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="b25bf-116">Explanation</span></span>  
 <span data-ttu-id="b25bf-117">Este error indica que el adaptador no pudo crear la identidad de extremo.</span><span class="sxs-lookup"><span data-stu-id="b25bf-117">This error indicates the adapter failed to create the endpoint identity.</span></span>  

## <a name="user-action"></a><span data-ttu-id="b25bf-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b25bf-118">User Action</span></span>  
 <span data-ttu-id="b25bf-119">Use el procedimiento siguiente para configurar la identidad de extremo.</span><span class="sxs-lookup"><span data-stu-id="b25bf-119">Use the following procedure to configure the endpoint identity.</span></span>  

#### <a name="to-configure-the-endpoint-identity"></a><span data-ttu-id="b25bf-120">Para configurar la identidad de extremo</span><span class="sxs-lookup"><span data-stu-id="b25bf-120">To configure the endpoint identity</span></span>  

1. <span data-ttu-id="b25bf-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="b25bf-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="b25bf-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b25bf-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="b25bf-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="b25bf-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="b25bf-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="b25bf-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="b25bf-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b25bf-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="b25bf-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="b25bf-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="b25bf-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="b25bf-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="b25bf-128">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="b25bf-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="b25bf-129">En el **identidad de extremo** sección, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="b25bf-129">In the **Endpoint Identity** section, click **Edit**.</span></span>  

10. <span data-ttu-id="b25bf-130">En el **Editor de identidad** diálogo cuadro, asegúrese de que la configuración sea válida.</span><span class="sxs-lookup"><span data-stu-id="b25bf-130">In the **Identity Editor** dialog box, ensure that the settings are valid.</span></span>
