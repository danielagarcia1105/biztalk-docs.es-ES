---
title: Finalizadores SWIFT | Microsoft Docs
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
ms.openlocfilehash: 1457c05b37c3f5b1dfcc5887c1a3f6ce27fcb0d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004845"
---
# <a name="swift-trailers"></a><span data-ttu-id="261cc-102">Finalizadores SWIFT</span><span class="sxs-lookup"><span data-stu-id="261cc-102">SWIFT Trailers</span></span>
<span data-ttu-id="261cc-103">Cada mensaje SWIFT tiene uno o más finalizadores según sea necesario por los requisitos de exchange y la seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="261cc-103">Each SWIFT message has one or more trailers as required by the message exchange and security requirements.</span></span> <span data-ttu-id="261cc-104">Finalizadores del sistema, si procede, siguen los finalizadores de usuario.</span><span class="sxs-lookup"><span data-stu-id="261cc-104">System trailers, if applicable, follow user trailers.</span></span> <span data-ttu-id="261cc-105">Cada finalizador dentro del bloque de finalizador aparece dentro de un subblock delimitado por más pares de llaves.</span><span class="sxs-lookup"><span data-stu-id="261cc-105">Each trailer within the Trailer Block appears within a subblock delimited by further pairs of curly brackets.</span></span> <span data-ttu-id="261cc-106">Cada subblock comienza con tres letras que indica el tipo de finalizador, seguido de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="261cc-106">Each subblock begins with three letters denoting the trailer type, followed by a colon.</span></span>  
  
 <span data-ttu-id="261cc-107">El esquema de finalizador de SWIFT (SWIFT Trailer.xsd) contiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="261cc-107">The SWIFT Trailer schema (SWIFT Trailer.xsd) contains the format for the following:</span></span>  
  
- <span data-ttu-id="261cc-108">El delimitador final del bloque de texto</span><span class="sxs-lookup"><span data-stu-id="261cc-108">The ending delimiter of the text block</span></span>  
  
- <span data-ttu-id="261cc-109">Finalizadores de usuario (información de usuario y del sistema)</span><span class="sxs-lookup"><span data-stu-id="261cc-109">User trailers (user and system information)</span></span>  
  
- <span data-ttu-id="261cc-110">Finalizadores del sistema</span><span class="sxs-lookup"><span data-stu-id="261cc-110">System trailers</span></span>  
  
  <span data-ttu-id="261cc-111">El delimitador final del bloque de texto es "-"}.</span><span class="sxs-lookup"><span data-stu-id="261cc-111">The ending delimiter of the Text Block is "-}".</span></span> <span data-ttu-id="261cc-112">El bloque de finalizador comienza con "{5:".</span><span class="sxs-lookup"><span data-stu-id="261cc-112">The trailer block begins with "{5:".</span></span> <span data-ttu-id="261cc-113">El contenido del bloque de finalizador incluye información de usuario (suma de comprobación, la autenticación de mensajes, autenticación etc.) e información del sistema (mensaje demorado, referencia de mensajes, mensajes duplicados posibles y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="261cc-113">The contents of the trailer block include both user information (checksum, message authentication, proprietary authentication, and so on), and system information (delayed message, message reference, possible duplicate message, and so on).</span></span> <span data-ttu-id="261cc-114">Finalizadores SWIFT agregados también proporcionan un tercer bloque, delimitado por "{S:".</span><span class="sxs-lookup"><span data-stu-id="261cc-114">Trailers added by SWIFT also provide a third block, delimited by "{S:".</span></span> <span data-ttu-id="261cc-115">El *manual del usuario de SWIFT*, "Descripción del servicio FIN", se describe detalladamente el contenido del bloque 5.</span><span class="sxs-lookup"><span data-stu-id="261cc-115">The *SWIFT User Handbook*, "FIN Service Description" topic, describes in detail the contents of block 5.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="261cc-116"> no valida el contenido del bloque S.</span><span class="sxs-lookup"><span data-stu-id="261cc-116"> does not validate the contents of block S.</span></span>  
  
  <span data-ttu-id="261cc-117">La interfaz FIN real o la red SWIFT anexa los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="261cc-117">The actual FIN interface or the SWIFT network appends the trailers.</span></span> <span data-ttu-id="261cc-118">Si un mensaje contiene un finalizador cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] lleva a cabo el finalizador con el mensaje.</span><span class="sxs-lookup"><span data-stu-id="261cc-118">If a message contains a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] carries the trailer with the message.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="261cc-119"> no se genera un error si un mensaje no contiene un finalizador cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="261cc-119"> does not raise an error if a message does not contain a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message.</span></span> <span data-ttu-id="261cc-120">Como sucede con los encabezados, todas las entradas de finalizador, incluidos los bloques de por sí mismos, son opcionales en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="261cc-120">As with headers, all of the trailer entries, including the blocks themselves, are optional in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  
  
  <span data-ttu-id="261cc-121">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="261cc-121">This section contains:</span></span>  
  
- [<span data-ttu-id="261cc-122">Finalizadores de usuario</span><span class="sxs-lookup"><span data-stu-id="261cc-122">User Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
- [<span data-ttu-id="261cc-123">Finalizadores del sistema</span><span class="sxs-lookup"><span data-stu-id="261cc-123">System Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a><span data-ttu-id="261cc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="261cc-124">See Also</span></span>  
 [<span data-ttu-id="261cc-125">Trabajar con esquemas</span><span class="sxs-lookup"><span data-stu-id="261cc-125">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)