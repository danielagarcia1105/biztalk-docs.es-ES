---
title: Elemento de enlace desconocido o inesperado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56021ff3-5abf-46ab-90bb-4531ccc9abd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bfe15cf5aeab233c4ecef56f7b278e0646de5ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015645"
---
# <a name="unknown-or-unexpected-binding-element"></a><span data-ttu-id="ef0c2-102">Elemento de enlace desconocido o inesperado.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-102">Unknown or unexpected binding element</span></span>
## <a name="details"></a><span data-ttu-id="ef0c2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ef0c2-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="ef0c2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ef0c2-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="ef0c2-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ef0c2-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="ef0c2-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ef0c2-106">Event ID</span></span>     |                                         <span data-ttu-id="ef0c2-107">0</span><span class="sxs-lookup"><span data-stu-id="ef0c2-107">0</span></span>                                          |
|  <span data-ttu-id="ef0c2-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ef0c2-108">Event Source</span></span>   |                                         <span data-ttu-id="ef0c2-109">0</span><span class="sxs-lookup"><span data-stu-id="ef0c2-109">0</span></span>                                          |
|    <span data-ttu-id="ef0c2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ef0c2-110">Component</span></span>    |                                         <span data-ttu-id="ef0c2-111">0</span><span class="sxs-lookup"><span data-stu-id="ef0c2-111">0</span></span>                                          |
|  <span data-ttu-id="ef0c2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ef0c2-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="ef0c2-113">0</span><span class="sxs-lookup"><span data-stu-id="ef0c2-113">0</span></span>                                          |
|  <span data-ttu-id="ef0c2-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ef0c2-114">Message Text</span></span>   |                       <span data-ttu-id="ef0c2-115">Elemento de enlace desconocido o inesperado.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-115">Unknown or unexpected binding element</span></span>                        |

## <a name="explanation"></a><span data-ttu-id="ef0c2-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ef0c2-116">Explanation</span></span>  
 <span data-ttu-id="ef0c2-117">Este error indica que el adaptador no encuentra el elemento de enlace definido por el usuario especificado en el enlace.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-117">This error indicates the adapter cannot find the user defined binding element specified in the binding.</span></span> <span data-ttu-id="ef0c2-118">Esta situación se produce principalmente con los adaptadores de WCF-Custom y WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ef0c2-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ef0c2-119">User Action</span></span>  
 <span data-ttu-id="ef0c2-120">Use el procedimiento siguiente para comprobar que los elementos de enlace son válidos.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-120">Use the following procedure to verify binding elements are valid.</span></span>  

#### <a name="to-verify-binding-elements-are-valid"></a><span data-ttu-id="ef0c2-121">Para comprobar que los elementos de enlace son válidos</span><span class="sxs-lookup"><span data-stu-id="ef0c2-121">To verify binding elements are valid</span></span>  

1. <span data-ttu-id="ef0c2-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="ef0c2-123">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="ef0c2-124">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="ef0c2-125">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="ef0c2-126">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="ef0c2-127">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="ef0c2-128">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="ef0c2-129">En WCF **[**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-129">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="ef0c2-130">Asegúrese de que los elementos de enlace especificados en la configuración son válidos.</span><span class="sxs-lookup"><span data-stu-id="ef0c2-130">Ensure that the binding elements specified in the configuration are valid.</span></span>
