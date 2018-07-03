---
title: Infringido de condición de exclusión | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e508da6-7edc-45c0-a7ab-f23337dc1b54
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93e55595eaf2903ead7319b5f0269f803a3a83e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968741"
---
# <a name="exclusion-condition-violated"></a><span data-ttu-id="9ade6-102">Infracción de condición de exclusión</span><span class="sxs-lookup"><span data-stu-id="9ade6-102">Exclusion Condition Violated</span></span>
## <a name="details"></a><span data-ttu-id="9ade6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9ade6-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9ade6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9ade6-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9ade6-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9ade6-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9ade6-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9ade6-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9ade6-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9ade6-107">Event Source</span></span>   | <span data-ttu-id="9ade6-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ade6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="9ade6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="9ade6-109">Component</span></span>    |                                       <span data-ttu-id="9ade6-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="9ade6-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="9ade6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9ade6-111">Symbolic Name</span></span>  |                       <span data-ttu-id="9ade6-112">X12DeExclusionConditionViolatedDescription</span><span class="sxs-lookup"><span data-stu-id="9ade6-112">X12DeExclusionConditionViolatedDescription</span></span>                       |
|  <span data-ttu-id="9ade6-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9ade6-113">Message Text</span></span>   |       <span data-ttu-id="9ade6-114">Infracción de condición de exclusión. Vea el valor del campo de la instancia para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="9ade6-114">Exclusion Condition Violated, refer to field value in instance for details</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="9ade6-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="9ade6-115">Explanation</span></span>  
 <span data-ttu-id="9ade6-116">Este evento de error,  indica que no se pudo validar un intercambio X12 en tiempo de diseño (mediante la herramienta de validación XML) o bien en tiempo de ejecución, bien en la recepción o bien en el envío, debido a que un segmento de la instancia no superó una regla de exclusión de la validación de campos cruzados.</span><span class="sxs-lookup"><span data-stu-id="9ade6-116">This Error/Warning/Information event indicates that validation of an X12 interchange failed either at design time (using the XML validation tool) or at run time, on either the receive side or the send side, because a segment in the instance failed a cross-field validation exclusion rule.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9ade6-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9ade6-117">User Action</span></span>  
 <span data-ttu-id="9ade6-118">Para resolver este error, asegúrese de modificar el segmento que tuvo un error en la regla de exclusión de modo que supere la validación de campo cruzado y, a continuación, vuelva a ejecutar el proceso de validación.</span><span class="sxs-lookup"><span data-stu-id="9ade6-118">To resolve this error, ensure that the segment that failed the exclusion rule is changed so that it passes cross-field validation, and then run the validation process again.</span></span>