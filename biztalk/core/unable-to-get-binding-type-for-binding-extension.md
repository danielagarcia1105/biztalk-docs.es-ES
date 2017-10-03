---
title: "No se puede obtener el tipo de enlace de extensión de enlace | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 453a579daae80a202df1ed4d3c72ae9c13f47d9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a><span data-ttu-id="ad81a-102">No se puede obtener el tipo de enlace para la extensión de enlace</span><span class="sxs-lookup"><span data-stu-id="ad81a-102">Unable to get binding type for binding extension</span></span>
## <a name="details"></a><span data-ttu-id="ad81a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ad81a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad81a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ad81a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ad81a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ad81a-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="ad81a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ad81a-106">Event ID</span></span>|<span data-ttu-id="ad81a-107">0</span><span class="sxs-lookup"><span data-stu-id="ad81a-107">0</span></span>|  
|<span data-ttu-id="ad81a-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ad81a-108">Event Source</span></span>|<span data-ttu-id="ad81a-109">0</span><span class="sxs-lookup"><span data-stu-id="ad81a-109">0</span></span>|  
|<span data-ttu-id="ad81a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ad81a-110">Component</span></span>|<span data-ttu-id="ad81a-111">0</span><span class="sxs-lookup"><span data-stu-id="ad81a-111">0</span></span>|  
|<span data-ttu-id="ad81a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ad81a-112">Symbolic Name</span></span>|<span data-ttu-id="ad81a-113">0</span><span class="sxs-lookup"><span data-stu-id="ad81a-113">0</span></span>|  
|<span data-ttu-id="ad81a-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ad81a-114">Message Text</span></span>|<span data-ttu-id="ad81a-115">No se puede obtener el tipo de enlace para la extensión de enlace "{0}".</span><span class="sxs-lookup"><span data-stu-id="ad81a-115">Unable to get binding type for binding extension "{0}".</span></span> <span data-ttu-id="ad81a-116">Si machine.config se actualizó mientras estaba abierta la aplicación, reinicie la aplicación para que se apliquen los cambios.</span><span class="sxs-lookup"><span data-stu-id="ad81a-116">If machine.config was updated while your application was open, restart your application to pick up changes.</span></span> <span data-ttu-id="ad81a-117">Compruebe que la extensión de enlace está registrada en machine.config.</span><span class="sxs-lookup"><span data-stu-id="ad81a-117">Verify the binding extension is registered in machine.config</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad81a-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="ad81a-118">Explanation</span></span>  
 <span data-ttu-id="ad81a-119">Una extensión de enlace personalizado para un transporte WCF-Custom o WCF-CustomIsolated no se configuró correctamente.</span><span class="sxs-lookup"><span data-stu-id="ad81a-119">A custom binding extension for a WCF-Custom or a WCF-CustomIsolated transport was not configured properly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad81a-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ad81a-120">User Action</span></span>  
 <span data-ttu-id="ad81a-121">Par resolver este error, realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad81a-121">To resolve this error do one or more of the following:</span></span>  
  
-   <span data-ttu-id="ad81a-122">Asegúrese del **archivo.config** en **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config** tiene la \< **bindingExtensions**> elemento ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ad81a-122">Ensure the **machine.config file** in **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config** has the \<**bindingExtensions**> element configured properly.</span></span>  
  
-   <span data-ttu-id="ad81a-123">En el Explorador de Windows, vaya a **%WinDir%\Assembly**y asegúrese de que los ensamblados que implementan la extensión de enlace personalizada están instalados correctamente.</span><span class="sxs-lookup"><span data-stu-id="ad81a-123">In Windows Explorer, go to **%WinDir%\Assembly**, and make sure the assemblies implementing the custom binding extension are installed properly.</span></span>  
  
-   <span data-ttu-id="ad81a-124">Para el adaptador de WCF-Custom, en la consola de administración de BizTalk, reinicie la instancia de host que ejecuta el transporte WCF.</span><span class="sxs-lookup"><span data-stu-id="ad81a-124">For the WCF-Custom adapter, in the BizTalk Administration console, restart the host instance running the WCF transport.</span></span>  
  
-   <span data-ttu-id="ad81a-125">Para el adaptador de WCF-CustomIsolated, en la consola de administración de IIS, reinicie el grupo de aplicaciones que hospeda el transporte WCF.</span><span class="sxs-lookup"><span data-stu-id="ad81a-125">For the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool hosting the WCF transport.</span></span>  
  
-   <span data-ttu-id="ad81a-126">Abra y cierre la consola de administración de BizTalk si estaba abierta.</span><span class="sxs-lookup"><span data-stu-id="ad81a-126">Open and close the BizTalk Administration console if it was opened</span></span>  
  
 <span data-ttu-id="ad81a-127">Para obtener más información, vea el recurso siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad81a-127">For further information, see the following resource:</span></span>  
  
-   [<span data-ttu-id="ad81a-128">Cómo habilitar los puntos de extensibilidad de WCF con los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="ad81a-128">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)