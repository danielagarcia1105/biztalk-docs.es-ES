---
title: Identificador de estándar de Control no válido. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d2b5a54-7f29-49c9-8bcf-a5b4b6d07ad3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cadbb2ed9458199433b62ecb918668fda8a1def0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966237"
---
# <a name="invalid-control-standard-identifier"></a><span data-ttu-id="318a6-102">Identificador de estándar de control no válido.</span><span class="sxs-lookup"><span data-stu-id="318a6-102">Invalid Control Standard Identifier</span></span>
## <a name="details"></a><span data-ttu-id="318a6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="318a6-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="318a6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="318a6-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="318a6-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="318a6-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="318a6-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="318a6-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="318a6-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="318a6-107">Event Source</span></span>   | <span data-ttu-id="318a6-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="318a6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="318a6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="318a6-109">Component</span></span>    |                                       <span data-ttu-id="318a6-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="318a6-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="318a6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="318a6-111">Symbolic Name</span></span>  |                   <span data-ttu-id="318a6-112">X12Ta1InvalidControlStandardIdentifierDescription</span><span class="sxs-lookup"><span data-stu-id="318a6-112">X12Ta1InvalidControlStandardIdentifierDescription</span></span>                    |
|  <span data-ttu-id="318a6-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="318a6-113">Message Text</span></span>   |                          <span data-ttu-id="318a6-114">Identificador de estándar de control no válido.</span><span class="sxs-lookup"><span data-stu-id="318a6-114">Invalid Control Standard Identifier</span></span>                           |
  
## <a name="explanation"></a><span data-ttu-id="318a6-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="318a6-115">Explanation</span></span>  
 <span data-ttu-id="318a6-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del identificador de estándar de control de intercambio (campo ISA11) del intercambio no coincidía con una entrada en la enumeración que especifica el esquema.</span><span class="sxs-lookup"><span data-stu-id="318a6-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the interchange control standards identifier (field ISA11) in the interchange did not match an entry in the enumeration specified by the schema.</span></span> <span data-ttu-id="318a6-117">El esquema es X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll.</span><span class="sxs-lookup"><span data-stu-id="318a6-117">The schema is the X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="318a6-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="318a6-118">User Action</span></span>  
 <span data-ttu-id="318a6-119">Para resolver este error, asegúrese de que el identificador de estándar de control de intercambio usado en el intercambio coincide con una entrada en la enumeración para el campo ISA11 y, a continuación, reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="318a6-119">To resolve this error, make sure that the interchange control standards identifier used in the interchange matches an entry in the enumeration for the ISA11 field, and then have the interchange resent.</span></span>