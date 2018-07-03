---
title: Huella digital del certificado de cliente válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f18fa0a2-b0d9-4190-aa96-12ab7007edd1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74551ac825f9e517bec1d07edc7f288db732b348
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018886"
---
# <a name="invalid-client-certificate-thumbprint"></a><span data-ttu-id="08312-102">Huella digital de certificado de cliente no válida</span><span class="sxs-lookup"><span data-stu-id="08312-102">Invalid client certificate thumbprint</span></span>
## <a name="details"></a><span data-ttu-id="08312-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="08312-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="08312-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="08312-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="08312-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="08312-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="08312-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="08312-106">Event ID</span></span>     |                                         <span data-ttu-id="08312-107">0</span><span class="sxs-lookup"><span data-stu-id="08312-107">0</span></span>                                          |
|  <span data-ttu-id="08312-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="08312-108">Event Source</span></span>   |                                         <span data-ttu-id="08312-109">0</span><span class="sxs-lookup"><span data-stu-id="08312-109">0</span></span>                                          |
|    <span data-ttu-id="08312-110">Componente</span><span class="sxs-lookup"><span data-stu-id="08312-110">Component</span></span>    |                                         <span data-ttu-id="08312-111">0</span><span class="sxs-lookup"><span data-stu-id="08312-111">0</span></span>                                          |
|  <span data-ttu-id="08312-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="08312-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="08312-113">0</span><span class="sxs-lookup"><span data-stu-id="08312-113">0</span></span>                                          |
|  <span data-ttu-id="08312-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="08312-114">Message Text</span></span>   |       <span data-ttu-id="08312-115">Huella digital de certificado no válida; se esperaban 40 dígitos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="08312-115">Invalid client certificate thumbprint; expected 40 hexadecimal digits.</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="08312-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="08312-116">Explanation</span></span>  
 <span data-ttu-id="08312-117">Se especificó una huella digital de certificado de cliente no válida.</span><span class="sxs-lookup"><span data-stu-id="08312-117">An invalid client certificate thumbprint was specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08312-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="08312-118">User Action</span></span>  
 <span data-ttu-id="08312-119">En el código que configura el puerto de envío WCF, la propiedad de certificado de cliente de la interfaz de usuario espera un valor de 40 dígitos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="08312-119">In the code configuring the WCF send port, the client certificate property of the user interface expects a hexadecimal 40-digit value.</span></span> <span data-ttu-id="08312-120">Ejemplo: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span><span class="sxs-lookup"><span data-stu-id="08312-120">Example: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span></span>  
  
 <span data-ttu-id="08312-121">Para obtener más información sobre certificados, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08312-121">For additional information on certificates, see the following:</span></span>  
  
-   [<span data-ttu-id="08312-122">Instalación de certificados para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="08312-122">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)