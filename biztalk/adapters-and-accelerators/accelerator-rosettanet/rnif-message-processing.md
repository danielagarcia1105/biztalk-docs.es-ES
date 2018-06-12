---
title: Procesamiento de mensajes RNIF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RosettaNet Implementation Framework (RNIF)
- RosettaNet, about RosettaNet
- RNIF
- RNIF, non-repudiation
- RNIF, BizTalk Accelerator for RosettaNet
- non-repudiation
- RNIF, about RNIF
- BizTalk Accelerator for RosettaNet, RNIF
- RosettaNet
ms.assetid: 994f15bc-765c-4220-8ab1-176919e9e821
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810f673b9ae2cf9c6e1b64ccab6a6a541118cbca
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855527"
---
# <a name="rnif-message-processing"></a><span data-ttu-id="40d51-102">Procesamiento de mensajes RNIF</span><span class="sxs-lookup"><span data-stu-id="40d51-102">RNIF Message Processing</span></span>
<span data-ttu-id="40d51-103">La organización RosettaNet define el intercambio de mensajes en las especificaciones de RosettaNet Implementation Framework (RNIF).</span><span class="sxs-lookup"><span data-stu-id="40d51-103">The RosettaNet organization defines message exchange in the RosettaNet Implementation Framework (RNIF) specifications.</span></span> <span data-ttu-id="40d51-104">RNIF define cómo sistemas de integración transportan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="40d51-104">RNIF defines how integration systems will transport messages.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="40d51-105"> implementa por completo las especificaciones de RNIF, agregar esta funcionalidad a lo que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporcionan de forma nativa de cuadro.</span><span class="sxs-lookup"><span data-stu-id="40d51-105"> fully implements the RNIF specifications, adding that functionality to what [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] natively provides out-of-the-box.</span></span>  
  
<span data-ttu-id="40d51-106">Las comunicaciones de RNIF son complejas.</span><span class="sxs-lookup"><span data-stu-id="40d51-106">RNIF communications are complex.</span></span> <span data-ttu-id="40d51-107">Los procesos públicos que realizan el procesamiento de RNIF incluyen una serie de comprobaciones de validación y la lógica de flujo de trabajo complejo.</span><span class="sxs-lookup"><span data-stu-id="40d51-107">The public processes that perform RNIF processing include a variety of validation checks and complex workflow logic.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="40d51-108"> proporciona esta funcionalidad de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="40d51-108"> provides this functionality natively.</span></span> <span data-ttu-id="40d51-109">Esto le permite usar un sistema compatible con RosettaNet sin desarrollar o mantener la lógica RNIF desde el principio.</span><span class="sxs-lookup"><span data-stu-id="40d51-109">This lets you use a RosettaNet-compliant system without developing or maintaining RNIF logic from scratch.</span></span>  
  
## <a name="btarn-support-for-rnif"></a><span data-ttu-id="40d51-110">Compatibilidad con BTARN RNIF</span><span class="sxs-lookup"><span data-stu-id="40d51-110">BTARN Support for RNIF</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="40d51-111"> es compatible con ambas versiones de RNIF: RNIF 1.1 y RNIF 2.0 (V02.00.01).</span><span class="sxs-lookup"><span data-stu-id="40d51-111"> supports both versions of RNIF: RNIF 1.1 and RNIF 2.0 (V02.00.01).</span></span> <span data-ttu-id="40d51-112">RNIF 2.0 agrega funciones no compatibles con RNIF 1.1, incluido el cifrado, los datos adjuntos y transacciones sincrónicas.</span><span class="sxs-lookup"><span data-stu-id="40d51-112">RNIF 2.0 added significant functionality beyond that supported by RNIF 1.1, including encryption, attachments, and synchronous transactions.</span></span> <span data-ttu-id="40d51-113">RNIF 2.0 no es compatible con RNIF 1.1.</span><span class="sxs-lookup"><span data-stu-id="40d51-113">RNIF 2.0 is not backward compatible with RNIF 1.1.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="40d51-114"> es compatible con RosettaNet listo RNIF 2.0.</span><span class="sxs-lookup"><span data-stu-id="40d51-114"> is RosettaNet Ready RNIF 2.0 compliant.</span></span>  
  
<span data-ttu-id="40d51-115">Las dos versiones definen los mensajes de RosettaNet de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="40d51-115">The two versions define the RosettaNet message differently.</span></span> <span data-ttu-id="40d51-116">Para obtener más información acerca de los contenedores de mensajes diferente, consulte [RNIF estándar](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md).</span><span class="sxs-lookup"><span data-stu-id="40d51-116">For more information about the different message containers, see [RNIF Standard](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md).</span></span>  
  
<span data-ttu-id="40d51-117">Sistemas de integración realizan la transferencia RNIF con HTTP/HTTPS y SMTP; Sin embargo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementa sólo HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="40d51-117">Integration systems perform RNIF transfer over HTTP/HTTPS and SMTP; however, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implements only HTTP/HTTPS.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="40d51-118"> no admite datos adjuntos y las transacciones sincrónicas en RNIF 1.1.</span><span class="sxs-lookup"><span data-stu-id="40d51-118"> does not support attachments and synchronous transactions in RNIF 1.1.</span></span>  
  
### <a name="non-repudiation"></a><span data-ttu-id="40d51-119">Sin repudio</span><span class="sxs-lookup"><span data-stu-id="40d51-119">Non-Repudiation</span></span>  
<span data-ttu-id="40d51-120">El estándar RNIF incluye un requisito para sin repudio.</span><span class="sxs-lookup"><span data-stu-id="40d51-120">The RNIF standard includes a requirement for non-repudiation.</span></span> <span data-ttu-id="40d51-121">Esto implica almacenar el formato de los mensajes recibidos o enviados mediante [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] en una base de datos sin repudio, por lo que se puede demostrar legalmente que ha recibido o enviado.</span><span class="sxs-lookup"><span data-stu-id="40d51-121">This involves storing the wire format of any message received or sent by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] in a non-repudiation database, so that you can prove legally that you have received or sent it.</span></span> <span data-ttu-id="40d51-122">Para este propósito, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] utiliza la tabla MessageStorageIn en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]archivar la base de datos para los mensajes entrantes y la tabla MessageStorageOut de la misma base de datos para los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="40d51-122">For this purpose, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] uses the MessageStorageIn table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive database for incoming messages and the MessageStorageOut table in the same database for outgoing messages.</span></span>  
  
<span data-ttu-id="40d51-123">Se establecen sin repudio requisitos para el contenido de servicio y para las confirmaciones por separado en el perfil de configuración de proceso.</span><span class="sxs-lookup"><span data-stu-id="40d51-123">You set non-repudiation requirements for service content and for acknowledgements separately in the process configuration profile.</span></span> <span data-ttu-id="40d51-124">Si establece uno o ambos de la **sin repudio del origen y del contenido** y **sin repudio necesario** opciones para `True`, a continuación, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] se almacenarán los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="40d51-124">If you set one or both of the **Non-Repudiation of Origin and Content** and **Non-Repudiation Required** options to `True`, then [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will store the following data:</span></span>  
  
|<span data-ttu-id="40d51-125">data</span><span class="sxs-lookup"><span data-stu-id="40d51-125">Data</span></span>|<span data-ttu-id="40d51-126">Contenido</span><span class="sxs-lookup"><span data-stu-id="40d51-126">Contents</span></span>|  
|----------|--------------|  
|<span data-ttu-id="40d51-127">RecordID</span><span class="sxs-lookup"><span data-stu-id="40d51-127">RecordID</span></span>|<span data-ttu-id="40d51-128">Propiedad Id. único del mensaje almacenado</span><span class="sxs-lookup"><span data-stu-id="40d51-128">Proprietary unique ID of the stored message</span></span>|  
|<span data-ttu-id="40d51-129">MessageCategory</span><span class="sxs-lookup"><span data-stu-id="40d51-129">MessageCategory</span></span>|<span data-ttu-id="40d51-130">(0) de la solicitud, respuesta (1) o señal (2)</span><span class="sxs-lookup"><span data-stu-id="40d51-130">Request (0), Response (1), or Signal (2)</span></span>|  
|<span data-ttu-id="40d51-131">DestinationParty</span><span class="sxs-lookup"><span data-stu-id="40d51-131">DestinationParty</span></span>|<span data-ttu-id="40d51-132">Nombre de la entidad de destino</span><span class="sxs-lookup"><span data-stu-id="40d51-132">Name of the destination party</span></span>|  
|<span data-ttu-id="40d51-133">SourceParty</span><span class="sxs-lookup"><span data-stu-id="40d51-133">SourceParty</span></span>|<span data-ttu-id="40d51-134">Nombre de la entidad de origen</span><span class="sxs-lookup"><span data-stu-id="40d51-134">Name of the source party</span></span>|  
|<span data-ttu-id="40d51-135">PIPCode</span><span class="sxs-lookup"><span data-stu-id="40d51-135">PIPCode</span></span>|<span data-ttu-id="40d51-136">Por ejemplo, PIP3A4</span><span class="sxs-lookup"><span data-stu-id="40d51-136">For example, PIP3A4</span></span>|  
|<span data-ttu-id="40d51-137">PIPVersion</span><span class="sxs-lookup"><span data-stu-id="40d51-137">PIPVersion</span></span>|<span data-ttu-id="40d51-138">Por ejemplo, V02.00</span><span class="sxs-lookup"><span data-stu-id="40d51-138">For example, V02.00</span></span>|  
|<span data-ttu-id="40d51-139">MessageContent</span><span class="sxs-lookup"><span data-stu-id="40d51-139">MessageContent</span></span>|<span data-ttu-id="40d51-140">Mensaje en formato binario</span><span class="sxs-lookup"><span data-stu-id="40d51-140">Message in binary format</span></span>|  
|<span data-ttu-id="40d51-141">MessageTrackingID</span><span class="sxs-lookup"><span data-stu-id="40d51-141">MessageTrackingID</span></span>|<span data-ttu-id="40d51-142">Identificador del mensaje de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="40d51-142">Message tracking ID of the message</span></span>|  
|<span data-ttu-id="40d51-143">PIPInstanceID</span><span class="sxs-lookup"><span data-stu-id="40d51-143">PIPInstanceID</span></span>|<span data-ttu-id="40d51-144">Id. de instancia PIP del proceso</span><span class="sxs-lookup"><span data-stu-id="40d51-144">PIP instance ID of the process</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40d51-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="40d51-145">See Also</span></span>  
 <span data-ttu-id="40d51-146">[Lo que agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="40d51-146">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="40d51-147">Implementación de PIP</span><span class="sxs-lookup"><span data-stu-id="40d51-147">PIP Implementation</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)
