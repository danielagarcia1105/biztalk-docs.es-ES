---
title: Id. de destinatario no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feabf940-c49b-4f4a-8906-230dc8fb1b30
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f38b480c7c7ada535a921e285e885bcb3bfa9c6c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024346"
---
# <a name="invalid-receiverid"></a><span data-ttu-id="cc77c-102">Id. de destinatario no válido.</span><span class="sxs-lookup"><span data-stu-id="cc77c-102">Invalid ReceiverId</span></span>
## <a name="details"></a><span data-ttu-id="cc77c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cc77c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="cc77c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cc77c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="cc77c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cc77c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="cc77c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cc77c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="cc77c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cc77c-107">Event Source</span></span>   | <span data-ttu-id="cc77c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc77c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="cc77c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="cc77c-109">Component</span></span>    |                                       <span data-ttu-id="cc77c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="cc77c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="cc77c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cc77c-111">Symbolic Name</span></span>  |                           <span data-ttu-id="cc77c-112">X12Ta1InvalidReceiverIdDescription</span><span class="sxs-lookup"><span data-stu-id="cc77c-112">X12Ta1InvalidReceiverIdDescription</span></span>                           |
|  <span data-ttu-id="cc77c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cc77c-113">Message Text</span></span>   |                                   <span data-ttu-id="cc77c-114">Id. de destinatario no válido.</span><span class="sxs-lookup"><span data-stu-id="cc77c-114">Invalid ReceiverId</span></span>                                   |
  
## <a name="explanation"></a><span data-ttu-id="cc77c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="cc77c-115">Explanation</span></span>  
 <span data-ttu-id="cc77c-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque el identificador de receptor en el campo ISA08 o la identificación de destinatario en el campo UNB3.1 no se ajustaba al tipo de datos y al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="cc77c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Receiver ID in the ISA08 field or the Recipient Identification in the UNB3.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cc77c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cc77c-117">User Action</span></span>  
 <span data-ttu-id="cc77c-118">Para resolver este error, asegúrese de que el campo ISA08 sea del tipo de datos X12_AN y tenga una longitud de 15 caracteres (con o sin espacios finales) o de que el campo UNB3.1 sea del tipo de datos EDIFACT_AN y tenga entre 1 y 35 caracteres.</span><span class="sxs-lookup"><span data-stu-id="cc77c-118">To resolve this error, make sure that the ISA08 field is of the X12_AN data type and is 15 characters long (with or without trailing spaces) or that the UNB3.1 field is of the EDIFACT_AN data type and is between 1 and 35 characters.</span></span> <span data-ttu-id="cc77c-119">Vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="cc77c-119">Have the interchange resent.</span></span>