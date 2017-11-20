---
title: Finalizadores de usuario | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc2d7f2a3dd21d35bb33fa625f59aa27c04e656
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="user-trailers"></a><span data-ttu-id="2745f-102">Finalizadores de usuario</span><span class="sxs-lookup"><span data-stu-id="2745f-102">User Trailers</span></span>
<span data-ttu-id="2745f-103">Finalizadores de usuario, excepto el finalizador de distrib, son opcionales y cuando está presente, se producen en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="2745f-103">User trailers, except for the CHK trailer, are optional and when present, occur in the following order:</span></span>  
  
|<span data-ttu-id="2745f-104">Código de finalizador</span><span class="sxs-lookup"><span data-stu-id="2745f-104">Trailer code</span></span>|<span data-ttu-id="2745f-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="2745f-105">Name</span></span>|  
|------------------|----------|  
|<span data-ttu-id="2745f-106">MAC</span><span class="sxs-lookup"><span data-stu-id="2745f-106">MAC</span></span>|<span data-ttu-id="2745f-107">Código de autenticación de mensaje</span><span class="sxs-lookup"><span data-stu-id="2745f-107">Message Authentication Code</span></span>|  
|<span data-ttu-id="2745f-108">PAC</span><span class="sxs-lookup"><span data-stu-id="2745f-108">PAC</span></span>|<span data-ttu-id="2745f-109">Código de autenticación propietario</span><span class="sxs-lookup"><span data-stu-id="2745f-109">Proprietary Authentication Code</span></span>|  
|<span data-ttu-id="2745f-110">DISTRIB</span><span class="sxs-lookup"><span data-stu-id="2745f-110">CHK</span></span>|<span data-ttu-id="2745f-111">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2745f-111">Checksum</span></span>|  
|<span data-ttu-id="2745f-112">TNG</span><span class="sxs-lookup"><span data-stu-id="2745f-112">TNG</span></span>|<span data-ttu-id="2745f-113">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="2745f-113">Training</span></span>|  
|<span data-ttu-id="2745f-114">PDE</span><span class="sxs-lookup"><span data-stu-id="2745f-114">PDE</span></span>|<span data-ttu-id="2745f-115">Emisión de duplicados posibles</span><span class="sxs-lookup"><span data-stu-id="2745f-115">Possible Duplicate Emission</span></span>|  
  
-   <span data-ttu-id="2745f-116">**Finalizador de código (MAC) de autenticación de mensaje.**</span><span class="sxs-lookup"><span data-stu-id="2745f-116">**Message Authentication Code (MAC) Trailer.**</span></span> <span data-ttu-id="2745f-117">Permite la autenticación por el usuario que recibe.</span><span class="sxs-lookup"><span data-stu-id="2745f-117">Allows authentication by the receiving user.</span></span> <span data-ttu-id="2745f-118">El finalizador de MAC va seguido de un resultado de la autenticación.</span><span class="sxs-lookup"><span data-stu-id="2745f-118">The MAC trailer is followed by an authentication result.</span></span> <span data-ttu-id="2745f-119">Este finalizador es obligatorio para la mayoría de categorías de mensaje de usuario a otro dentro de la aplicación de FIN.</span><span class="sxs-lookup"><span data-stu-id="2745f-119">This trailer is mandatory for most user-to-user message categories within the FIN application.</span></span>  
  
     <span data-ttu-id="2745f-120">Cuando se utiliza el servicio de copia de FIN, un finalizador de PAC (si existe) sigue el finalizador de MAC.</span><span class="sxs-lookup"><span data-stu-id="2745f-120">When the FIN Copy Service is used, a PAC trailer (if present) follows the MAC trailer.</span></span> <span data-ttu-id="2745f-121">El código siguiente es un ejemplo de un finalizador de MAC:</span><span class="sxs-lookup"><span data-stu-id="2745f-121">The following code is an example of a MAC trailer:</span></span>  
  
    ```  
    {MAC:<authentication-result>}  
    where <authentication-result> = 8!h  
    ```  
  
-   <span data-ttu-id="2745f-122">**Finalizador de autenticación propietario código (PAC).**</span><span class="sxs-lookup"><span data-stu-id="2745f-122">**Proprietary Authentication Code (PAC) Trailer.**</span></span> <span data-ttu-id="2745f-123">El finalizador de PAC se utiliza en el servicio de copia de FIN solo cuando se utiliza la opción de autenticación dobles.</span><span class="sxs-lookup"><span data-stu-id="2745f-123">The PAC trailer is used within the FIN Copy service only when using the double authentication option.</span></span> <span data-ttu-id="2745f-124">Mensajes de usuario a otro bloque 5 de FINÉS incluyen el finalizador de PAC inmediatamente después del finalizador de MAC, si está presente.</span><span class="sxs-lookup"><span data-stu-id="2745f-124">Block 5 of FIN user-to-user messages include the PAC trailer immediately after the MAC trailer, if present.</span></span> <span data-ttu-id="2745f-125">Este resultado se calcula en los campos extraídos del bloque 4 del mensaje, el valor del campo 115, si está presente y el \<resultado de la autenticación > del finalizador de MAC para servicios de copia con doble autenticación.</span><span class="sxs-lookup"><span data-stu-id="2745f-125">This result is calculated on the extracted fields of Block 4 of the message, the value of field 115, if present, and the \<authentication-result> of the MAC trailer for Copy Services with double authentication.</span></span>  
  
     <span data-ttu-id="2745f-126">Como resultado, el indicador de bloque final (CrLf-) se incluye en el cálculo de PAC y los campos se definen como sigue:</span><span class="sxs-lookup"><span data-stu-id="2745f-126">As a result, the end-of-block indicator (CrLf-) is included in the PAC calculation and the fields are defined as follows:</span></span>  
  
    -   <span data-ttu-id="2745f-127">Los primeros cuatro caracteres son CrLf:</span><span class="sxs-lookup"><span data-stu-id="2745f-127">The first four characters are CrLf:</span></span>  
  
    -   <span data-ttu-id="2745f-128">El campo y el delimitador están presentes, es decir, 32:, 20:, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2745f-128">The field and the delimiter are present, that is, 32A:, 20:, and so on.</span></span>  
  
    -   <span data-ttu-id="2745f-129">Todos los subcampos y sus delimitadores están presentes.</span><span class="sxs-lookup"><span data-stu-id="2745f-129">All subfields and their delimiters are present.</span></span>  
  
     <span data-ttu-id="2745f-130">El código siguiente es un ejemplo del formato de finalizador PAC:</span><span class="sxs-lookup"><span data-stu-id="2745f-130">The following code is an example of the PAC trailer format:</span></span>  
  
    ```  
    {PAC:[<authentication-result>]}  
    where <authentication-result> is mandatory on input messages only and  
    <authentication-result> = 8!h  
    ```  
  
-   <span data-ttu-id="2745f-131">**Finalizador de distrib (suma de comprobación) (obligatorio para todos los mensajes FIN)**</span><span class="sxs-lookup"><span data-stu-id="2745f-131">**CHK (Checksum) Trailer (mandatory for all FIN messages)**</span></span>  
  
     <span data-ttu-id="2745f-132">El finalizador de distrib es obligatorio para todos los mensajes FIN y se calcula basándose en la dirección del destinatario (12 caracteres con el carácter noveno reemplazan por *X* junto con el bloque de texto).</span><span class="sxs-lookup"><span data-stu-id="2745f-132">The CHK trailer is mandatory for all FIN messages and is computed based upon the receiver's address (12 characters with the ninth character replaced by *X* plus the text block).</span></span> <span data-ttu-id="2745f-133">Este finalizador, el sistema y el CBT para comprobar que los mensajes no están dañados debido a un fallo en el sistema o un error de transmisión sin detectar.</span><span class="sxs-lookup"><span data-stu-id="2745f-133">This trailer allows the system and the CBT to check that messages are not corrupted due to a system malfunction or an undetected transmission error.</span></span>  
  
     <span data-ttu-id="2745f-134">El código siguiente es un ejemplo del formato de finalizador distrib:</span><span class="sxs-lookup"><span data-stu-id="2745f-134">The following code is an example of the CHK trailer format:</span></span>  
  
    ```  
    {CHK:<checksum-result>}  
    where <checksum-result> = 12!h  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2745f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2745f-135">See Also</span></span>  
 [<span data-ttu-id="2745f-136">Trabajar con esquemas</span><span class="sxs-lookup"><span data-stu-id="2745f-136">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)