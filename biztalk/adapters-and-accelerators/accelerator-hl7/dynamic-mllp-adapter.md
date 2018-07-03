---
title: Adaptador de MLLP dinámico | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e22fabb-0edf-4931-b8b2-74a5daccee4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b1ad131716f5b1bb1b5abdfb7985fa93f2ae41c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999813"
---
# <a name="dynamic-mllp-adapter"></a><span data-ttu-id="db738-102">Adaptador de MLLP dinámico</span><span class="sxs-lookup"><span data-stu-id="db738-102">Dynamic MLLP Adapter</span></span>
<span data-ttu-id="db738-103">A partir de [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)], se pueden configurar las propiedades del adaptador MLLP en tiempo de ejecución mediante un puerto de envío unidireccional o bidireccional (solicitud-respuesta).</span><span class="sxs-lookup"><span data-stu-id="db738-103">Starting with [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)], the MLLP adapter properties can be configured at Runtime using a One-Way or Two-Way (Request-Response) send port.</span></span>  
  
## <a name="dynamic-properties"></a><span data-ttu-id="db738-104">Propiedades dinámicas</span><span class="sxs-lookup"><span data-stu-id="db738-104">Dynamic Properties</span></span>  
 <span data-ttu-id="db738-105">Las propiedades siguientes están en el **GlobalPropertySchemas** espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="db738-105">The following properties are in the **GlobalPropertySchemas** namespace:</span></span>  
  
|<span data-ttu-id="db738-106">Property</span><span class="sxs-lookup"><span data-stu-id="db738-106">Property</span></span>|<span data-ttu-id="db738-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="db738-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="db738-108">Mensaje (MLLP.acceptableACKCodes) = "Todos los códigos de confirmación";</span><span class="sxs-lookup"><span data-stu-id="db738-108">Message(MLLP.acceptableACKCodes)=”All ACK Codes”;</span></span>|<span data-ttu-id="db738-109">Los valores son:</span><span class="sxs-lookup"><span data-stu-id="db738-109">Values include:</span></span><br /><br /> <span data-ttu-id="db738-110">-Todos los códigos de confirmación</span><span class="sxs-lookup"><span data-stu-id="db738-110">-   All ACK Codes</span></span><br /><span data-ttu-id="db738-111">-AA y entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="db738-111">-   AA and CA</span></span><br /><span data-ttu-id="db738-112">-AA, CA, AE y CE</span><span class="sxs-lookup"><span data-stu-id="db738-112">-   AA, CA, AE and CE</span></span><br /><span data-ttu-id="db738-113">-AA, CA, AR y CR</span><span class="sxs-lookup"><span data-stu-id="db738-113">-   AA, CA, AR and CR</span></span><br /><br /> <span data-ttu-id="db738-114">Esto es similar a la **aceptable códigos de confirmación** propiedad en un puerto de envío estático de MLLP.</span><span class="sxs-lookup"><span data-stu-id="db738-114">This is similar to the **Acceptable ACK Codes** property in a Static MLLP Send Port.</span></span>|  
|<span data-ttu-id="db738-115">Mensaje (MLLP. CarriageReturn) = "0D";</span><span class="sxs-lookup"><span data-stu-id="db738-115">Message(MLLP.CarriageReturn)=”0d”;</span></span>|<span data-ttu-id="db738-116">Carácter de retorno de carro ASCII</span><span class="sxs-lookup"><span data-stu-id="db738-116">ASCII Carriage Return Character</span></span>|  
|<span data-ttu-id="db738-117">Mensaje (MLLP.endBlockDelimiter) = "c 1";</span><span class="sxs-lookup"><span data-stu-id="db738-117">Message(MLLP.endBlockDelimiter)=”1c”;</span></span>|<span data-ttu-id="db738-118">ASCII de bloque final</span><span class="sxs-lookup"><span data-stu-id="db738-118">ASCII End Block Character</span></span>|  
|<span data-ttu-id="db738-119">Mensaje (MLLP.startBlockDelimiter) = "0b";</span><span class="sxs-lookup"><span data-stu-id="db738-119">Message(MLLP.startBlockDelimiter)=”0b”;</span></span>|<span data-ttu-id="db738-120">ASCII de bloque de inicio</span><span class="sxs-lookup"><span data-stu-id="db738-120">ASCII Start Block Character</span></span>|  
|<span data-ttu-id="db738-121">Mensaje (MLLP.timeout) = "60000";</span><span class="sxs-lookup"><span data-stu-id="db738-121">Message(MLLP.timeout)=”60000”;</span></span>|<span data-ttu-id="db738-122">Período después de qué socket envío inactiva en el tiempo de espera de BTAHL7 server will (0 no es tiempo de espera)</span><span class="sxs-lookup"><span data-stu-id="db738-122">Period after which inactive sending socket on BTAHL7 server will timeout(0 is no timeout)</span></span>|  
|<span data-ttu-id="db738-123">SendPortName(Microsoft.XLANGs.BaseTypes.Address) = "127.0.0.1:11000";</span><span class="sxs-lookup"><span data-stu-id="db738-123">SendPortName(Microsoft.XLANGs.BaseTypes.Address) = “127.0.0.1:11000”;</span></span>|<span data-ttu-id="db738-124">Dirección y puerto para enrutar el mensaje</span><span class="sxs-lookup"><span data-stu-id="db738-124">Address and Port for routing the message</span></span>|  
|<span data-ttu-id="db738-125">SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) = "MLLP";</span><span class="sxs-lookup"><span data-stu-id="db738-125">SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) = “MLLP”;</span></span>|<span data-ttu-id="db738-126">Tipo de adaptador (MLLP)</span><span class="sxs-lookup"><span data-stu-id="db738-126">Type of Adapter (MLLP)</span></span>|  
  
## <a name="additional"></a><span data-ttu-id="db738-127">Notas</span><span class="sxs-lookup"><span data-stu-id="db738-127">Additional</span></span>  
  
- <span data-ttu-id="db738-128">Al crear un mensaje de varias partes en una orquestación para HL7, cree las partes del mensaje en este siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="db738-128">When creating a multipart message in an orchestration for HL7, create the message parts in this following order:</span></span>  
  
  1. <span data-ttu-id="db738-129">Segmento de MSH</span><span class="sxs-lookup"><span data-stu-id="db738-129">MSH Segment</span></span>  
  
  2. <span data-ttu-id="db738-130">BodySegments</span><span class="sxs-lookup"><span data-stu-id="db738-130">BodySegments</span></span>  
  
  3. <span data-ttu-id="db738-131">ZSegments</span><span class="sxs-lookup"><span data-stu-id="db738-131">ZSegments</span></span>  
  
     <span data-ttu-id="db738-132">Si especifica las partes del mensaje en un orden diferente, se produce el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="db738-132">If you specify the message parts in a different order, the following error occurs:</span></span>  
  
     <span data-ttu-id="db738-133">WrongBodyPartException</span><span class="sxs-lookup"><span data-stu-id="db738-133">WrongBodyPartException</span></span>  
  
- <span data-ttu-id="db738-134">Las propiedades de ruta del adaptador pueden especificarse en la orquestación para admitir el enrutamiento dinámico.</span><span class="sxs-lookup"><span data-stu-id="db738-134">The adapter route properties can be specified on the orchestration to support dynamic routing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db738-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="db738-135">See Also</span></span>  
 <span data-ttu-id="db738-136">[Parámetros de configuración de envío y recepción de adaptadores](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="db738-136">[Configuration Parameters for Send and Receive Adapters](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span></span>  
 <span data-ttu-id="db738-137">[Procesamiento de adaptadores de recepción de MLLP](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md) </span><span class="sxs-lookup"><span data-stu-id="db738-137">[MLLP Receive Adapter Processing](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md) </span></span>  
 <span data-ttu-id="db738-138">[Procesamiento de adaptadores de envío MLLP](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span><span class="sxs-lookup"><span data-stu-id="db738-138">[MLLP Send Adapter Processing](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span></span>  
 [<span data-ttu-id="db738-139">Procesamiento de mensajes con codificación MLLP</span><span class="sxs-lookup"><span data-stu-id="db738-139">Processing MLLP-encoded Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)