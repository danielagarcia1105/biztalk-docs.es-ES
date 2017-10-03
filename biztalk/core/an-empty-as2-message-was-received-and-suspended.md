---
title: "Se recibió un mensaje AS2 vacío y se suspendió | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 349f7134-d039-44ab-b2b3-d378d38dfd38
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90c8221c7e0bd5b297b33118b8672fbe55612244
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="an-empty-as2-message-was-received-and-suspended"></a><span data-ttu-id="c1c2c-102">Se recibió y suspendió un mensaje AS2 vacío</span><span class="sxs-lookup"><span data-stu-id="c1c2c-102">An empty AS2 message was received and suspended</span></span>
## <a name="details"></a><span data-ttu-id="c1c2c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c1c2c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1c2c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c1c2c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c1c2c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c1c2c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c1c2c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c1c2c-106">Event ID</span></span>|-|  
|<span data-ttu-id="c1c2c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c1c2c-107">Event Source</span></span>|<span data-ttu-id="c1c2c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c2c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="c1c2c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c1c2c-109">Component</span></span>|<span data-ttu-id="c1c2c-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="c1c2c-110">AS2 Engine</span></span>|  
|<span data-ttu-id="c1c2c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c1c2c-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="c1c2c-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c1c2c-112">Message Text</span></span>|<span data-ttu-id="c1c2c-113">Se recibió un mensaje AS2 vacío.</span><span class="sxs-lookup"><span data-stu-id="c1c2c-113">An empty AS2 message was received.</span></span>  <span data-ttu-id="c1c2c-114">El mensaje se suspenderá.</span><span class="sxs-lookup"><span data-stu-id="c1c2c-114">The message will be suspended.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c1c2c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c1c2c-115">Explanation</span></span>  
 <span data-ttu-id="c1c2c-116">Este evento de error,  indica que BizTalk Server no pudo procesar el mensaje AS2 entrante porque el mensaje no contiene cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c1c2c-116">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message does not contain a body.</span></span> <span data-ttu-id="c1c2c-117">El cuerpo debe estar separado de los encabezados por dos retornos de carro o avances de línea.</span><span class="sxs-lookup"><span data-stu-id="c1c2c-117">The body must be separated from the headers by two carriage return/line feeds.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c1c2c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c1c2c-118">User Action</span></span>  
 <span data-ttu-id="c1c2c-119">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1c2c-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="c1c2c-120">Asegúrese de que la entidad remitente agrega un cuerpo (separado de los encabezados por dos retornos de carro o avances de línea) al mensaje AS2 antes de enviarlo.</span><span class="sxs-lookup"><span data-stu-id="c1c2c-120">Ensure the sending party adds a body (separated from the headers by two carriage return/line feeds) to the AS2 message before sending it.</span></span>