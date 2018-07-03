---
title: No se puede crear el elemento de enlace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b036833-12ba-463c-8df6-9d5e1ac26b6d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 117ad9a604f0b0d61cd494da52d84b8aabd4a9eb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987901"
---
# <a name="unable-to-create-binding-element"></a><span data-ttu-id="2f7c7-102">No se puede crear el elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="2f7c7-102">Unable to create binding element</span></span>
## <a name="details"></a><span data-ttu-id="2f7c7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2f7c7-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="2f7c7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2f7c7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="2f7c7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2f7c7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="2f7c7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2f7c7-106">Event ID</span></span>     |                                         <span data-ttu-id="2f7c7-107">0</span><span class="sxs-lookup"><span data-stu-id="2f7c7-107">0</span></span>                                          |
|  <span data-ttu-id="2f7c7-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2f7c7-108">Event Source</span></span>   |                                         <span data-ttu-id="2f7c7-109">0</span><span class="sxs-lookup"><span data-stu-id="2f7c7-109">0</span></span>                                          |
|    <span data-ttu-id="2f7c7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2f7c7-110">Component</span></span>    |                                         <span data-ttu-id="2f7c7-111">0</span><span class="sxs-lookup"><span data-stu-id="2f7c7-111">0</span></span>                                          |
|  <span data-ttu-id="2f7c7-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2f7c7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="2f7c7-113">0</span><span class="sxs-lookup"><span data-stu-id="2f7c7-113">0</span></span>                                          |
|  <span data-ttu-id="2f7c7-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2f7c7-114">Message Text</span></span>   |                 <span data-ttu-id="2f7c7-115">No se puede crear el elemento de enlace para el enlace"{0}</span><span class="sxs-lookup"><span data-stu-id="2f7c7-115">Unable to create binding element for binding "{0}</span></span>                  |

## <a name="explanation"></a><span data-ttu-id="2f7c7-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="2f7c7-116">Explanation</span></span>  
 <span data-ttu-id="2f7c7-117">Este error indica que el adaptador no puede crear el enlace especificado en la configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-117">This error indicates the adapter cannot create the binding specified in the configuration at runtime.</span></span> <span data-ttu-id="2f7c7-118">Esta situación se produce principalmente con los adaptadores de WCF-Custom y WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="2f7c7-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2f7c7-119">User Action</span></span>  
 <span data-ttu-id="2f7c7-120">Use el procedimiento siguiente para comprobar que los elementos de enlace son válidos.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-120">Use the following procedure to verify binding elements are valid.</span></span>  

#### <a name="to-verify-binding-elements"></a><span data-ttu-id="2f7c7-121">Para comprobar los elementos de enlace</span><span class="sxs-lookup"><span data-stu-id="2f7c7-121">To verify binding elements</span></span>  

1. <span data-ttu-id="2f7c7-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="2f7c7-123">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="2f7c7-124">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="2f7c7-125">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="2f7c7-126">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="2f7c7-127">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="2f7c7-128">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="2f7c7-129">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="2f7c7-130">Asegúrese de que los elementos de enlace especificados en la configuración son válidos.</span><span class="sxs-lookup"><span data-stu-id="2f7c7-130">Ensure that the binding elements specified in the configuration are valid.</span></span>
