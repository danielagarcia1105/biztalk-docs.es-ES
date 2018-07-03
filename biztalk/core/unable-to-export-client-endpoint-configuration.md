---
title: No se puede exportar la configuración de punto de conexión de cliente | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d93fe5e-fdb2-49c5-86de-d428b1ecda7f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 752546eb85f8285e18c0a38d0877637e3627b6a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999429"
---
# <a name="unable-to-export-client-endpoint-configuration"></a><span data-ttu-id="d3f11-102">No se puede exportar la configuración de extremo de cliente</span><span class="sxs-lookup"><span data-stu-id="d3f11-102">Unable to export client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="d3f11-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d3f11-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="d3f11-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d3f11-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="d3f11-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d3f11-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="d3f11-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d3f11-106">Event ID</span></span>     |                                         <span data-ttu-id="d3f11-107">0</span><span class="sxs-lookup"><span data-stu-id="d3f11-107">0</span></span>                                          |
|  <span data-ttu-id="d3f11-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d3f11-108">Event Source</span></span>   |                                         <span data-ttu-id="d3f11-109">0</span><span class="sxs-lookup"><span data-stu-id="d3f11-109">0</span></span>                                          |
|    <span data-ttu-id="d3f11-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d3f11-110">Component</span></span>    |                                         <span data-ttu-id="d3f11-111">0</span><span class="sxs-lookup"><span data-stu-id="d3f11-111">0</span></span>                                          |
|  <span data-ttu-id="d3f11-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d3f11-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="d3f11-113">0</span><span class="sxs-lookup"><span data-stu-id="d3f11-113">0</span></span>                                          |
|  <span data-ttu-id="d3f11-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d3f11-114">Message Text</span></span>   |              <span data-ttu-id="d3f11-115">No se puede exportar la configuración de punto de conexión de cliente a "{0}"</span><span class="sxs-lookup"><span data-stu-id="d3f11-115">Unable to export client endpoint configuration to "{0}"</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="d3f11-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="d3f11-116">Explanation</span></span>  
 <span data-ttu-id="d3f11-117">Este error indica una de las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3f11-117">This error indicates one of the following:</span></span>  
  
-   <span data-ttu-id="d3f11-118">El usuario no tiene permiso para escribir en el destino.</span><span class="sxs-lookup"><span data-stu-id="d3f11-118">The user may not have permission to write to the destination.</span></span>  
  
     <span data-ttu-id="d3f11-119">\- O BIEN</span><span class="sxs-lookup"><span data-stu-id="d3f11-119">\- OR -</span></span>  
  
-   <span data-ttu-id="d3f11-120">Algunas de las propiedades necesarias no se especificaron correctamente, como **dirección (URI)** y **BindingType**.</span><span class="sxs-lookup"><span data-stu-id="d3f11-120">Some of the required properties were not correctly specified, such as **Address (URI)** and **Binding Type**.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d3f11-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d3f11-121">User Action</span></span>  
 <span data-ttu-id="d3f11-122">Utilice el procedimiento siguiente para comprobar los permisos de usuario y confirmar **dirección (URI)** y **BindingType** configuración es válida.</span><span class="sxs-lookup"><span data-stu-id="d3f11-122">Use the following procedure to verify user permissions and confirm **Address (URI)** and **Binding Type** settings are valid.</span></span>  
  
#### <a name="to-verify-user-permissions-and-confirm-settings"></a><span data-ttu-id="d3f11-123">Para comprobar los permisos del usuario y confirmar la configuración</span><span class="sxs-lookup"><span data-stu-id="d3f11-123">To verify user permissions and confirm settings</span></span>  
  
1. <span data-ttu-id="d3f11-124">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d3f11-124">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d3f11-125">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d3f11-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="d3f11-126">Localice la aplicación y, a continuación, el transporte.</span><span class="sxs-lookup"><span data-stu-id="d3f11-126">Locate your application, and then locate your transport.</span></span>  
  
4. <span data-ttu-id="d3f11-127">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="d3f11-127">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="d3f11-128">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d3f11-128">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="d3f11-129">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="d3f11-129">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="d3f11-130">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="d3f11-130">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="d3f11-131">En WCF **[**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="d3f11-131">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="d3f11-132">Asegúrese de que está permitido escribir en la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="d3f11-132">Ensure writing to the destination folder is permitted.</span></span>  
  
10. <span data-ttu-id="d3f11-133">Compruebe el **comportamiento** ficha y el **identidad de extremo** configuración en **General** ficha para asegurarse de que son válidos.</span><span class="sxs-lookup"><span data-stu-id="d3f11-133">Check the **Behavior** tab and the **Endpoint Identity** settings in **General** tab to ensure they are valid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3f11-134">Debe tener permisos de escritura en la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="d3f11-134">You must have write permissions to the destination folder.</span></span> <span data-ttu-id="d3f11-135">Póngase en contacto con el administrador del equipo para obtener estos permisos.</span><span class="sxs-lookup"><span data-stu-id="d3f11-135">Contact the administrator of the machine to get these permissions.</span></span>