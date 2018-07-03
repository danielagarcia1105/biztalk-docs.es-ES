---
title: Se encontró ninguna transformación coincidente para DocType en puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23f62ac7-3849-49fe-a765-2be72880a4c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9668694f5cde2e99775d1392c8722bad0645b251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966213"
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a><span data-ttu-id="95824-102">No se ha encontrado ninguna transformación coincidente para DocType en Puerto de envío</span><span class="sxs-lookup"><span data-stu-id="95824-102">No matching transform found for DocType in Send Port</span></span>
## <a name="details"></a><span data-ttu-id="95824-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="95824-103">Details</span></span>  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="95824-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="95824-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| <span data-ttu-id="95824-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="95824-105">Product Version</span></span> |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    <span data-ttu-id="95824-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="95824-106">Event ID</span></span>     |                                                   -                                                    |
|  <span data-ttu-id="95824-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="95824-107">Event Source</span></span>   |         <span data-ttu-id="95824-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95824-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>         |
|    <span data-ttu-id="95824-109">Componente</span><span class="sxs-lookup"><span data-stu-id="95824-109">Component</span></span>    |                                               <span data-ttu-id="95824-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="95824-110">EDI Engine</span></span>                                               |
|  <span data-ttu-id="95824-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="95824-111">Symbolic Name</span></span>  |                             <span data-ttu-id="95824-112">NoMatchingTransformFoundForSendPortAndDocType</span><span class="sxs-lookup"><span data-stu-id="95824-112">NoMatchingTransformFoundForSendPortAndDocType</span></span>                              |
|  <span data-ttu-id="95824-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="95824-113">Message Text</span></span>   | <span data-ttu-id="95824-114">Se encontró ninguna transformación coincidente para DocType {0} en el puerto de envío {1}.</span><span class="sxs-lookup"><span data-stu-id="95824-114">No matching transform found for DocType {0} in Send Port {1}.</span></span> <span data-ttu-id="95824-115">Incoherente con la información de ExplorerOM</span><span class="sxs-lookup"><span data-stu-id="95824-115">Inconsistent with ExplorerOM information</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="95824-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="95824-116">Explanation</span></span>  
 <span data-ttu-id="95824-117">Este error indica que no se encontró ninguna transformación coincidente para un DocType y Puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="95824-117">This error indicates that a matching transform was not found for a given DocType and SendPort.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95824-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="95824-118">User Action</span></span>  
 <span data-ttu-id="95824-119">Para resolver este error, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95824-119">To resolve this error, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="95824-120">Abra la consola de administración de BizTalk, localice el transporte y haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="95824-120">Open the BizTalk Administration console, locate the transport, and right-click the transport name.</span></span>  
  
2.  <span data-ttu-id="95824-121">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="95824-121">Click **Properties**.</span></span>  
  
3.  <span data-ttu-id="95824-122">En la lista Tipo de puerto, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="95824-122">In the port Type list, select the correct port.</span></span> <span data-ttu-id="95824-123">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="95824-123">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="95824-124">En el cuadro de diálogo Propiedades de puerto de envío de [nombre de puerto], haga clic en **asignaciones de salida** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="95824-124">In the [port name] Send Port Properties dialog box, click **Outbound Maps** in the left pane.</span></span>  
  
5.  <span data-ttu-id="95824-125">Compruebe que aquí aparece la asignación y que corresponde con el tipo de documento correcto.</span><span class="sxs-lookup"><span data-stu-id="95824-125">Verify that the map is listed here and that it corresponds to the correct document type.</span></span>