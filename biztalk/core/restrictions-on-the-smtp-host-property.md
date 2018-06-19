---
title: Restricciones de la propiedad de Host SMTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: 6dbdb6dc-0062-4444-a4c8-6e2a7900f533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 465946f15d11f087995b8000231796c5e204c077
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972906"
---
# <a name="restrictions-on-the-smtp-host-property"></a><span data-ttu-id="90d2d-102">Restricciones de la propiedad de Host de SMTP</span><span class="sxs-lookup"><span data-stu-id="90d2d-102">Restrictions on the SMTP Host Property</span></span>
<span data-ttu-id="90d2d-103">La propiedad de host SMTP es una cadena que especifica el servidor SMTP que usará el adaptador de SMTP para enviar mensajes desde el servidor BizTalk.</span><span class="sxs-lookup"><span data-stu-id="90d2d-103">The SMTP host property is a string that specifies the SMTP server that the SMTP adapter will use to send messages from the BizTalk server.</span></span>  
  
 <span data-ttu-id="90d2d-104">Las siguientes reglas y restricciones se aplican a esta propiedad:</span><span class="sxs-lookup"><span data-stu-id="90d2d-104">The following rules and restrictions apply to this property:</span></span>  
  
-   <span data-ttu-id="90d2d-105">Esta propiedad se debe configurar en el controlador de adaptador, en el extremo o en ambos.</span><span class="sxs-lookup"><span data-stu-id="90d2d-105">This property must be configured on the adapter handler level, on the endpoint level, or in both places.</span></span>  
  
-   <span data-ttu-id="90d2d-106">La propiedad del servidor SMTP no puede contener los siguientes caracteres: ' ~!</span><span class="sxs-lookup"><span data-stu-id="90d2d-106">The SMTP server property cannot contain the following characters: \` ~ !</span></span> <span data-ttu-id="90d2d-107">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span><span class="sxs-lookup"><span data-stu-id="90d2d-107">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span></span>  
  
-   <span data-ttu-id="90d2d-108">La longitud del nombre del servidor SMTP no debe exceder 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="90d2d-108">The length of the SMTP server name must not exceed 256 characters.</span></span>  
  
 <span data-ttu-id="90d2d-109">El adaptador de SMTP valida siempre el nombre del host SMTP en tiempo de diseño usando las reglas mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="90d2d-109">The SMTP adapter always validates the SMTP host name at design time by using the previously mentioned rules.</span></span> <span data-ttu-id="90d2d-110">Además, el adaptador de SMTP valida el nombre del host SMTP en tiempo de ejecución si se envía un mensaje a través de un puerto dinámico con el adaptador de SMTP.</span><span class="sxs-lookup"><span data-stu-id="90d2d-110">In addition, the SMTP adapter validates the SMTP host name at run time if a message is sent through a dynamic port with the SMTP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d2d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="90d2d-111">See Also</span></span>  
 [<span data-ttu-id="90d2d-112">Restricciones al configurar el adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="90d2d-112">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)