---
title: Enlace no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e851f7f-ffc8-4f55-b06e-501a7f41b32a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 589d55d4ffccadf277f586104f8d5b9b1bf36b00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996229"
---
# <a name="invalid-binding"></a><span data-ttu-id="1bc57-102">Enlace no válido.</span><span class="sxs-lookup"><span data-stu-id="1bc57-102">Invalid binding</span></span>
## <a name="details"></a><span data-ttu-id="1bc57-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1bc57-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="1bc57-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1bc57-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="1bc57-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1bc57-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="1bc57-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1bc57-106">Event ID</span></span>     |                                         <span data-ttu-id="1bc57-107">0</span><span class="sxs-lookup"><span data-stu-id="1bc57-107">0</span></span>                                          |
|  <span data-ttu-id="1bc57-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1bc57-108">Event Source</span></span>   |                                         <span data-ttu-id="1bc57-109">0</span><span class="sxs-lookup"><span data-stu-id="1bc57-109">0</span></span>                                          |
|    <span data-ttu-id="1bc57-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1bc57-110">Component</span></span>    |                                         <span data-ttu-id="1bc57-111">0</span><span class="sxs-lookup"><span data-stu-id="1bc57-111">0</span></span>                                          |
|  <span data-ttu-id="1bc57-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1bc57-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="1bc57-113">0</span><span class="sxs-lookup"><span data-stu-id="1bc57-113">0</span></span>                                          |
|  <span data-ttu-id="1bc57-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1bc57-114">Message Text</span></span>   |                                  <span data-ttu-id="1bc57-115">Enlace no válido.</span><span class="sxs-lookup"><span data-stu-id="1bc57-115">Invalid binding</span></span>                                   |

## <a name="explanation"></a><span data-ttu-id="1bc57-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1bc57-116">Explanation</span></span>  
 <span data-ttu-id="1bc57-117">Este error indica que el adaptador no puede crear el enlace especificado en la configuración de enlace de la ubicación de recepción o el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="1bc57-117">This error indicates the adapter cannot create the binding specified in the binding configuration of the receive location or send port.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1bc57-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1bc57-118">User Action</span></span>  
 <span data-ttu-id="1bc57-119">Use el procedimiento siguiente para comprobar los elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="1bc57-119">Use the following procedure to verify binding elements.</span></span>  

#### <a name="to-verify-binding-elements"></a><span data-ttu-id="1bc57-120">Para comprobar los elementos de enlace</span><span class="sxs-lookup"><span data-stu-id="1bc57-120">To verify binding elements</span></span>  

1. <span data-ttu-id="1bc57-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="1bc57-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="1bc57-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1bc57-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="1bc57-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="1bc57-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="1bc57-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="1bc57-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="1bc57-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1bc57-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="1bc57-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="1bc57-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="1bc57-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="1bc57-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="1bc57-128">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="1bc57-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="1bc57-129">Asegúrese de que los elementos de enlace especificados en la configuración son válidos.</span><span class="sxs-lookup"><span data-stu-id="1bc57-129">Ensure the binding elements specified in the configuration are valid.</span></span>
