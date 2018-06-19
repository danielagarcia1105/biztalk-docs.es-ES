---
title: Ejemplos de adaptadores HTTP | Documentos de Microsoft
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
ms.openlocfilehash: a1111322d59f8ff5c6ba6209aa48eb515a23c72f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970986"
---
# <a name="http-adapter-samples"></a><span data-ttu-id="8cf25-102">Ejemplos de adaptadores de HTTP</span><span class="sxs-lookup"><span data-stu-id="8cf25-102">HTTP Adapter Samples</span></span>
<span data-ttu-id="8cf25-103">Esta sección contiene ejemplos que muestran la funcionalidad avanzada para configurar el adaptador de HTTP de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8cf25-103">This section contains samples that illustrate advanced functionality when using the BizTalk HTTP Adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cf25-104">Antes de ejecutar este ejemplo, lleve a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8cf25-104">Before running this sample, you need to do the following steps:</span></span>  
>   
>  1.  <span data-ttu-id="8cf25-105">Abra IIS y agregue restricciones de ISAPI y CGI:</span><span class="sxs-lookup"><span data-stu-id="8cf25-105">Open IIS, add ISAPI and CGI restrictions:</span></span>  
>   
>      <span data-ttu-id="8cf25-106">Haga clic en el nombre del equipo en el panel izquierdo, haga clic en "Restricciones de ISAPI y CGI" en el panel derecho y, a continuación, agregue la ruta de acceso de ISAPI o CGI:</span><span class="sxs-lookup"><span data-stu-id="8cf25-106">Click Machine Name on left panel, then click "ISAPI and CGI restrictions" on the right panel, then Add the ISAPI or CGI path:</span></span>  
>   
>      <span data-ttu-id="8cf25-107">En un equipo de 64 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive64\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="8cf25-107">On a 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\BTSHTTPReceive.dll</span></span>  
>   
>      <span data-ttu-id="8cf25-108">En un equipo de 32 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="8cf25-108">On a 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHTTPReceive.dll</span></span>  
>   
>      <span data-ttu-id="8cf25-109">Marque la casilla Permitir ejecución de la ruta de extensión.</span><span class="sxs-lookup"><span data-stu-id="8cf25-109">Check allowed extension path or execute.</span></span>  
> 2.  <span data-ttu-id="8cf25-110">Haga clic en "HTTPRequestResponseSample" en panel izquierdo, haga clic en "Asignaciones de controlador" en el panel central y, a continuación, haga clic en "Agregar asignación de script" con el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="8cf25-110">Click "HTTPRequestResponseSample" on left panel, then click "Handler Mapping" on middle panel, then click "Add script mapping” with the following setting:</span></span>  
>   
>      <span data-ttu-id="8cf25-111">Ruta de acceso de solicitudes:BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="8cf25-111">Request path:BTSHTTPReceive.dll</span></span>  
>   
>      <span data-ttu-id="8cf25-112">Ejecutable:</span><span class="sxs-lookup"><span data-stu-id="8cf25-112">Executable:</span></span>  
>   
>      <span data-ttu-id="8cf25-113">En el equipo de 64 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive64\\</span><span class="sxs-lookup"><span data-stu-id="8cf25-113">On 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\\</span></span>  
>   
>      <span data-ttu-id="8cf25-114">En el equipo de 32 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive\\</span><span class="sxs-lookup"><span data-stu-id="8cf25-114">On 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\\</span></span>  
>   
>      <span data-ttu-id="8cf25-115">Restricciones de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="8cf25-115">Request restrictions:</span></span>  
>   
>      <span data-ttu-id="8cf25-116">Verbos: POST</span><span class="sxs-lookup"><span data-stu-id="8cf25-116">Verbs: POST</span></span>  
>   
>      <span data-ttu-id="8cf25-117">Acceso: Script</span><span class="sxs-lookup"><span data-stu-id="8cf25-117">Access: Script</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8cf25-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8cf25-118">In This Section</span></span>  
  
-   [<span data-ttu-id="8cf25-119">HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="8cf25-119">HTTPSolicitResponse</span></span>](../core/httpsolicitresponse.md)  
  
-   [<span data-ttu-id="8cf25-120">HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="8cf25-120">HTTPRequestResponse</span></span>](../core/httprequestresponse.md)