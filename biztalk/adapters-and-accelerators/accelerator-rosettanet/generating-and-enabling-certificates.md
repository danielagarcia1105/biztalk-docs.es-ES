---
title: Generar y habilitar certificados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, enabling
- private process tutorial, creating certificates
- private process tutorial, enabling certificates
ms.assetid: a36d9725-d57c-499d-948d-558096709d67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93293939ae509dcb2af04e17fcdd35e9cf6d03cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209788"
---
# <a name="generating-and-enabling-certificates"></a><span data-ttu-id="d2106-102">Generar y habilitar certificados</span><span class="sxs-lookup"><span data-stu-id="d2106-102">Generating and Enabling Certificates</span></span>
<span data-ttu-id="d2106-103">Este tutorial utiliza certificados para firmar y cifrar mensajes enviados por las organizaciones de Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="d2106-103">This tutorial uses certificates to sign and encrypt messages sent by the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="d2106-104">Si ya ha completado el Tutorial de doble acción, puede omitir este paso y pase a [crear la solución de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md).</span><span class="sxs-lookup"><span data-stu-id="d2106-104">If you have already completed the Double Action Tutorial, you may skip this step and move on to [Creating the Contoso Solution](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md).</span></span> <span data-ttu-id="d2106-105">Para generar y usar certificados para este tutorial, siga los procedimientos descritos en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2106-105">To generate and use certificates for this tutorial, follow the procedures in the following topics:</span></span>  
  
-   [<span data-ttu-id="d2106-106">Paso 1: Crear una entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="d2106-106">Step 1: Creating a Certification Authority</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [<span data-ttu-id="d2106-107">Paso 2: Crear Public y Private certificados</span><span class="sxs-lookup"><span data-stu-id="d2106-107">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="d2106-108">Paso 3: Importar Public y Private certificados</span><span class="sxs-lookup"><span data-stu-id="d2106-108">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="d2106-109">Paso 4: Habilitar SSL en IIS</span><span class="sxs-lookup"><span data-stu-id="d2106-109">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2106-110">Estos pasos se encuentran en el Tutorial de doble acción.</span><span class="sxs-lookup"><span data-stu-id="d2106-110">These steps are in the Double Action Tutorial.</span></span> <span data-ttu-id="d2106-111">Después de completar cada paso, volver a este tema para seguir el Tutorial de procesos privado.</span><span class="sxs-lookup"><span data-stu-id="d2106-111">After completing each step, return to this topic to continue the Private Process Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2106-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2106-112">See Also</span></span>  
 [<span data-ttu-id="d2106-113">Creación de la solución de Contoso</span><span class="sxs-lookup"><span data-stu-id="d2106-113">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)