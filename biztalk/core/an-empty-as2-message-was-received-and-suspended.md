---
title: Se recibió y suspendió un mensaje AS2 vacío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 349f7134-d039-44ab-b2b3-d378d38dfd38
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48701d24b405f46ad66a76c0ac473fb7343317f2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994133"
---
# <a name="an-empty-as2-message-was-received-and-suspended"></a><span data-ttu-id="6ab45-102">Se recibió y suspendió un mensaje AS2 vacío</span><span class="sxs-lookup"><span data-stu-id="6ab45-102">An empty AS2 message was received and suspended</span></span>
## <a name="details"></a><span data-ttu-id="6ab45-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6ab45-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6ab45-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6ab45-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6ab45-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6ab45-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6ab45-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6ab45-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6ab45-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6ab45-107">Event Source</span></span>   | <span data-ttu-id="6ab45-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ab45-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="6ab45-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6ab45-109">Component</span></span>    |                                       <span data-ttu-id="6ab45-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="6ab45-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="6ab45-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6ab45-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="6ab45-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6ab45-112">Message Text</span></span>   |           <span data-ttu-id="6ab45-113">Se recibió un mensaje AS2 vacío.</span><span class="sxs-lookup"><span data-stu-id="6ab45-113">An empty AS2 message was received.</span></span>  <span data-ttu-id="6ab45-114">El mensaje se suspenderá.</span><span class="sxs-lookup"><span data-stu-id="6ab45-114">The message will be suspended.</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="6ab45-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="6ab45-115">Explanation</span></span>  
 <span data-ttu-id="6ab45-116">Este evento de error,  indica que BizTalk Server no pudo procesar el mensaje AS2 entrante porque el mensaje no contiene cuerpo.</span><span class="sxs-lookup"><span data-stu-id="6ab45-116">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message does not contain a body.</span></span> <span data-ttu-id="6ab45-117">El cuerpo debe estar separado de los encabezados por dos retornos de carro o avances de línea.</span><span class="sxs-lookup"><span data-stu-id="6ab45-117">The body must be separated from the headers by two carriage return/line feeds.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6ab45-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6ab45-118">User Action</span></span>  
 <span data-ttu-id="6ab45-119">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ab45-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="6ab45-120">Asegúrese de que la entidad remitente agrega un cuerpo (separado de los encabezados por dos retornos de carro o avances de línea) al mensaje AS2 antes de enviarlo.</span><span class="sxs-lookup"><span data-stu-id="6ab45-120">Ensure the sending party adds a body (separated from the headers by two carriage return/line feeds) to the AS2 message before sending it.</span></span>