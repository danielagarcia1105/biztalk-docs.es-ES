---
title: El límite máximo aceptable X12 ha alcanzado el número de control de grupo funcional para la entidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a920a66c-1e38-4f4a-8113-cbad01940839
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 527f6709d48124f7ffcc0823bdc5ff84e92256ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978405"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-party"></a><span data-ttu-id="b477e-102">Se ha alcanzado el límite máximo permitido del número de control de grupo funcional X12 para la entidad</span><span class="sxs-lookup"><span data-stu-id="b477e-102">Max limit of acceptable X12 functional group control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="b477e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b477e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b477e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b477e-104">Product Name</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="b477e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b477e-105">Product Version</span></span> |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="b477e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b477e-106">Event ID</span></span>     |                                                                                              -                                                                                               |
|  <span data-ttu-id="b477e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b477e-107">Event Source</span></span>   |                                                    <span data-ttu-id="b477e-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b477e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                    |
|    <span data-ttu-id="b477e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b477e-109">Component</span></span>    |                                                                                          <span data-ttu-id="b477e-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="b477e-110">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="b477e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b477e-111">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="b477e-112">PartyX12GsNumberError</span><span class="sxs-lookup"><span data-stu-id="b477e-112">PartyX12GsNumberError</span></span>                                                                                     |
|  <span data-ttu-id="b477e-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b477e-113">Message Text</span></span>   | <span data-ttu-id="b477e-114">El límite máximo aceptable X12 ha alcanzado el número de control de grupo funcional para la entidad {0}.</span><span class="sxs-lookup"><span data-stu-id="b477e-114">Max limit of acceptable X12 functional group control number has reached for party {0}.</span></span> <span data-ttu-id="b477e-115">Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo GS 6, del administrador de acuerdos de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="b477e-115">Reset counter by navigating to Party in receiver role screen, field GS 6 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b477e-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="b477e-116">Explanation</span></span>  
 <span data-ttu-id="b477e-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control de grupo del campo GS06 especificado en la configuración de entidad era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="b477e-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the group control number in the GS06 field specified in the party settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="b477e-118">El número máximo de caracteres es 9 para el número de control de grupo.</span><span class="sxs-lookup"><span data-stu-id="b477e-118">The maximum number of characters for the group control number is 9.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b477e-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b477e-119">User Action</span></span>  
 <span data-ttu-id="b477e-120">Para resolver este error, restablezca el número de control de grupo tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b477e-120">To resolve this error, reset the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="b477e-121">En el cuadro de diálogo Propiedades de EDI para la entidad resuelta para el intercambio, abra la página Definición de segmentos GS y ST para la entidad como receptor de intercambio.</span><span class="sxs-lookup"><span data-stu-id="b477e-121">In the EDI Properties dialog box for the party resolved for the interchange, open the GS and ST Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="b477e-122">Haga clic en el campo Editar asociado con el campo GS06.</span><span class="sxs-lookup"><span data-stu-id="b477e-122">Click the Edit field associated with the GS06 field.</span></span>  
  
3.  <span data-ttu-id="b477e-123">Defina el número de control de grupo en un valor nuevo, de modo que el campo tenga nueve dígitos o menos.</span><span class="sxs-lookup"><span data-stu-id="b477e-123">Set the group control number to a new value such that the field has nine or fewer digits.</span></span>