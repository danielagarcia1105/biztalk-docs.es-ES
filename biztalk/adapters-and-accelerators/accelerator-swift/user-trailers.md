---
title: Finalizadores de usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10bc0d4d0fcdb36311e0590d9ae04239db168ed7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010221"
---
# <a name="user-trailers"></a><span data-ttu-id="2d837-102">Finalizadores de usuario</span><span class="sxs-lookup"><span data-stu-id="2d837-102">User Trailers</span></span>
<span data-ttu-id="2d837-103">Finalizadores de usuario, excepto el finalizador "chk", son opcionales y cuando está presente, se producen en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d837-103">User trailers, except for the CHK trailer, are optional and when present, occur in the following order:</span></span>  
  
|<span data-ttu-id="2d837-104">Código de finalizador</span><span class="sxs-lookup"><span data-stu-id="2d837-104">Trailer code</span></span>|<span data-ttu-id="2d837-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d837-105">Name</span></span>|  
|------------------|----------|  
|<span data-ttu-id="2d837-106">MAC</span><span class="sxs-lookup"><span data-stu-id="2d837-106">MAC</span></span>|<span data-ttu-id="2d837-107">Código de autenticación de mensajes</span><span class="sxs-lookup"><span data-stu-id="2d837-107">Message Authentication Code</span></span>|  
|<span data-ttu-id="2d837-108">PAC</span><span class="sxs-lookup"><span data-stu-id="2d837-108">PAC</span></span>|<span data-ttu-id="2d837-109">Código de autenticación propietario</span><span class="sxs-lookup"><span data-stu-id="2d837-109">Proprietary Authentication Code</span></span>|  
|<span data-ttu-id="2d837-110">"CHK"</span><span class="sxs-lookup"><span data-stu-id="2d837-110">CHK</span></span>|<span data-ttu-id="2d837-111">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="2d837-111">Checksum</span></span>|  
|<span data-ttu-id="2d837-112">TNG</span><span class="sxs-lookup"><span data-stu-id="2d837-112">TNG</span></span>|<span data-ttu-id="2d837-113">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="2d837-113">Training</span></span>|  
|<span data-ttu-id="2d837-114">PDE</span><span class="sxs-lookup"><span data-stu-id="2d837-114">PDE</span></span>|<span data-ttu-id="2d837-115">Emisión de duplicados posibles</span><span class="sxs-lookup"><span data-stu-id="2d837-115">Possible Duplicate Emission</span></span>|  
  
- <span data-ttu-id="2d837-116">**Finalizador de código (MAC) de autenticación de mensaje.**</span><span class="sxs-lookup"><span data-stu-id="2d837-116">**Message Authentication Code (MAC) Trailer.**</span></span> <span data-ttu-id="2d837-117">Permite la autenticación del usuario que recibe.</span><span class="sxs-lookup"><span data-stu-id="2d837-117">Allows authentication by the receiving user.</span></span> <span data-ttu-id="2d837-118">El finalizador de MAC seguido de un resultado de la autenticación.</span><span class="sxs-lookup"><span data-stu-id="2d837-118">The MAC trailer is followed by an authentication result.</span></span> <span data-ttu-id="2d837-119">Este finalizador es obligatorio para la mayoría de las categorías de mensaje al usuario dentro de la aplicación a FIN.</span><span class="sxs-lookup"><span data-stu-id="2d837-119">This trailer is mandatory for most user-to-user message categories within the FIN application.</span></span>  
  
   <span data-ttu-id="2d837-120">Cuando se usa el servicio de FIN, un finalizador de PAC (si existe) sigue el finalizador de MAC.</span><span class="sxs-lookup"><span data-stu-id="2d837-120">When the FIN Copy Service is used, a PAC trailer (if present) follows the MAC trailer.</span></span> <span data-ttu-id="2d837-121">El código siguiente es un ejemplo de un finalizador de MAC:</span><span class="sxs-lookup"><span data-stu-id="2d837-121">The following code is an example of a MAC trailer:</span></span>  
  
  ```  
  {MAC:<authentication-result>}  
  where <authentication-result> = 8!h  
  ```  
  
- <span data-ttu-id="2d837-122">**Finalizador de código (PAC) de autenticación propietario.**</span><span class="sxs-lookup"><span data-stu-id="2d837-122">**Proprietary Authentication Code (PAC) Trailer.**</span></span> <span data-ttu-id="2d837-123">El finalizador de PAC se utiliza en el servicio de FIN solo cuando se usa la opción de doble autenticación.</span><span class="sxs-lookup"><span data-stu-id="2d837-123">The PAC trailer is used within the FIN Copy service only when using the double authentication option.</span></span> <span data-ttu-id="2d837-124">Los mensajes de usuario a otro bloque 5 de FIN incluyen el finalizador de PAC inmediatamente después del finalizador de MAC, si está presente.</span><span class="sxs-lookup"><span data-stu-id="2d837-124">Block 5 of FIN user-to-user messages include the PAC trailer immediately after the MAC trailer, if present.</span></span> <span data-ttu-id="2d837-125">Este resultado se calcula en los campos extraídos de bloque de 4 del mensaje, el valor del campo 115, si está presente y el \<resultado de la autenticación\> del remolque MAC para los servicios de copia con doble autenticación.</span><span class="sxs-lookup"><span data-stu-id="2d837-125">This result is calculated on the extracted fields of Block 4 of the message, the value of field 115, if present, and the \<authentication-result\> of the MAC trailer for Copy Services with double authentication.</span></span>  
  
   <span data-ttu-id="2d837-126">Como resultado, el indicador de final del bloque (CrLf-) se incluye en el cálculo de PAC y los campos se definen como sigue:</span><span class="sxs-lookup"><span data-stu-id="2d837-126">As a result, the end-of-block indicator (CrLf-) is included in the PAC calculation and the fields are defined as follows:</span></span>  
  
  - <span data-ttu-id="2d837-127">Los primeros cuatro caracteres son CrLf:</span><span class="sxs-lookup"><span data-stu-id="2d837-127">The first four characters are CrLf:</span></span>  
  
  - <span data-ttu-id="2d837-128">El campo y los delimitadores están presentes, es decir, 32A:, 20:, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2d837-128">The field and the delimiter are present, that is, 32A:, 20:, and so on.</span></span>  
  
  - <span data-ttu-id="2d837-129">Todos los subcampos y sus delimitadores están presentes.</span><span class="sxs-lookup"><span data-stu-id="2d837-129">All subfields and their delimiters are present.</span></span>  
  
    <span data-ttu-id="2d837-130">El código siguiente es un ejemplo del formato de finalizador PAC:</span><span class="sxs-lookup"><span data-stu-id="2d837-130">The following code is an example of the PAC trailer format:</span></span>  
  
  ```  
  {PAC:[<authentication-result>]}  
  where <authentication-result> is mandatory on input messages only and  
  <authentication-result> = 8!h  
  ```  
  
- <span data-ttu-id="2d837-131">**Finalizador "chk" (suma de comprobación) (obligatorio para todos los mensajes FIN)**</span><span class="sxs-lookup"><span data-stu-id="2d837-131">**CHK (Checksum) Trailer (mandatory for all FIN messages)**</span></span>  
  
   <span data-ttu-id="2d837-132">El finalizador "chk" es obligatorio para todos los mensajes FIN y se calcula basándose en la dirección del destinatario (12 caracteres con la novena reemplazan por *X* además del bloque de texto).</span><span class="sxs-lookup"><span data-stu-id="2d837-132">The CHK trailer is mandatory for all FIN messages and is computed based upon the receiver's address (12 characters with the ninth character replaced by *X* plus the text block).</span></span> <span data-ttu-id="2d837-133">Este finalizador permite que el sistema y el CBT para comprobar que los mensajes no están dañados debido a un error de funcionamiento del sistema o un error de transmisión no detectados.</span><span class="sxs-lookup"><span data-stu-id="2d837-133">This trailer allows the system and the CBT to check that messages are not corrupted due to a system malfunction or an undetected transmission error.</span></span>  
  
   <span data-ttu-id="2d837-134">El código siguiente es un ejemplo del formato de finalizador "chk":</span><span class="sxs-lookup"><span data-stu-id="2d837-134">The following code is an example of the CHK trailer format:</span></span>  
  
  ```  
  {CHK:<checksum-result>}  
  where <checksum-result> = 12!h  
  ```  
  
## <a name="see-also"></a><span data-ttu-id="2d837-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d837-135">See Also</span></span>  
 [<span data-ttu-id="2d837-136">Trabajar con esquemas</span><span class="sxs-lookup"><span data-stu-id="2d837-136">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)