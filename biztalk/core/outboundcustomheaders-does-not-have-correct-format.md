---
title: OutboundCustomHeaders no tiene el formato correcto | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6097762b-01c9-48b8-8cee-ccd6b11d28d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d9cb9311015bfa7d88169944a206a8882b11cfe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008925"
---
# <a name="outboundcustomheaders-does-not-have-correct-format"></a><span data-ttu-id="110df-102">OutboundCustomHeaders no tiene el formato correcto</span><span class="sxs-lookup"><span data-stu-id="110df-102">OutboundCustomHeaders does not have correct format</span></span>
## <a name="details"></a><span data-ttu-id="110df-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="110df-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="110df-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="110df-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="110df-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="110df-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="110df-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="110df-106">Event ID</span></span>     |                                         <span data-ttu-id="110df-107">0</span><span class="sxs-lookup"><span data-stu-id="110df-107">0</span></span>                                          |
|  <span data-ttu-id="110df-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="110df-108">Event Source</span></span>   |                                         <span data-ttu-id="110df-109">0</span><span class="sxs-lookup"><span data-stu-id="110df-109">0</span></span>                                          |
|    <span data-ttu-id="110df-110">Componente</span><span class="sxs-lookup"><span data-stu-id="110df-110">Component</span></span>    |                                         <span data-ttu-id="110df-111">0</span><span class="sxs-lookup"><span data-stu-id="110df-111">0</span></span>                                          |
|  <span data-ttu-id="110df-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="110df-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="110df-113">0</span><span class="sxs-lookup"><span data-stu-id="110df-113">0</span></span>                                          |
|  <span data-ttu-id="110df-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="110df-114">Message Text</span></span>   |                <span data-ttu-id="110df-115">OutboundCustomHeaders no tiene un formato correcto.</span><span class="sxs-lookup"><span data-stu-id="110df-115">OutboundCustomHeaders does not have a correct format</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="110df-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="110df-116">Explanation</span></span>  
 <span data-ttu-id="110df-117">El valor de WCF. InboundHeaders o WCF. OutboundCustomHeaders no tiene el formato siguiente: \<encabezados\>...\</headers\>.</span><span class="sxs-lookup"><span data-stu-id="110df-117">The value of WCF.InboundHeaders or WCF.OutboundCustomHeaders  is not in the following format: \<headers\>….\</headers\>.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="110df-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="110df-118">User Action</span></span>  
 <span data-ttu-id="110df-119">Ajustar los valores de propiedad con \<encabezados\> elemento.</span><span class="sxs-lookup"><span data-stu-id="110df-119">Wrap the property values with \<headers\> element.</span></span>  
  
 <span data-ttu-id="110df-120">Para obtener más información, vea el recurso siguiente en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="110df-120">For further information, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="110df-121">Uso de encabezados SOAP en mensajes WCF con componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="110df-121">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)