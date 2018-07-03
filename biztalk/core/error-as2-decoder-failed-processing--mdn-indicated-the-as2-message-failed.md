---
title: El descodificador AS2 no pudo procesar el MDN indicó el procesamiento del mensaje error de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bce620a-f336-435e-b7c3-3db060f2819d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 240c90d488d313bf43982c7c98db3e8a1ea05e75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984501"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-indicated-the-as2-message-failed-processing"></a><span data-ttu-id="aac34-102">Error de procesamiento de descodificador AS2. MDN indicó un error de procesamiento del mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="aac34-102">The AS2 Decoder failed processing because the MDN indicated the AS2 message failed processing</span></span>
## <a name="details"></a><span data-ttu-id="aac34-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="aac34-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="aac34-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="aac34-104">Product Name</span></span>   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| <span data-ttu-id="aac34-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="aac34-105">Product Version</span></span> |                                                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                            |
|    <span data-ttu-id="aac34-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="aac34-106">Event ID</span></span>     |                                                                                                        -                                                                                                         |
|  <span data-ttu-id="aac34-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="aac34-107">Event Source</span></span>   |                                                              <span data-ttu-id="aac34-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aac34-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                              |
|    <span data-ttu-id="aac34-109">Componente</span><span class="sxs-lookup"><span data-stu-id="aac34-109">Component</span></span>    |                                                                                                    <span data-ttu-id="aac34-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="aac34-110">AS2 Engine</span></span>                                                                                                    |
|  <span data-ttu-id="aac34-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="aac34-111">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="aac34-112">AS2DecoderMdnProcessingFailureReturned</span><span class="sxs-lookup"><span data-stu-id="aac34-112">AS2DecoderMdnProcessingFailureReturned</span></span>                                                                                      |
|  <span data-ttu-id="aac34-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="aac34-113">Message Text</span></span>   | <span data-ttu-id="aac34-114">Error de procesamiento de descodificador AS2. MDN indicó un error de procesamiento del mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="aac34-114">The AS2 Decoder failure processing because the MDN indicated the AS2 message failed processing.</span></span>  <span data-ttu-id="aac34-115">Detalles del mensaje MDN son los siguientes: AS2-de: "{0}" AS2-para: "{1}" MessageID: "{2}" OriginalMessageID: "{3}"</span><span class="sxs-lookup"><span data-stu-id="aac34-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="aac34-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="aac34-116">Explanation</span></span>  
 <span data-ttu-id="aac34-117">Este evento de error,  indica que la respuesta de MDN indica que el receptor del mensaje AS2 original no pudo procesar el mensaje AS2 original.</span><span class="sxs-lookup"><span data-stu-id="aac34-117">This Error/Warning/Information event indicates that the MDN response shows that the receiver of the original AS2 message could not process the original AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aac34-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="aac34-118">User Action</span></span>  
 <span data-ttu-id="aac34-119">Para resolver este error, póngase en contacto con el receptor del mensaje AS2, determine por qué se ha producido un error en el destinatario, corrija el mensaje AS2 original y vuelva a enviarlo.</span><span class="sxs-lookup"><span data-stu-id="aac34-119">To resolve this error, contact the receiver of the AS2 message, determine why processing failed at the receiver, fix the original AS2 message, and then resend.</span></span>