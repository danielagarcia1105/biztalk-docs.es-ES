---
title: El descodificador AS2 no pudo procesar la firma MDN no cumplía nuestra solicitud | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a42d344-fc28-4bc4-9328-46158f15a008
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a4d5cb5cd1825f5620ab39e4c770eb9818a5ade
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978879"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a><span data-ttu-id="20305-102">Error de procesamiento de descodificador AS2. La firma MDN no cumplía nuestra solicitud</span><span class="sxs-lookup"><span data-stu-id="20305-102">The AS2 Decoder failed processing because the MDN signing did not match our request</span></span>
## <a name="details"></a><span data-ttu-id="20305-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="20305-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="20305-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="20305-104">Product Name</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="20305-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="20305-105">Product Version</span></span> |                                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    <span data-ttu-id="20305-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="20305-106">Event ID</span></span>     |                                                                                                   -                                                                                                    |
|  <span data-ttu-id="20305-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="20305-107">Event Source</span></span>   |                                                         <span data-ttu-id="20305-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20305-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                         |
|    <span data-ttu-id="20305-109">Componente</span><span class="sxs-lookup"><span data-stu-id="20305-109">Component</span></span>    |                                                                                               <span data-ttu-id="20305-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="20305-110">AS2 Engine</span></span>                                                                                               |
|  <span data-ttu-id="20305-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="20305-111">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="20305-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="20305-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span></span>                                                                           |
|  <span data-ttu-id="20305-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="20305-113">Message Text</span></span>   | <span data-ttu-id="20305-114">Error de procesamiento de descodificador AS2. La firma MDN no cumplía nuestra solicitud.</span><span class="sxs-lookup"><span data-stu-id="20305-114">The AS2 Decoder failure processing because the MDN signing did not match our request.</span></span>  <span data-ttu-id="20305-115">Detalles del mensaje MDN son los siguientes: AS2-de: "{0}" AS2-para: "{1}" MessageID: "{2}" OriginalMessageID: "{3}"</span><span class="sxs-lookup"><span data-stu-id="20305-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="20305-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="20305-116">Explanation</span></span>  
 <span data-ttu-id="20305-117">Este evento de error,  indica que la canalización de recepción no pudo procesar el MDN entrante porque el MDN estaba firmado y no se solicitaba la firma para él o que el MDN estaba sin firmar y se solicitaba la firma para él.</span><span class="sxs-lookup"><span data-stu-id="20305-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN either because the MDN was signed, but signing wasn't requested for the MDN, or the MDN was unsigned, but signing was requested for the MDN.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="20305-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="20305-118">User Action</span></span>  
 <span data-ttu-id="20305-119">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="20305-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="20305-120">Cambie la solicitud de firma para que el MDN coincida con la solicitud.</span><span class="sxs-lookup"><span data-stu-id="20305-120">Change the signature request for the MDN to match the request.</span></span> <span data-ttu-id="20305-121">Para ello, abra la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2 y, con la propiedad "Solicitar MDN" seleccionada, seleccione o desactive la propiedad "Solicitar MDN firmado".</span><span class="sxs-lookup"><span data-stu-id="20305-121">To do so, open the Party as AS2 Message Receiver page of the AS2 Properties dialog box, and with the "Request MDN" property selected, either select or clear the "Request signed MDN" property.</span></span>  
  
2.  <span data-ttu-id="20305-122">Póngase en contacto con el receptor del mensaje AS2 original para resolver si los MDN deben firmarse o no.</span><span class="sxs-lookup"><span data-stu-id="20305-122">Contact the receiver of the original AS2 message to resolve whether MDNs should be signed or not.</span></span>