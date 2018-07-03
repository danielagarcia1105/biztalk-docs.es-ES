---
title: No se admite el algoritmo hash especificado en el mensaje AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b292238-f964-4275-bbfa-e21c9150abf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c3c46f65fb71ef810fc4e657df01e0065757cae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008597"
---
# <a name="the-hash-algorithm-specified-in-the-as2-message-is-unsupported"></a><span data-ttu-id="40a72-102">El algoritmo de hash especificado en el mensaje AS2 no es compatible</span><span class="sxs-lookup"><span data-stu-id="40a72-102">The hash algorithm specified in the AS2 message is unsupported</span></span>
## <a name="details"></a><span data-ttu-id="40a72-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="40a72-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="40a72-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="40a72-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="40a72-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="40a72-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="40a72-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="40a72-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="40a72-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="40a72-107">Event Source</span></span>   | <span data-ttu-id="40a72-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40a72-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="40a72-109">Componente</span><span class="sxs-lookup"><span data-stu-id="40a72-109">Component</span></span>    |                                       <span data-ttu-id="40a72-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="40a72-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="40a72-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="40a72-111">Symbolic Name</span></span>  |                            <span data-ttu-id="40a72-112">UnsupportedAS2HashAlgorithmError</span><span class="sxs-lookup"><span data-stu-id="40a72-112">UnsupportedAS2HashAlgorithmError</span></span>                            |
|  <span data-ttu-id="40a72-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="40a72-113">Message Text</span></span>   |            <span data-ttu-id="40a72-114">El algoritmo de hash especificado en el mensaje AS2 no es compatible.</span><span class="sxs-lookup"><span data-stu-id="40a72-114">The hash algorithm specified in the AS2 message is unsupported.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="40a72-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="40a72-115">Explanation</span></span>  
 <span data-ttu-id="40a72-116">Este evento de error,  indica que la canalización de recepción no pudo generar el MDN según se ha especificado porque el algoritmo hash MIC especificado en el encabezado signed-receipt-micalg del mensaje AS2 recibido no es un valor válido.</span><span class="sxs-lookup"><span data-stu-id="40a72-116">This Error/Warning/Information event indicates that the receive pipeline could not generate the MDN as specified because the MIC hash algorithm specified in the signed-receipt-micalg header of the received AS2 message is not a valid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="40a72-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="40a72-117">User Action</span></span>  
 <span data-ttu-id="40a72-118">Para resolver este error, haga que el remitente del mensaje cambie el algoritmo a MD5 o SHA1 y reenvíe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="40a72-118">To resolve this error, have the sender of the message change the algorithm to either MD5 or SHA1, and resend the message.</span></span>