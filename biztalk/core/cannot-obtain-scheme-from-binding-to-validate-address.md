---
title: No se puede obtener el esquema del enlace para validar la dirección | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b002084a-63ae-4685-8ce3-88cc6489e19e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2032decfdf59ae175f3ee8fc686341c8a4061fc6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991341"
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a><span data-ttu-id="87b1d-102">No se puede obtener el esquema del enlace para validar la dirección</span><span class="sxs-lookup"><span data-stu-id="87b1d-102">Cannot obtain scheme from binding to validate address</span></span>
## <a name="details"></a><span data-ttu-id="87b1d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="87b1d-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="87b1d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="87b1d-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="87b1d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="87b1d-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="87b1d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="87b1d-106">Event ID</span></span>     |                                         <span data-ttu-id="87b1d-107">0</span><span class="sxs-lookup"><span data-stu-id="87b1d-107">0</span></span>                                          |
|  <span data-ttu-id="87b1d-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="87b1d-108">Event Source</span></span>   |                                         <span data-ttu-id="87b1d-109">0</span><span class="sxs-lookup"><span data-stu-id="87b1d-109">0</span></span>                                          |
|    <span data-ttu-id="87b1d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="87b1d-110">Component</span></span>    |                                         <span data-ttu-id="87b1d-111">0</span><span class="sxs-lookup"><span data-stu-id="87b1d-111">0</span></span>                                          |
|  <span data-ttu-id="87b1d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="87b1d-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="87b1d-113">0</span><span class="sxs-lookup"><span data-stu-id="87b1d-113">0</span></span>                                          |
|  <span data-ttu-id="87b1d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="87b1d-114">Message Text</span></span>   |               <span data-ttu-id="87b1d-115">No se puede obtener el esquema del enlace para validar la dirección.</span><span class="sxs-lookup"><span data-stu-id="87b1d-115">Cannot obtain scheme from binding to validate address.</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="87b1d-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="87b1d-116">Explanation</span></span>  
 <span data-ttu-id="87b1d-117">El elemento de enlace de transporte que se ha especificado no tiene esquema.</span><span class="sxs-lookup"><span data-stu-id="87b1d-117">The transport binding element that has been specified does not have a scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87b1d-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="87b1d-118">User Action</span></span>  
 <span data-ttu-id="87b1d-119">Asegúrese de que el elemento de enlace de transporte tiene un esquema válido, o que esté seleccionado un elemento de enlace de transporte válido.</span><span class="sxs-lookup"><span data-stu-id="87b1d-119">Make sure that the transport binding element has a valid scheme, or that a valid transport binding element is selected.</span></span> <span data-ttu-id="87b1d-120">Si usa un enlace personalizado, asegúrese de que se especifique un elemento de enlace de transporte válido.</span><span class="sxs-lookup"><span data-stu-id="87b1d-120">If using a custom binding, make sure a valid transport binding element is specified.</span></span>  
  
 <span data-ttu-id="87b1d-121">Para obtener más información, consulte los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:</span><span class="sxs-lookup"><span data-stu-id="87b1d-121">For additional information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="87b1d-122">Configuración del adaptador de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="87b1d-122">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)