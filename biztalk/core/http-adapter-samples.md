---
title: Ejemplos de adaptadores de HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 6796ea39-2947-45df-b228-1ecdb23a7ab8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7682a16bd298ed58cf55e5122603bb2b3af9003
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977973"
---
# <a name="http-adapter-samples"></a><span data-ttu-id="e3e6c-102">Ejemplos de adaptadores de HTTP</span><span class="sxs-lookup"><span data-stu-id="e3e6c-102">HTTP Adapter Samples</span></span>
<span data-ttu-id="e3e6c-103">Esta sección contiene ejemplos que muestran la funcionalidad avanzada para configurar el adaptador de HTTP de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-103">This section contains samples that illustrate advanced functionality when using the BizTalk HTTP Adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3e6c-104">Antes de ejecutar este ejemplo, lleve a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-104">Before running this sample, you need to do the following steps:</span></span>  
> 
> 1. <span data-ttu-id="e3e6c-105">Abra IIS y agregue restricciones de ISAPI y CGI:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-105">Open IIS, add ISAPI and CGI restrictions:</span></span>  
> 
>    <span data-ttu-id="e3e6c-106">Haga clic en el nombre del equipo en el panel izquierdo, haga clic en "Restricciones de ISAPI y CGI" en el panel derecho y, a continuación, agregue la ruta de acceso de ISAPI o CGI:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-106">Click Machine Name on left panel, then click "ISAPI and CGI restrictions" on the right panel, then Add the ISAPI or CGI path:</span></span>  
> 
>    <span data-ttu-id="e3e6c-107">En un equipo de 64 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive64\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="e3e6c-107">On a 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\BTSHTTPReceive.dll</span></span>  
> 
>    <span data-ttu-id="e3e6c-108">En un equipo de 32 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="e3e6c-108">On a 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHTTPReceive.dll</span></span>  
> 
>    <span data-ttu-id="e3e6c-109">Marque la casilla Permitir ejecución de la ruta de extensión.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-109">Check allowed extension path or execute.</span></span>  
>    2.  <span data-ttu-id="e3e6c-110">Haga clic en "HTTPRequestResponseSample" en panel izquierdo, haga clic en "Asignaciones de controlador" en el panel central y, a continuación, haga clic en "Agregar asignación de script" con el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-110">Click "HTTPRequestResponseSample" on left panel, then click "Handler Mapping" on middle panel, then click "Add script mapping” with the following setting:</span></span>  
> 
>    <span data-ttu-id="e3e6c-111">Ruta de acceso de solicitudes:BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="e3e6c-111">Request path:BTSHTTPReceive.dll</span></span>  
> 
>    <span data-ttu-id="e3e6c-112">Ejecutable:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-112">Executable:</span></span>  
> 
>    <span data-ttu-id="e3e6c-113">En el equipo de 64 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive64\\</span><span class="sxs-lookup"><span data-stu-id="e3e6c-113">On 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\\</span></span>  
> 
>    <span data-ttu-id="e3e6c-114">En el equipo de 32 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive\\</span><span class="sxs-lookup"><span data-stu-id="e3e6c-114">On 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\\</span></span>  
> 
>    <span data-ttu-id="e3e6c-115">Restricciones de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-115">Request restrictions:</span></span>  
> 
>    <span data-ttu-id="e3e6c-116">Verbos: POST</span><span class="sxs-lookup"><span data-stu-id="e3e6c-116">Verbs: POST</span></span>  
> 
>    <span data-ttu-id="e3e6c-117">Acceso: Script</span><span class="sxs-lookup"><span data-stu-id="e3e6c-117">Access: Script</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3e6c-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e3e6c-118">In This Section</span></span>  
  
-   [<span data-ttu-id="e3e6c-119">HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="e3e6c-119">HTTPSolicitResponse</span></span>](../core/httpsolicitresponse.md)  
  
-   [<span data-ttu-id="e3e6c-120">HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="e3e6c-120">HTTPRequestResponse</span></span>](../core/httprequestresponse.md)