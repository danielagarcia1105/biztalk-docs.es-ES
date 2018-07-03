---
title: No se puede determinar el esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cc6e50b-33f5-4a88-b35d-075fdf8d79b2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6086562f593b7ca04db63b7fb41f5cf128afe9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007173"
---
# <a name="cannot-determine-scheme"></a><span data-ttu-id="3680b-102">No se puede determinar el esquema</span><span class="sxs-lookup"><span data-stu-id="3680b-102">Cannot determine scheme</span></span>
## <a name="details"></a><span data-ttu-id="3680b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3680b-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="3680b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3680b-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="3680b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3680b-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="3680b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3680b-106">Event ID</span></span>     |                                         <span data-ttu-id="3680b-107">0</span><span class="sxs-lookup"><span data-stu-id="3680b-107">0</span></span>                                          |
|  <span data-ttu-id="3680b-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3680b-108">Event Source</span></span>   |                                         <span data-ttu-id="3680b-109">0</span><span class="sxs-lookup"><span data-stu-id="3680b-109">0</span></span>                                          |
|    <span data-ttu-id="3680b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3680b-110">Component</span></span>    |                                         <span data-ttu-id="3680b-111">0</span><span class="sxs-lookup"><span data-stu-id="3680b-111">0</span></span>                                          |
|  <span data-ttu-id="3680b-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3680b-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="3680b-113">0</span><span class="sxs-lookup"><span data-stu-id="3680b-113">0</span></span>                                          |
|  <span data-ttu-id="3680b-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3680b-114">Message Text</span></span>   |                 <span data-ttu-id="3680b-115">No se puede determinar el esquema; especifique un enlace válido.</span><span class="sxs-lookup"><span data-stu-id="3680b-115">Cannot determine scheme; specify a valid binding.</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="3680b-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="3680b-116">Explanation</span></span>  
 <span data-ttu-id="3680b-117">El elemento de enlace de transporte que se ha especificado no tiene esquema.</span><span class="sxs-lookup"><span data-stu-id="3680b-117">The transport binding element that has been specified does not have a scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3680b-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3680b-118">User Action</span></span>  
 <span data-ttu-id="3680b-119">Seleccione un enlace válido y asegúrese de que el elemento de enlace de transporte tenga un esquema válido.</span><span class="sxs-lookup"><span data-stu-id="3680b-119">Select a valid binding and make sure the transport binding element has a valid scheme.</span></span> <span data-ttu-id="3680b-120">Si usa un enlace personalizado, asegúrese de que se especifique un elemento de enlace de transporte válido.</span><span class="sxs-lookup"><span data-stu-id="3680b-120">If using a custom binding, make sure a valid transport binding element is specified.</span></span>  
  
 <span data-ttu-id="3680b-121">Para obtener más información, consulte los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:</span><span class="sxs-lookup"><span data-stu-id="3680b-121">For additional information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="3680b-122">Configuración del adaptador de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="3680b-122">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)