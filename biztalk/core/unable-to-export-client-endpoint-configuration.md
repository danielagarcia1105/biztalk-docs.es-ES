---
title: "No se puede exportar la configuración de punto de conexión de cliente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d93fe5e-fdb2-49c5-86de-d428b1ecda7f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 941d42ff01bcf578bd7ba7c426c6fe5ca2bfbce3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-export-client-endpoint-configuration"></a><span data-ttu-id="b6f07-102">No se puede exportar la configuración de extremo de cliente</span><span class="sxs-lookup"><span data-stu-id="b6f07-102">Unable to export client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="b6f07-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b6f07-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6f07-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b6f07-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b6f07-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b6f07-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="b6f07-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b6f07-106">Event ID</span></span>|<span data-ttu-id="b6f07-107">0</span><span class="sxs-lookup"><span data-stu-id="b6f07-107">0</span></span>|  
|<span data-ttu-id="b6f07-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b6f07-108">Event Source</span></span>|<span data-ttu-id="b6f07-109">0</span><span class="sxs-lookup"><span data-stu-id="b6f07-109">0</span></span>|  
|<span data-ttu-id="b6f07-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b6f07-110">Component</span></span>|<span data-ttu-id="b6f07-111">0</span><span class="sxs-lookup"><span data-stu-id="b6f07-111">0</span></span>|  
|<span data-ttu-id="b6f07-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b6f07-112">Symbolic Name</span></span>|<span data-ttu-id="b6f07-113">0</span><span class="sxs-lookup"><span data-stu-id="b6f07-113">0</span></span>|  
|<span data-ttu-id="b6f07-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b6f07-114">Message Text</span></span>|<span data-ttu-id="b6f07-115">No se puede exportar la configuración de extremo de cliente a "{0}".</span><span class="sxs-lookup"><span data-stu-id="b6f07-115">Unable to export client endpoint configuration to "{0}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b6f07-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="b6f07-116">Explanation</span></span>  
 <span data-ttu-id="b6f07-117">Este error indica una de las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6f07-117">This error indicates one of the following:</span></span>  
  
-   <span data-ttu-id="b6f07-118">El usuario no tiene permiso para escribir en el destino.</span><span class="sxs-lookup"><span data-stu-id="b6f07-118">The user may not have permission to write to the destination.</span></span>  
  
     <span data-ttu-id="b6f07-119">\- O BIEN</span><span class="sxs-lookup"><span data-stu-id="b6f07-119">\- OR -</span></span>  
  
-   <span data-ttu-id="b6f07-120">Algunas de las propiedades necesarias no se especificaron correctamente, como **dirección (URI)** y **BindingType**.</span><span class="sxs-lookup"><span data-stu-id="b6f07-120">Some of the required properties were not correctly specified, such as **Address (URI)** and **Binding Type**.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b6f07-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b6f07-121">User Action</span></span>  
 <span data-ttu-id="b6f07-122">Utilice el procedimiento siguiente para comprobar los permisos de usuario y confirmar **dirección (URI)** y **BindingType** configuración es válida.</span><span class="sxs-lookup"><span data-stu-id="b6f07-122">Use the following procedure to verify user permissions and confirm **Address (URI)** and **Binding Type** settings are valid.</span></span>  
  
#### <a name="to-verify-user-permissions-and-confirm-settings"></a><span data-ttu-id="b6f07-123">Para comprobar los permisos del usuario y confirmar la configuración</span><span class="sxs-lookup"><span data-stu-id="b6f07-123">To verify user permissions and confirm settings</span></span>  
  
1.  <span data-ttu-id="b6f07-124">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="b6f07-124">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b6f07-125">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b6f07-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="b6f07-126">Localice la aplicación y, a continuación, el transporte.</span><span class="sxs-lookup"><span data-stu-id="b6f07-126">Locate your application, and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="b6f07-127">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="b6f07-127">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="b6f07-128">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b6f07-128">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="b6f07-129">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="b6f07-129">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="b6f07-130">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="b6f07-130">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="b6f07-131">En WCF **[***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="b6f07-131">In the WCF **[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="b6f07-132">Asegúrese de que está permitido escribir en la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="b6f07-132">Ensure writing to the destination folder is permitted.</span></span>  
  
10. <span data-ttu-id="b6f07-133">Compruebe el **comportamiento** ficha y la **identidad de extremo** configuración de **General** ficha para asegurarse de que son válidos.</span><span class="sxs-lookup"><span data-stu-id="b6f07-133">Check the **Behavior** tab and the **Endpoint Identity** settings in **General** tab to ensure they are valid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6f07-134">Debe tener permisos de escritura en la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="b6f07-134">You must have write permissions to the destination folder.</span></span> <span data-ttu-id="b6f07-135">Póngase en contacto con el administrador del equipo para obtener estos permisos.</span><span class="sxs-lookup"><span data-stu-id="b6f07-135">Contact the administrator of the machine to get these permissions.</span></span>