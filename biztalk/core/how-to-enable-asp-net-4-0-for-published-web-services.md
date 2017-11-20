---
title: "Cómo habilitar ASP.NET 4.0 para publican servicios Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58646ff2-77a3-49dc-8593-f6e41d85d4f3
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e68b8eef114828ad181e83ce0c7acd70a5545e0d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-aspnet-40-for-published-web-services"></a><span data-ttu-id="07d09-102">Cómo habilitar ASP.NET 4.0 para servicios Web publicados</span><span class="sxs-lookup"><span data-stu-id="07d09-102">How to Enable ASP.NET 4.0 for Published Web Services</span></span>
<span data-ttu-id="07d09-103">Establezca la versión de ASP.Net en IIS.</span><span class="sxs-lookup"><span data-stu-id="07d09-103">Set the ASP.Net version in IIS.</span></span>

<span data-ttu-id="07d09-104">El Asistente de publicación de servicios de BizTalk Server Web se basa en la funcionalidad proporcionada con ASP.NET, que se incluye con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="07d09-104">The BizTalk Server Web Services Publishing Wizard relies on functionality provided with ASP.NET, which is included with the .NET Framework.</span></span> <span data-ttu-id="07d09-105">Las versiones de ASP.Net se incluyen con la versión de .NET CLR que elija.</span><span class="sxs-lookup"><span data-stu-id="07d09-105">The ASP.Net versions are included with the .NET CLR version you choose.</span></span> 

<span data-ttu-id="07d09-106">En este tema se muestra cómo cambiar la versión de CLR. NET.</span><span class="sxs-lookup"><span data-stu-id="07d09-106">This topic shows you how to change the .NET CLR version.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="07d09-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="07d09-107">Prerequisites</span></span>

<span data-ttu-id="07d09-108">IIS se incluye con la **servidor Web (IIS)** rol en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="07d09-108">IIS is included with the **Web Server (IIS)** role in the operating system.</span></span> <span data-ttu-id="07d09-109">Al instalar este rol, seleccione también la versión más reciente de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="07d09-109">When you install this role, also select the newer version of ASP.NET.</span></span> 
  
## <a name="update-an-application-pool"></a><span data-ttu-id="07d09-110">Actualizar un grupo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="07d09-110">Update an application pool</span></span>
  
1.  <span data-ttu-id="07d09-111">Abra **de Internet Information Services (IIS) Manager**:</span><span class="sxs-lookup"><span data-stu-id="07d09-111">Open **Internet Information Services (IIS) Manager**:</span></span>

    1. <span data-ttu-id="07d09-112">En **el administrador del servidor**, seleccione **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="07d09-112">In **Server Manager**, select **Tools**.</span></span>
    2. <span data-ttu-id="07d09-113">Seleccione **de Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="07d09-113">Select **Internet Information Services (IIS) Manager**.</span></span>
  
2.  <span data-ttu-id="07d09-114">Expanda el nombre del servidor y seleccione **grupos de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="07d09-114">Expand the server name, and select **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="07d09-115">Seleccione el grupo de aplicaciones y abra el **configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="07d09-115">Select the app pool, and open the **Basic Settings**.</span></span>  
  
4. <span data-ttu-id="07d09-116">Establecer el **versión de .NET CLR** a la versión más reciente y seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="07d09-116">Set the **.NET CLR version** to the newer version, and select **OK** to save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="07d09-117">También puede cambiar la versión en el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="07d09-117">You can also change the version in the web.config file.</span></span>
 
## <a name="allow-the-aspnet-extension"></a><span data-ttu-id="07d09-118">Permitir la extensión de ASP.Net</span><span class="sxs-lookup"><span data-stu-id="07d09-118">Allow the ASP.Net extension</span></span>
  
1.  <span data-ttu-id="07d09-119">Abra **de Internet Information Services (IIS) Manager**:</span><span class="sxs-lookup"><span data-stu-id="07d09-119">Open **Internet Information Services (IIS) Manager**:</span></span>

    1. <span data-ttu-id="07d09-120">En **el administrador del servidor**, seleccione **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="07d09-120">In **Server Manager**, select **Tools**.</span></span>
    2. <span data-ttu-id="07d09-121">Seleccione **de Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="07d09-121">Select **Internet Information Services (IIS) Manager**.</span></span>
  
2.  <span data-ttu-id="07d09-122">Seleccione el nombre del servidor y haga doble clic en **restricciones de ISAPI y CGI**.</span><span class="sxs-lookup"><span data-stu-id="07d09-122">Select the server name, and double-click **ISAPI and CGI Restrictions**.</span></span>  
  
3. <span data-ttu-id="07d09-123">Confirmar ASP.NET es **permitido** para las versiones de 32 bits y 64 bits.</span><span class="sxs-lookup"><span data-stu-id="07d09-123">Confirm ASP.NET is **Allowed** for the 32-bit and 64-bit versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d09-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="07d09-124">See Also</span></span>  
 [<span data-ttu-id="07d09-125">Planificación para publicar servicios Web</span><span class="sxs-lookup"><span data-stu-id="07d09-125">Planning for Publishing Web Services</span></span>](../core/planning-for-publishing-web-services2.md)