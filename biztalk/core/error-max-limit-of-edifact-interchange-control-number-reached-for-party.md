---
title: Ha alcanzado el límite máximo del número aceptable de control de intercambio de Edifact para la entidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c00c357-4c7b-42ea-a031-15bad0195a75
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c11029af5b2f87e4e1bf3e7fc4225bfc5ba46105
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998205"
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-party"></a><span data-ttu-id="5d91d-102">Se ha alcanzado el límite máximo permitido del número de control de intercambio Edifact para la entidad</span><span class="sxs-lookup"><span data-stu-id="5d91d-102">Max limit of acceptable Edifact interchange control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="5d91d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d91d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5d91d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5d91d-104">Product Name</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="5d91d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5d91d-105">Product Version</span></span> |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="5d91d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5d91d-106">Event ID</span></span>     |                                                                                              -                                                                                               |
|  <span data-ttu-id="5d91d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5d91d-107">Event Source</span></span>   |                                                    <span data-ttu-id="5d91d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d91d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                    |
|    <span data-ttu-id="5d91d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5d91d-109">Component</span></span>    |                                                                                          <span data-ttu-id="5d91d-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="5d91d-110">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="5d91d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5d91d-111">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="5d91d-112">PartyEdifactUnbNumberError</span><span class="sxs-lookup"><span data-stu-id="5d91d-112">PartyEdifactUnbNumberError</span></span>                                                                                  |
|  <span data-ttu-id="5d91d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5d91d-113">Message Text</span></span>   | <span data-ttu-id="5d91d-114">Ha alcanzado el límite máximo del número aceptable de control de intercambio de Edifact para la entidad {0}.</span><span class="sxs-lookup"><span data-stu-id="5d91d-114">Max limit of acceptable Edifact interchange control number has reached for party {0}.</span></span> <span data-ttu-id="5d91d-115">Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo UNB 5, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="5d91d-115">Reset counter by navigating to Party in receiver role screen, field UNB 5 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5d91d-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="5d91d-116">Explanation</span></span>  
 <span data-ttu-id="5d91d-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control de intercambio en el campo UNB5 especificado en la configuración de la entidad, específicamente el número de referencia en el campo UNB5.2, era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="5d91d-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the interchange control number in the UNB5 field specified in the party settings, specifically the reference number in field UNB5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="5d91d-118">El valor máximo permitido para el número de control de intercambio depende de los valores de los tres campos en UNB5.</span><span class="sxs-lookup"><span data-stu-id="5d91d-118">The maximum allowable value for the interchange control number depends upon the values of the three fields in UNB5.</span></span> <span data-ttu-id="5d91d-119">El número máximo de caracteres es 14 para el número de referencia en el campo UNB5.2, 13 para el prefijo en UNB5.1, 13 para el sufijo en UNB5.3 y 14 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="5d91d-119">The maximum number of characters is 14 for the reference number in field UNB5.2, 13 for the prefix in UNB5.1 and 13 for the suffix in UNB5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5d91d-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5d91d-120">User Action</span></span>  
 <span data-ttu-id="5d91d-121">Para resolver este error, restablezca el campo de número de referencia (UNB5.2) del número de control de intercambio, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="5d91d-121">To resolve this error, reset the reference number field (UNB5.2) of the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="5d91d-122">En el cuadro de diálogo Propiedades de EDI para la entidad resuelta para el intercambio, abra la página Definición de segmento UNB para la entidad como receptora del intercambio.</span><span class="sxs-lookup"><span data-stu-id="5d91d-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNB Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="5d91d-123">Haga clic en el campo Editar asociado con el campo UNB5.</span><span class="sxs-lookup"><span data-stu-id="5d91d-123">Click the Edit field associated with the UNB5 field.</span></span>  
  
3.  <span data-ttu-id="5d91d-124">Defina el campo del centro del número de control de intercambio (el número de referencia en UNB5.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="5d91d-124">Set the middle field of the interchange control number (the reference number in UNB5.2) to a new value such that the field has an acceptable number of digits.</span></span>