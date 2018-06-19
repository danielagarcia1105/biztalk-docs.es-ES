---
title: SWIFT remolque | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT Trailer schema
- schemas, SWIFT
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: b6d64584-0514-4c87-98c0-33755efc4695
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc3155ac21f55e7c61483b9287429f9b722f6a84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214500"
---
# <a name="swift-trailers"></a><span data-ttu-id="cca0f-102">Finalizadores SWIFT</span><span class="sxs-lookup"><span data-stu-id="cca0f-102">SWIFT Trailers</span></span>
<span data-ttu-id="cca0f-103">Cada mensaje SWIFT tiene uno o más finalizadores según sea necesario por los requisitos de exchange y la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cca0f-103">Each SWIFT message has one or more trailers as required by the message exchange and security requirements.</span></span> <span data-ttu-id="cca0f-104">Finalizadores de sistema, si procede, siguen los finalizadores de usuario.</span><span class="sxs-lookup"><span data-stu-id="cca0f-104">System trailers, if applicable, follow user trailers.</span></span> <span data-ttu-id="cca0f-105">Cada finalizador dentro del bloque de finalizador aparece dentro de un subbloques delimitados por más pares de paréntesis.</span><span class="sxs-lookup"><span data-stu-id="cca0f-105">Each trailer within the Trailer Block appears within a subblock delimited by further pairs of curly brackets.</span></span> <span data-ttu-id="cca0f-106">Cada subbloques comienza con tres letras que indica el tipo de finalizador, seguido de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="cca0f-106">Each subblock begins with three letters denoting the trailer type, followed by a colon.</span></span>  
  
 <span data-ttu-id="cca0f-107">El esquema de finalizador de SWIFT (SWIFT Trailer.xsd) contiene el formato para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cca0f-107">The SWIFT Trailer schema (SWIFT Trailer.xsd) contains the format for the following:</span></span>  
  
-   <span data-ttu-id="cca0f-108">El delimitador final del bloque de texto</span><span class="sxs-lookup"><span data-stu-id="cca0f-108">The ending delimiter of the text block</span></span>  
  
-   <span data-ttu-id="cca0f-109">Finalizadores de usuario (información de usuario y del sistema)</span><span class="sxs-lookup"><span data-stu-id="cca0f-109">User trailers (user and system information)</span></span>  
  
-   <span data-ttu-id="cca0f-110">Finalizadores de sistema</span><span class="sxs-lookup"><span data-stu-id="cca0f-110">System trailers</span></span>  
  
 <span data-ttu-id="cca0f-111">El delimitador final del bloque de texto es "-"}.</span><span class="sxs-lookup"><span data-stu-id="cca0f-111">The ending delimiter of the Text Block is "-}".</span></span> <span data-ttu-id="cca0f-112">El bloque de finalizador comienza con "{5:".</span><span class="sxs-lookup"><span data-stu-id="cca0f-112">The trailer block begins with "{5:".</span></span> <span data-ttu-id="cca0f-113">El contenido del bloque de finalizador incluye información de usuario (suma de comprobación, autenticación de mensajes, autenticación propietario etc.) y de información del sistema (mensajes retrasada, referencia de mensajes, mensajes duplicados posibles y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="cca0f-113">The contents of the trailer block include both user information (checksum, message authentication, proprietary authentication, and so on), and system information (delayed message, message reference, possible duplicate message, and so on).</span></span> <span data-ttu-id="cca0f-114">Finalizadores agregadas por SWIFT también proporcionan un bloque terceros, delimitado por "{S:".</span><span class="sxs-lookup"><span data-stu-id="cca0f-114">Trailers added by SWIFT also provide a third block, delimited by "{S:".</span></span> <span data-ttu-id="cca0f-115">El *manual de usuario de SWIFT*, tema "Descripción del servicio FINÉS", se describe detalladamente el contenido del bloque 5.</span><span class="sxs-lookup"><span data-stu-id="cca0f-115">The *SWIFT User Handbook*, "FIN Service Description" topic, describes in detail the contents of block 5.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="cca0f-116">no valida el contenido del bloque S.</span><span class="sxs-lookup"><span data-stu-id="cca0f-116"> does not validate the contents of block S.</span></span>  
  
 <span data-ttu-id="cca0f-117">La interfaz FIN real o la red SWIFT anexa los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="cca0f-117">The actual FIN interface or the SWIFT network appends the trailers.</span></span> <span data-ttu-id="cca0f-118">Si un mensaje contiene un finalizador cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] lleva el finalizador con el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cca0f-118">If a message contains a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] carries the trailer with the message.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="cca0f-119">no se genera un error si un mensaje no contenía un finalizador cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cca0f-119"> does not raise an error if a message does not contain a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message.</span></span> <span data-ttu-id="cca0f-120">Como con encabezados, todas las entradas de finalizador, incluidos los bloques de por sí mismos, son opcionales en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cca0f-120">As with headers, all of the trailer entries, including the blocks themselves, are optional in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  
  
 <span data-ttu-id="cca0f-121">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="cca0f-121">This section contains:</span></span>  
  
-   [<span data-ttu-id="cca0f-122">Finalizadores de usuario</span><span class="sxs-lookup"><span data-stu-id="cca0f-122">User Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
-   [<span data-ttu-id="cca0f-123">Finalizadores de sistema</span><span class="sxs-lookup"><span data-stu-id="cca0f-123">System Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a><span data-ttu-id="cca0f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="cca0f-124">See Also</span></span>  
 [<span data-ttu-id="cca0f-125">Trabajar con esquemas</span><span class="sxs-lookup"><span data-stu-id="cca0f-125">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)