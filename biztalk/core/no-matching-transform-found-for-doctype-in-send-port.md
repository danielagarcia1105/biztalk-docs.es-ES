---
title: "Se encontró ninguna transformación coincidente para DocType en puerto de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23f62ac7-3849-49fe-a765-2be72880a4c9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bc45ac0edf425bc19ab526fac6b2690f3a6b6d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a><span data-ttu-id="7c75c-102">No se ha encontrado ninguna transformación coincidente para DocType en Puerto de envío</span><span class="sxs-lookup"><span data-stu-id="7c75c-102">No matching transform found for DocType in Send Port</span></span>
## <a name="details"></a><span data-ttu-id="7c75c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7c75c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c75c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7c75c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7c75c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7c75c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7c75c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7c75c-106">Event ID</span></span>|-|  
|<span data-ttu-id="7c75c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7c75c-107">Event Source</span></span>|<span data-ttu-id="7c75c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c75c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="7c75c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7c75c-109">Component</span></span>|<span data-ttu-id="7c75c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="7c75c-110">EDI Engine</span></span>|  
|<span data-ttu-id="7c75c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7c75c-111">Symbolic Name</span></span>|<span data-ttu-id="7c75c-112">NoMatchingTransformFoundForSendPortAndDocType</span><span class="sxs-lookup"><span data-stu-id="7c75c-112">NoMatchingTransformFoundForSendPortAndDocType</span></span>|  
|<span data-ttu-id="7c75c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7c75c-113">Message Text</span></span>|<span data-ttu-id="7c75c-114">Ninguna transformación coincidente que encuentra para DocType {0} en {1} del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7c75c-114">No matching transform found for DocType {0} in Send Port {1}.</span></span> <span data-ttu-id="7c75c-115">Incoherente con la información de ExplorerOM</span><span class="sxs-lookup"><span data-stu-id="7c75c-115">Inconsistent with ExplorerOM information</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7c75c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="7c75c-116">Explanation</span></span>  
 <span data-ttu-id="7c75c-117">Este error indica que no se encontró ninguna transformación coincidente para un DocType y Puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7c75c-117">This error indicates that a matching transform was not found for a given DocType and SendPort.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c75c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7c75c-118">User Action</span></span>  
 <span data-ttu-id="7c75c-119">Para resolver este error, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c75c-119">To resolve this error, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="7c75c-120">Abra la consola de administración de BizTalk, localice el transporte y haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="7c75c-120">Open the BizTalk Administration console, locate the transport, and right-click the transport name.</span></span>  
  
2.  <span data-ttu-id="7c75c-121">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7c75c-121">Click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7c75c-122">En la lista Tipo de puerto, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="7c75c-122">In the port Type list, select the correct port.</span></span> <span data-ttu-id="7c75c-123">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7c75c-123">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="7c75c-124">En el cuadro de diálogo Propiedades de puerto de envío de [nombre de puerto], haga clic en **asignaciones de salida** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="7c75c-124">In the [port name] Send Port Properties dialog box, click **Outbound Maps** in the left pane.</span></span>  
  
5.  <span data-ttu-id="7c75c-125">Compruebe que aquí aparece la asignación y que corresponde con el tipo de documento correcto.</span><span class="sxs-lookup"><span data-stu-id="7c75c-125">Verify that the map is listed here and that it corresponds to the correct document type.</span></span>