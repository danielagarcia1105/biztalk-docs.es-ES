---
title: El descodificador AS2 no pudo procesar al validar el valor MIC devuelto en MDN | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fe2d76d-b0f1-4118-8483-547c2c9fffb7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b15ec1518e4736052e31254283db66395d87fb6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985845"
---
# <a name="the-as2-decoder-failed-processing-when-validating-the-mic-value-returned-in-the-mdn"></a><span data-ttu-id="2960a-102">Error de procesamiento de descodificador AS2 al validar el valor MIC devuelto en MDN</span><span class="sxs-lookup"><span data-stu-id="2960a-102">The AS2 Decoder failed processing when validating the MIC value returned in the MDN</span></span>
## <a name="details"></a><span data-ttu-id="2960a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2960a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2960a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2960a-104">Product Name</span></span>   |                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="2960a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2960a-105">Product Version</span></span> |                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    <span data-ttu-id="2960a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2960a-106">Event ID</span></span>     |                                                                                                   -                                                                                                   |
|  <span data-ttu-id="2960a-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2960a-107">Event Source</span></span>   |                                                        <span data-ttu-id="2960a-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2960a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                         |
|    <span data-ttu-id="2960a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2960a-109">Component</span></span>    |                                                                                              <span data-ttu-id="2960a-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="2960a-110">AS2 Engine</span></span>                                                                                               |
|  <span data-ttu-id="2960a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2960a-111">Symbolic Name</span></span>  |                                                                                <span data-ttu-id="2960a-112">AS2DecoderMdnMicFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="2960a-112">AS2DecoderMdnMicFailureDuringProcessing</span></span>                                                                                |
|  <span data-ttu-id="2960a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2960a-113">Message Text</span></span>   | <span data-ttu-id="2960a-114">Error de procesamiento de descodificador AS2 al validar el valor MIC devuelto en MDN.</span><span class="sxs-lookup"><span data-stu-id="2960a-114">The AS2 Decoder failed processing when validating the MIC value returned in the MDN.</span></span>  <span data-ttu-id="2960a-115">Detalles del mensaje MDN son los siguientes: AS2-de: "{0}" AS2-para: "{1}" MessageID: "{2}" OriginalMessageID: "{3}"</span><span class="sxs-lookup"><span data-stu-id="2960a-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2960a-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="2960a-116">Explanation</span></span>  
 <span data-ttu-id="2960a-117">Este evento de error,  indica que la canalización de recepción no pudo procesar el MDN entrante debido a que la comprobación de integridad del mensaje (MIC) no se pudo validar.</span><span class="sxs-lookup"><span data-stu-id="2960a-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN because the MIC (Message Integrity Check) failed validation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2960a-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2960a-118">User Action</span></span>  
 <span data-ttu-id="2960a-119">Para resolver este error, compruebe que el algoritmo que se usa para la generación del MDN (en el encabezado Signed-Receipt-MICalg del mensaje original) es el mismo que el algoritmo especificado en la propiedad Signed-Receipt-MICalg para el receptor del mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="2960a-119">To resolve this error, verify that the algorithm used for generating the MDN (in the Signed-Receipt-MICalg header of the original message) is the same as the algorithm specified in the Signed-Receipt-MICalg property for the AS2 Message Receiver.</span></span> <span data-ttu-id="2960a-120">Ambos deben ser SHA1 o MD5.</span><span class="sxs-lookup"><span data-stu-id="2960a-120">Both should be either SHA1 or MD5.</span></span> <span data-ttu-id="2960a-121">Si el algoritmo especificado es el mismo, compruebe que el campo de extensión Received-Content-MIC en la segunda parte del mensaje MDN firmado con varias partes incluye una síntesis de MIC válida.</span><span class="sxs-lookup"><span data-stu-id="2960a-121">If the algorithm specified is the same, verify that Received-Content-MIC extension field in the second part of the multipart signed MDN message includes a valid MIC digest.</span></span> <span data-ttu-id="2960a-122">Si es así, determine por qué el MDN no se corresponde con el intercambio que se ha enviado.</span><span class="sxs-lookup"><span data-stu-id="2960a-122">If it does, determine why the MDN does not correspond to the interchange that was sent.</span></span>