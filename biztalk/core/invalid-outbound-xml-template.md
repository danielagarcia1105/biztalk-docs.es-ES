---
title: Plantilla XML saliente no válida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f29bb60-8c04-4921-84bf-c629540a1c83
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b48f40ad758d61b802ed7e514e2e687a005842
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011909"
---
# <a name="invalid-outbound-xml-template"></a><span data-ttu-id="4ebe4-102">Plantilla XML saliente no válida.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-102">Invalid outbound XML template</span></span>
## <a name="details"></a><span data-ttu-id="4ebe4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4ebe4-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="4ebe4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4ebe4-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="4ebe4-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4ebe4-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="4ebe4-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4ebe4-106">Event ID</span></span>     |                                         <span data-ttu-id="4ebe4-107">0</span><span class="sxs-lookup"><span data-stu-id="4ebe4-107">0</span></span>                                          |
|  <span data-ttu-id="4ebe4-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4ebe4-108">Event Source</span></span>   |                                         <span data-ttu-id="4ebe4-109">0</span><span class="sxs-lookup"><span data-stu-id="4ebe4-109">0</span></span>                                          |
|    <span data-ttu-id="4ebe4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4ebe4-110">Component</span></span>    |                                         <span data-ttu-id="4ebe4-111">0</span><span class="sxs-lookup"><span data-stu-id="4ebe4-111">0</span></span>                                          |
|  <span data-ttu-id="4ebe4-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4ebe4-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="4ebe4-113">0</span><span class="sxs-lookup"><span data-stu-id="4ebe4-113">0</span></span>                                          |
|  <span data-ttu-id="4ebe4-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4ebe4-114">Message Text</span></span>   |                           <span data-ttu-id="4ebe4-115">Plantilla XML saliente no válida.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-115">Invalid outbound XML template</span></span>                            |
  
## <a name="explanation"></a><span data-ttu-id="4ebe4-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="4ebe4-116">Explanation</span></span>  
 <span data-ttu-id="4ebe4-117">Podrían haber varias razones.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-117">There could be multiple reasons.</span></span> <span data-ttu-id="4ebe4-118">La plantilla de mensaje saliente de WCF puede ser XML no válido.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-118">The outbound WCF message body template may not be valid XML.</span></span> <span data-ttu-id="4ebe4-119">Puede contener caracteres no válidos en la codificación.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-119">It may contain invalid characters in the given encoding.</span></span> <span data-ttu-id="4ebe4-120">Es posible que falte el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-120">The root element may be missing.</span></span> <span data-ttu-id="4ebe4-121">Es posible que los datos en el nivel de raíz no sean válidos.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4ebe4-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4ebe4-122">User Action</span></span>  
 <span data-ttu-id="4ebe4-123">Asegúrese de que la expresión de la plantilla contenga código XML válido.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-123">Ensure that template expression has valid XML code.</span></span> <span data-ttu-id="4ebe4-124">Asegúrese de que no contiene ningún carácter no válido y que únicamente hay un elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-124">Ensure that It doesn’t contain any invalid characters and that there is only one root element.</span></span>  
  
1. <span data-ttu-id="4ebe4-125">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-125">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4ebe4-126">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-126">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="4ebe4-127">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-127">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="4ebe4-128">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-128">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="4ebe4-129">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-129">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="4ebe4-130">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-130">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="4ebe4-131">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-131">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="4ebe4-132">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **mensajes** ficha.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-132">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="4ebe4-133">En el **cuerpo del mensaje saliente de WCF** sección, seleccione **plantilla--contenido especificado por plantilla**.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-133">In the **Outbound WCF message body** section, select **Template--content specified by template**.</span></span>  
  
10. <span data-ttu-id="4ebe4-134">En el **XML** texto, asegúrese de que el código XML es válido.</span><span class="sxs-lookup"><span data-stu-id="4ebe4-134">In the **XML** text box, ensure that the XML code is valid.</span></span>  
  
    <span data-ttu-id="4ebe4-135">Para obtener más información sobre plantillas, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4ebe4-135">For additional information on templates, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="4ebe4-136">Especificación del cuerpo del mensaje para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="4ebe4-136">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)