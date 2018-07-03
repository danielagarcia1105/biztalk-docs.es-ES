---
title: Ha alcanzado el límite máximo del número aceptable de control de grupo funcional de Edifact para la configuración de invitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93ea1bd6-8c39-4d11-81a5-75d4a861e041
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 533f1067effa99f4152c908c70adf16eeb067c7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010453"
---
# <a name="max-limit-of-acceptable-edifact-functional-group-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="c08a6-102">Se ha alcanzado el límite máximo permitido para el número de control de grupo funcional Edifact en la configuración de Invitado</span><span class="sxs-lookup"><span data-stu-id="c08a6-102">Max limit of acceptable Edifact functional group control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="c08a6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c08a6-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c08a6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c08a6-104">Product Name</span></span>   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| <span data-ttu-id="c08a6-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c08a6-105">Product Version</span></span> |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    <span data-ttu-id="c08a6-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c08a6-106">Event ID</span></span>     |                                                                                                         -                                                                                                          |
|  <span data-ttu-id="c08a6-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c08a6-107">Event Source</span></span>   |                                                               <span data-ttu-id="c08a6-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c08a6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                               |
|    <span data-ttu-id="c08a6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c08a6-109">Component</span></span>    |                                                                                                     <span data-ttu-id="c08a6-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c08a6-110">EDI Engine</span></span>                                                                                                     |
|  <span data-ttu-id="c08a6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c08a6-111">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="c08a6-112">GlobalEdifactUngNumberError</span><span class="sxs-lookup"><span data-stu-id="c08a6-112">GlobalEdifactUngNumberError</span></span>                                                                                             |
|  <span data-ttu-id="c08a6-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c08a6-113">Message Text</span></span>   | <span data-ttu-id="c08a6-114">Se ha alcanzado el límite máximo permitido para el número de control de grupo funcional Edifact en la configuración de Invitado.</span><span class="sxs-lookup"><span data-stu-id="c08a6-114">Max limit of acceptable Edifact functional group control number has reached for Guest settings.</span></span> <span data-ttu-id="c08a6-115">Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo UNB 5, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="c08a6-115">Reset counter by navigating to Global configuration receiver role screen, field UNG 5 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c08a6-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="c08a6-116">Explanation</span></span>  
 <span data-ttu-id="c08a6-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control de grupo del campo UNG5 especificado en la configuración global, específicamente el número de referencia en el campo UNG5.2, era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="c08a6-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the group control number in the UNG5 field specified in the global settings, specifically the reference number in field UNG5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="c08a6-118">El valor máximo permitido para el número de control de grupo depende de los valores de los tres campos en UNG5.</span><span class="sxs-lookup"><span data-stu-id="c08a6-118">The maximum allowable value for the group control number depends upon the values of the three fields in UNG5.</span></span> <span data-ttu-id="c08a6-119">El número máximo de caracteres es 14 para el número de referencia en el campo UNG5.2, 13 para el prefijo en UNG5.1, 13 para el sufijo en UNG5.3 y 14 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="c08a6-119">The maximum number of characters is 14 for the reference number in field UNG5.2, 13 for the prefix in UNG5.1 and 13 for the suffix in UNG5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c08a6-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c08a6-120">User Action</span></span>  
 <span data-ttu-id="c08a6-121">Para resolver este error, restablezca el campo de número de referencia (UNG5.2) del número de control de grupo, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c08a6-121">To resolve this error, reset the reference number field (UNG5.2) of the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="c08a6-122">En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmentos UNG y UNH.</span><span class="sxs-lookup"><span data-stu-id="c08a6-122">In the EDI Global Properties dialog box, open the UNG and UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="c08a6-123">Haga clic en el campo Editar asociado con el campo UNG5.</span><span class="sxs-lookup"><span data-stu-id="c08a6-123">Click the Edit field associated with the UNG5 field.</span></span>  
  
3.  <span data-ttu-id="c08a6-124">Defina el campo del centro del número de control de grupo (el número de referencia en UNG5.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="c08a6-124">Set the middle field of the group control number (the reference number in UNG5.2) to a new value such that the field has an acceptable number of digits.</span></span>