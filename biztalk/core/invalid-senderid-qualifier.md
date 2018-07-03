---
title: Calificador de Id. de remitente no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfe9c51c-d569-4f14-a690-f145ef1bf6a4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbe4b48e4e90443539b70c591750acf038be6e6b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014701"
---
# <a name="invalid-senderid-qualifier"></a><span data-ttu-id="c3f72-102">Calificador de Id. de remitente no válido.</span><span class="sxs-lookup"><span data-stu-id="c3f72-102">Invalid SenderId Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="c3f72-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c3f72-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c3f72-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c3f72-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c3f72-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c3f72-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c3f72-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c3f72-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c3f72-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c3f72-107">Event Source</span></span>   | <span data-ttu-id="c3f72-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3f72-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="c3f72-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c3f72-109">Component</span></span>    |                                       <span data-ttu-id="c3f72-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c3f72-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c3f72-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c3f72-111">Symbolic Name</span></span>  |                       <span data-ttu-id="c3f72-112">X12Ta1InvalidSenderIdQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="c3f72-112">X12Ta1InvalidSenderIdQualifierDescription</span></span>                        |
|  <span data-ttu-id="c3f72-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c3f72-113">Message Text</span></span>   |                               <span data-ttu-id="c3f72-114">Calificador de Id. de remitente no válido.</span><span class="sxs-lookup"><span data-stu-id="c3f72-114">Invalid SenderId Qualifier</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="c3f72-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c3f72-115">Explanation</span></span>  
 <span data-ttu-id="c3f72-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el calificador de remitente en el campo ISA05 (para un intercambio X12) o el calificador de código de remitente en el campo UNB2.2 (para un intercambio EDIFACT) no coincidía con un valor en la enumeración que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="c3f72-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Sender Qualifier in the ISA05 field (for an X12 interchange) or the Sender Code Qualifier in the UNB2.2 field (for an EDIFACT interchange) did not match a value in the enumeration established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c3f72-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c3f72-117">User Action</span></span>  
 <span data-ttu-id="c3f72-118">Para resolver este error, asegúrese de que el campo ISA07 o el campo UNB3.2 coincide con uno de los valores de la enumeración que establece el esquema de servicio.</span><span class="sxs-lookup"><span data-stu-id="c3f72-118">To resolve this error, make sure that the ISA07 field or the UNB3.2 field matches one of the values in the enumeration established by the service schema.</span></span> <span data-ttu-id="c3f72-119">Vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="c3f72-119">Have the interchange resent.</span></span>