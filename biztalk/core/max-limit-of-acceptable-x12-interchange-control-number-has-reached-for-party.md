---
title: El límite máximo aceptable X12 ha alcanzado el número de control de intercambio para la entidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc49089-3c7b-4ce2-9fbc-68e582c3a822
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de22f059a720fdec999f495f38a6b21009469158
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986309"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-party"></a><span data-ttu-id="ea2ac-102">Se ha alcanzado el límite máximo permitido del número de control de intercambio X12 para la entidad</span><span class="sxs-lookup"><span data-stu-id="ea2ac-102">Max limit of acceptable X12 interchange control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="ea2ac-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ea2ac-103">Details</span></span>  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ea2ac-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ea2ac-104">Product Name</span></span>   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| <span data-ttu-id="ea2ac-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ea2ac-105">Product Version</span></span> |                                                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    <span data-ttu-id="ea2ac-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ea2ac-106">Event ID</span></span>     |                                                                                             -                                                                                             |
|  <span data-ttu-id="ea2ac-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ea2ac-107">Event Source</span></span>   |                                                  <span data-ttu-id="ea2ac-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea2ac-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                   |
|    <span data-ttu-id="ea2ac-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ea2ac-109">Component</span></span>    |                                                                                        <span data-ttu-id="ea2ac-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ea2ac-110">EDI Engine</span></span>                                                                                         |
|  <span data-ttu-id="ea2ac-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ea2ac-111">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="ea2ac-112">PartyX12IsaNumberError</span><span class="sxs-lookup"><span data-stu-id="ea2ac-112">PartyX12IsaNumberError</span></span>                                                                                   |
|  <span data-ttu-id="ea2ac-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ea2ac-113">Message Text</span></span>   | <span data-ttu-id="ea2ac-114">El límite máximo aceptable X12 ha alcanzado el número de control de intercambio para la entidad {0}.</span><span class="sxs-lookup"><span data-stu-id="ea2ac-114">Max limit of acceptable X12 interchange control number has reached for party {0}.</span></span> <span data-ttu-id="ea2ac-115">Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo ISA 13, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="ea2ac-115">Reset counter by navigating to Party in receiver role screen, field ISA 13 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ea2ac-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ea2ac-116">Explanation</span></span>  
 <span data-ttu-id="ea2ac-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control de intercambio del campo ISA13 especificado en la configuración de la entidad era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="ea2ac-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the interchange control number in the ISA13 field specified in the party settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="ea2ac-118">El número máximo de caracteres es nueve para el número de control de intercambio.</span><span class="sxs-lookup"><span data-stu-id="ea2ac-118">The maximum number of characters for the interchange control number is nine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ea2ac-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ea2ac-119">User Action</span></span>  
 <span data-ttu-id="ea2ac-120">Para resolver este error, restablezca el número de control de intercambio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="ea2ac-120">To resolve this error, reset the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="ea2ac-121">En el cuadro de diálogo Propiedades de EDI para la entidad resuelta para el intercambio, abra la página Definición de segmento ISA para la entidad como receptora del intercambio.</span><span class="sxs-lookup"><span data-stu-id="ea2ac-121">In the EDI Properties dialog box for the party resolved for the interchange, open the ISA Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="ea2ac-122">Haga clic en el campo Editar asociado con el campo ISA13.</span><span class="sxs-lookup"><span data-stu-id="ea2ac-122">Click the Edit field associated with the ISA13 field.</span></span>  
  
3.  <span data-ttu-id="ea2ac-123">Defina el número de control de intercambio en un valor nuevo, de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="ea2ac-123">Set the interchange control number to a new value such that the field has an acceptable number of digits.</span></span>