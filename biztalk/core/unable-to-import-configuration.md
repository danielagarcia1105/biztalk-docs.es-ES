---
title: No se puede importar la configuración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2887da50-4f74-4259-a7d6-c87bc9b9fc58
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e565b466e4f9ce8af3745948952b4318a029ff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286684"
---
# <a name="unable-to-import-configuration"></a><span data-ttu-id="66387-102">No se pudo importar la configuración</span><span class="sxs-lookup"><span data-stu-id="66387-102">Unable to import configuration</span></span>
## <a name="details"></a><span data-ttu-id="66387-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="66387-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66387-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="66387-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="66387-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="66387-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="66387-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="66387-106">Event ID</span></span>|<span data-ttu-id="66387-107">0</span><span class="sxs-lookup"><span data-stu-id="66387-107">0</span></span>|  
|<span data-ttu-id="66387-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="66387-108">Event Source</span></span>|<span data-ttu-id="66387-109">0</span><span class="sxs-lookup"><span data-stu-id="66387-109">0</span></span>|  
|<span data-ttu-id="66387-110">Componente</span><span class="sxs-lookup"><span data-stu-id="66387-110">Component</span></span>|<span data-ttu-id="66387-111">0</span><span class="sxs-lookup"><span data-stu-id="66387-111">0</span></span>|  
|<span data-ttu-id="66387-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="66387-112">Symbolic Name</span></span>|<span data-ttu-id="66387-113">0</span><span class="sxs-lookup"><span data-stu-id="66387-113">0</span></span>|  
|<span data-ttu-id="66387-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="66387-114">Message Text</span></span>|<span data-ttu-id="66387-115">No se puede importar la configuración del archivo "{0}".</span><span class="sxs-lookup"><span data-stu-id="66387-115">Unable to import configuration from file "{0}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="66387-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="66387-116">Explanation</span></span>  
 <span data-ttu-id="66387-117">Podrían haber varias razones para este error:</span><span class="sxs-lookup"><span data-stu-id="66387-117">There could be multiple reasons for this error:</span></span>  
  
-   <span data-ttu-id="66387-118">Es posible que el archivo de configuración contega un carácter no válido en la codificación.</span><span class="sxs-lookup"><span data-stu-id="66387-118">The configuration file may contain invalid character in the given encoding.</span></span>  
  
-   <span data-ttu-id="66387-119">Es posible que falte el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="66387-119">The root element may be missing.</span></span>  
  
-   <span data-ttu-id="66387-120">Es posible que los datos en el nivel de raíz no sean válidos.</span><span class="sxs-lookup"><span data-stu-id="66387-120">The data at the root level may be invalid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66387-121">Esta situación y la acción del usuario solo se aplican a los adaptadores de WCF-Custom y WCF-CustomIsolate.</span><span class="sxs-lookup"><span data-stu-id="66387-121">This situation, and the user action, applies only to WCF-Custom and WCF-CustomIsolate adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66387-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="66387-122">User Action</span></span>  
 <span data-ttu-id="66387-123">Use el procedimiento siguiente para importar un archivo de configuración válido.</span><span class="sxs-lookup"><span data-stu-id="66387-123">Use the following procedure to import a valid configuration file.</span></span>  
  
#### <a name="to-import-a-valid-configuration-file"></a><span data-ttu-id="66387-124">Para importar un archivo de configuración válido</span><span class="sxs-lookup"><span data-stu-id="66387-124">To import a valid configuration file</span></span>  
  
1.  <span data-ttu-id="66387-125">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="66387-125">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="66387-126">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="66387-126">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="66387-127">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="66387-127">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="66387-128">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="66387-128">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="66387-129">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="66387-129">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="66387-130">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="66387-130">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="66387-131">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="66387-131">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="66387-132">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **importación/exportación** ficha.</span><span class="sxs-lookup"><span data-stu-id="66387-132">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Import/Export** tab.</span></span>  
  
9. <span data-ttu-id="66387-133">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="66387-133">Click **Import**.</span></span> <span data-ttu-id="66387-134">Importe un archivo de configuración válido y completo.</span><span class="sxs-lookup"><span data-stu-id="66387-134">Import a valid and complete configuration file.</span></span>  
  
 <span data-ttu-id="66387-135">También puede comprobar la validez del archivo de configuración, ábralo con el Editor de configuración de servicio **(Inicio > todos los programas > SDK de Windows)** (en este paso se asume que tiene instalado el SDK de Windows.) Abra **svcConfigEditor.exe** y compruebe todas las propiedades del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="66387-135">You can also verify the validity of the configuration file by opening it with the Service Configuration Editor **(Start > All Programs > Windows SDK)** (this step assumes you have the Windows SDK installed.) Open **svcConfigEditor.exe** and verify each property of the configuration file.</span></span>