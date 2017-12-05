---
title: No se especifica el elemento de cuerpo de mensaje de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af5d63c0-af96-4e34-828f-d29638cdf46d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0656cf14e1c2a16d6d53966e316550020c8cd0af
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="biztalk-message-body-element-not-specified"></a><span data-ttu-id="bd002-102">Elemento de cuerpo de mensaje de BizTalk no especificado.</span><span class="sxs-lookup"><span data-stu-id="bd002-102">BizTalk message body element not specified</span></span>
## <a name="details"></a><span data-ttu-id="bd002-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="bd002-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd002-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="bd002-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="bd002-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="bd002-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="bd002-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="bd002-106">Event ID</span></span>|<span data-ttu-id="bd002-107">0</span><span class="sxs-lookup"><span data-stu-id="bd002-107">0</span></span>|  
|<span data-ttu-id="bd002-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="bd002-108">Event Source</span></span>|<span data-ttu-id="bd002-109">0</span><span class="sxs-lookup"><span data-stu-id="bd002-109">0</span></span>|  
|<span data-ttu-id="bd002-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bd002-110">Component</span></span>|<span data-ttu-id="bd002-111">0</span><span class="sxs-lookup"><span data-stu-id="bd002-111">0</span></span>|  
|<span data-ttu-id="bd002-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bd002-112">Symbolic Name</span></span>|<span data-ttu-id="bd002-113">0</span><span class="sxs-lookup"><span data-stu-id="bd002-113">0</span></span>|  
|<span data-ttu-id="bd002-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bd002-114">Message Text</span></span>|<span data-ttu-id="bd002-115">Elemento de cuerpo de mensaje de BizTalk no especificado.</span><span class="sxs-lookup"><span data-stu-id="bd002-115">BizTalk message body element not specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd002-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="bd002-116">Explanation</span></span>  
 <span data-ttu-id="bd002-117">Este error indica el uso de la opción de plantilla para el mensaje saliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="bd002-117">This error indicates the use of the template option for the outbound WCF message.</span></span> <span data-ttu-id="bd002-118">Sin embargo, la expresión de plantilla no contiene el elemento de cuerpo de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bd002-118">However, the template expression doesn’t contain the BizTalk message body element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd002-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bd002-119">User Action</span></span>  
 <span data-ttu-id="bd002-120">Asegúrese de que la expresión de plantilla contiene el siguiente elemento: \< **bts-msg-body xmlns = "http://www.microsoft.com/schemas/bts2007" encoding = "[xml &#124; base64 &#124; hex &#124; cadena]" /** \>.</span><span class="sxs-lookup"><span data-stu-id="bd002-120">Ensure that the template expression contains the following element: \<**bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>.</span></span>