---
title: Id. de remitente no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be8055ab-8aba-49ac-ad33-fb33d4ff3e8b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7517adcd214f789c8af37d4abce2478e6da20507
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976541"
---
# <a name="invalid-senderid"></a><span data-ttu-id="ac12d-102">Id. de remitente no válido.</span><span class="sxs-lookup"><span data-stu-id="ac12d-102">Invalid SenderId</span></span>
## <a name="details"></a><span data-ttu-id="ac12d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ac12d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ac12d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ac12d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ac12d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ac12d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ac12d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ac12d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ac12d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ac12d-107">Event Source</span></span>   | <span data-ttu-id="ac12d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac12d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="ac12d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ac12d-109">Component</span></span>    |                                       <span data-ttu-id="ac12d-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ac12d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ac12d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ac12d-111">Symbolic Name</span></span>  |                            <span data-ttu-id="ac12d-112">X12Ta1InvalidSenderIdDescription</span><span class="sxs-lookup"><span data-stu-id="ac12d-112">X12Ta1InvalidSenderIdDescription</span></span>                            |
|  <span data-ttu-id="ac12d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ac12d-113">Message Text</span></span>   |                                    <span data-ttu-id="ac12d-114">Id. de remitente no válido.</span><span class="sxs-lookup"><span data-stu-id="ac12d-114">Invalid SenderId</span></span>                                    |
  
## <a name="explanation"></a><span data-ttu-id="ac12d-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="ac12d-115">Explanation</span></span>  
 <span data-ttu-id="ac12d-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el identificador de remitente en el campo ISA06 o la identificación de remitente en el campo UNB2.1 no se ajustaba al tipo de datos y al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="ac12d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Sender ID in the ISA06 field or the Sender Identification in the UNB2.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ac12d-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ac12d-117">User Action</span></span>  
 <span data-ttu-id="ac12d-118">Para resolver este error, asegúrese de que el campo ISA06 sea del tipo de datos X12_AN y tenga una longitud de 15 caracteres (con o sin espacios finales) o de que el campo UNB2.1 sea del tipo de datos EDIFACT_AN y tenga entre 1 y 35 caracteres.</span><span class="sxs-lookup"><span data-stu-id="ac12d-118">To resolve this error, make sure that the ISA06 field is of the X12_AN data type and is 15 characters long (with or without trailing spaces) or that the UNB2.1 field is of the EDIFACT_AN data type and is between 1 and 35 characters.</span></span> <span data-ttu-id="ac12d-119">Vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="ac12d-119">Have the interchange resent.</span></span>