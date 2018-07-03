---
title: Error de descompresión al procesar un mensaje AS2 comprimido. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5246ee97-cc60-4878-9447-de870c0f4c34
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c77bead00b97bf6fa072223485f2d1cc422053b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001893"
---
# <a name="decompression-failed-while-processing-a-compressed-as2-message"></a><span data-ttu-id="e4ea2-103">Error de descompresión al procesar un mensaje AS2 comprimido.</span><span class="sxs-lookup"><span data-stu-id="e4ea2-103">Decompression failed while processing a compressed AS2 message.</span></span>
## <a name="details"></a><span data-ttu-id="e4ea2-104">Detalles</span><span class="sxs-lookup"><span data-stu-id="e4ea2-104">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e4ea2-105">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e4ea2-105">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e4ea2-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e4ea2-106">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e4ea2-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e4ea2-107">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e4ea2-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e4ea2-108">Event Source</span></span>   | <span data-ttu-id="e4ea2-109">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4ea2-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="e4ea2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e4ea2-110">Component</span></span>    |                                       <span data-ttu-id="e4ea2-111">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="e4ea2-111">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="e4ea2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e4ea2-112">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="e4ea2-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e4ea2-113">Message Text</span></span>   |       <span data-ttu-id="e4ea2-114">Error de descompresión al procesar un mensaje AS2 comprimido.</span><span class="sxs-lookup"><span data-stu-id="e4ea2-114">Decompression failed while processing a compressed AS2 message.</span></span> <span data-ttu-id="e4ea2-115">Error: {0}</span><span class="sxs-lookup"><span data-stu-id="e4ea2-115">Error: {0}</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="e4ea2-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="e4ea2-116">Explanation</span></span>  
 <span data-ttu-id="e4ea2-117">Este evento de error,  indica que la canalización de recepción o el componente de descodificador AS2 no pudo descomprimir el mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="e4ea2-117">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not decompress the AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e4ea2-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e4ea2-118">User Action</span></span>  
 <span data-ttu-id="e4ea2-119">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e4ea2-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="e4ea2-120">Compruebe que el contenedor de compresión del mensaje AS2 es válido.</span><span class="sxs-lookup"><span data-stu-id="e4ea2-120">Verify that the compression wrapper in the AS2 message is valid.</span></span>  
  
-   <span data-ttu-id="e4ea2-121">Compruebe que la descompresión está habilitada para BizTalk Server. Para ello, compruebe que la propiedad "Debe comprimirse el mensaje" está activada en la página Entidad como remitente del mensaje AS2 del cuadro de diálogo Propiedades de AS2 (si está activada la propiedad Invalidar propiedades de mensajes entrantes).</span><span class="sxs-lookup"><span data-stu-id="e4ea2-121">Verify that decompression is enabled for BizTalk Server by verifying that the "Message should be compressed" property is checked on the Party as AS2 Message Sender page of the AS2 Properties dialog box (if the Override inbound message properties property is checked).</span></span>  
  
-   <span data-ttu-id="e4ea2-122">Use la descripción del error proporcionada en el texto del mensaje de error para identificar el problema específico.</span><span class="sxs-lookup"><span data-stu-id="e4ea2-122">Use the error description provided in the error message text to identify the specific issue.</span></span>