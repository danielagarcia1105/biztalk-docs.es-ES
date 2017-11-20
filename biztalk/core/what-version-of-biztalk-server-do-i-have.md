---
title: "¿Qué versión de BizTalk Server tengo? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb651202-f682-4e5f-8a79-221877af20a7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce5508a3b7c78e52fe5fcbef40e351dce58f2816
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-version-of-biztalk-server-do-i-have"></a><span data-ttu-id="bbd55-103">¿Qué versión de BizTalk Server tengo?</span><span class="sxs-lookup"><span data-stu-id="bbd55-103">What Version of BizTalk Server Do I Have?</span></span>
<span data-ttu-id="bbd55-104">Puede que esté ejecutando diferentes versiones y ediciones diferentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbd55-104">You may be running different versions and different editions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="bbd55-105">Este tema muestra cómo determinar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] información sobre la instalación, incluida la ruta de instalación, edición y número de versión.</span><span class="sxs-lookup"><span data-stu-id="bbd55-105">This topic shows you how to determine [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation information, including the version number, edition, and installation path.</span></span>  
  
## <a name="use-the-registry"></a><span data-ttu-id="bbd55-106">Utilice el registro</span><span class="sxs-lookup"><span data-stu-id="bbd55-106">Use the registry</span></span>
  
1.  <span data-ttu-id="bbd55-107">Seleccione **iniciar**, tipo `regedt32`y, a continuación, vuelva a abrirlo.</span><span class="sxs-lookup"><span data-stu-id="bbd55-107">Select **Start**, type `regedt32`, and then open it.</span></span>  
  
2.  <span data-ttu-id="bbd55-108">Expanda **HKEY_LOCAL_MACHINE**, expanda **SOFTWARE**, expanda **Microsoft**, expanda **BizTalk Server**y, a continuación, seleccione **3.0**.</span><span class="sxs-lookup"><span data-stu-id="bbd55-108">Expand **HKEY_LOCAL_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, expand **BizTalk Server**, and then select **3.0**.</span></span>  
  
3.  <span data-ttu-id="bbd55-109">El panel de la derecha muestra la información de instalación, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbd55-109">The right pane displays installation information, including:</span></span>  
  
    |<span data-ttu-id="bbd55-110">Subclave</span><span class="sxs-lookup"><span data-stu-id="bbd55-110">Sub-key</span></span>|<span data-ttu-id="bbd55-111">Description</span><span class="sxs-lookup"><span data-stu-id="bbd55-111">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="bbd55-112">**Rutadeinstalación**</span><span class="sxs-lookup"><span data-stu-id="bbd55-112">**InstallPath**</span></span>|<span data-ttu-id="bbd55-113">Indica la ruta de instalación en que se instaló [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbd55-113">Lists the installation path where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
    |<span data-ttu-id="bbd55-114">**ProductEdition**</span><span class="sxs-lookup"><span data-stu-id="bbd55-114">**ProductEdition**</span></span>|<span data-ttu-id="bbd55-115">Indica la edición, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbd55-115">Lists the edition, including:</span></span><br /><br /> <span data-ttu-id="bbd55-116">-Para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="bbd55-116">-   Developer</span></span><br /><span data-ttu-id="bbd55-117">-Bifurcación</span><span class="sxs-lookup"><span data-stu-id="bbd55-117">-   Branch</span></span><br /><span data-ttu-id="bbd55-118">-Estándar</span><span class="sxs-lookup"><span data-stu-id="bbd55-118">-   Standard</span></span><br /><span data-ttu-id="bbd55-119">-Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbd55-119">-   Enterprise</span></span>|  
    |<span data-ttu-id="bbd55-120">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="bbd55-120">**ProductVersion**</span></span>|<span data-ttu-id="bbd55-121">Indica la versión base del producto.</span><span class="sxs-lookup"><span data-stu-id="bbd55-121">Lists the base product version.</span></span> <span data-ttu-id="bbd55-122">Para la versión específica del producto, incluidos los service packs y actualizaciones acumulativas, consulte [versiones BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbd55-122">For specific product version, including service packs and cumulative updates, see [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span>|  

## <a name="use-the-control-panel"></a><span data-ttu-id="bbd55-123">Use el panel de control</span><span class="sxs-lookup"><span data-stu-id="bbd55-123">Use the control panel</span></span>

1.  <span data-ttu-id="bbd55-124">Seleccione **iniciar**, tipo `Programs and Features`y, a continuación, vuelva a abrirlo.</span><span class="sxs-lookup"><span data-stu-id="bbd55-124">Select **Start**, type `Programs and Features`, and then open it.</span></span>  

2. <span data-ttu-id="bbd55-125">En la lista, seleccione **Microsoft BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="bbd55-125">In the list, select **Microsoft BizTalk Server**.</span></span> <span data-ttu-id="bbd55-126">Se muestran la versión y edición.</span><span class="sxs-lookup"><span data-stu-id="bbd55-126">The version and edition are listed.</span></span>

<span data-ttu-id="bbd55-127">Vea [versiones BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbd55-127">See [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbd55-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbd55-128">See Also</span></span>  
 [<span data-ttu-id="bbd55-129">Introducción</span><span class="sxs-lookup"><span data-stu-id="bbd55-129">Get started</span></span>](../core/getting-started-with-biztalk-server.md)