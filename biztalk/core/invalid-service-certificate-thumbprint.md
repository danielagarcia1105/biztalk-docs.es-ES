---
title: Huella digital del certificado de servicio no válida | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22e7d74e-40ec-4187-9246-bc8da2a9ce86
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a465d631e72bc27c6b24274deb31e396037aa182
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257220"
---
# <a name="invalid-service-certificate-thumbprint"></a><span data-ttu-id="4b565-102">Huella digital de certificado de servicio no válida</span><span class="sxs-lookup"><span data-stu-id="4b565-102">Invalid service certificate thumbprint</span></span>
## <a name="details"></a><span data-ttu-id="4b565-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4b565-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b565-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4b565-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="4b565-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4b565-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="4b565-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4b565-106">Event ID</span></span>|<span data-ttu-id="4b565-107">0</span><span class="sxs-lookup"><span data-stu-id="4b565-107">0</span></span>|  
|<span data-ttu-id="4b565-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4b565-108">Event Source</span></span>|<span data-ttu-id="4b565-109">0</span><span class="sxs-lookup"><span data-stu-id="4b565-109">0</span></span>|  
|<span data-ttu-id="4b565-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4b565-110">Component</span></span>|<span data-ttu-id="4b565-111">0</span><span class="sxs-lookup"><span data-stu-id="4b565-111">0</span></span>|  
|<span data-ttu-id="4b565-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4b565-112">Symbolic Name</span></span>|<span data-ttu-id="4b565-113">0</span><span class="sxs-lookup"><span data-stu-id="4b565-113">0</span></span>|  
|<span data-ttu-id="4b565-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4b565-114">Message Text</span></span>|<span data-ttu-id="4b565-115">Huella digital de certificado de servicio no válida; se esperaban 40 dígitos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="4b565-115">Invalid service certificate thumbprint; expected 40 hexadecimal digits</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4b565-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="4b565-116">Explanation</span></span>  
 <span data-ttu-id="4b565-117">Se especificó una huella digital de certificado de servicio no válida.</span><span class="sxs-lookup"><span data-stu-id="4b565-117">An invalid service certificate thumbprint was specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b565-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4b565-118">User Action</span></span>  
 <span data-ttu-id="4b565-119">En el código que configura el puerto WCF, la propiedad de certificado de servicio de la interfaz de usuario espera un valor de 40 dígitos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="4b565-119">In the code configuring the WCF port, the service certificate property of the user interface expects a hexadecimal 40-digit value.</span></span> <span data-ttu-id="4b565-120">Ejemplo: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span><span class="sxs-lookup"><span data-stu-id="4b565-120">Example: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span></span>  
  
 <span data-ttu-id="4b565-121">Para obtener más información sobre certificados, vea el recurso siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b565-121">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="4b565-122">Instalación de certificados para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="4b565-122">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)