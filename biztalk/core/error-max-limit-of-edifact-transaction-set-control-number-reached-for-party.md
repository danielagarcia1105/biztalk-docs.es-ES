---
title: El límite máximo aceptable Edifact que se ha alcanzado el número de control de conjunto de transacciones para entidades | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a64cc5d3-a845-4044-9c6e-879ecda15fce
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85fd53beb1484d1e9ffbddf1bbc4f4ac69ae1e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004541"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-party"></a><span data-ttu-id="7abae-102">Se ha alcanzado el límite máximo permitido del número de control de conjunto de transacciones Edifact para la entidad</span><span class="sxs-lookup"><span data-stu-id="7abae-102">Max limit of acceptable Edifact transaction set control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="7abae-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7abae-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7abae-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7abae-104">Product Name</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| <span data-ttu-id="7abae-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7abae-105">Product Version</span></span> |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    <span data-ttu-id="7abae-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7abae-106">Event ID</span></span>     |                                                                                                -                                                                                                 |
|  <span data-ttu-id="7abae-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7abae-107">Event Source</span></span>   |                                                      <span data-ttu-id="7abae-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7abae-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                      |
|    <span data-ttu-id="7abae-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7abae-109">Component</span></span>    |                                                                                            <span data-ttu-id="7abae-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="7abae-110">EDI Engine</span></span>                                                                                            |
|  <span data-ttu-id="7abae-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7abae-111">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="7abae-112">GlobalEdifactUnhNumberError</span><span class="sxs-lookup"><span data-stu-id="7abae-112">GlobalEdifactUnhNumberError</span></span>                                                                                    |
|  <span data-ttu-id="7abae-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7abae-113">Message Text</span></span>   | <span data-ttu-id="7abae-114">El límite máximo aceptable Edifact que se ha alcanzado el número de control de conjunto de transacciones para entidades {0}.</span><span class="sxs-lookup"><span data-stu-id="7abae-114">Max limit of acceptable Edifact transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="7abae-115">Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo UNH 1, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="7abae-115">Reset counter by navigating to Party in receiver role screen, field UNH 1 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7abae-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="7abae-116">Explanation</span></span>  
 <span data-ttu-id="7abae-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control del conjunto de transacciones en el campo UNH1 especificado en la configuración de la entidad, específicamente el número de referencia en el campo UNH1.2, era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="7abae-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the transaction set control number in the UNH1 field specified in the party settings, specifically the reference number in field UNH1.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="7abae-118">El valor máximo permitido para el número de control del conjunto de transacciones depende de los valores de los tres campos en UNH1.</span><span class="sxs-lookup"><span data-stu-id="7abae-118">The maximum allowable value for the transaction set control number depends upon the values of the three fields in UNH1.</span></span> <span data-ttu-id="7abae-119">El número máximo de caracteres es 14 para el número de referencia en el campo UNH1.2, 13 para el prefijo en UNH1.1, 13 para el sufijo en UNH1.3 y 14 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="7abae-119">The maximum number of characters is 14 for the reference number in field UNH1.2, 13 for the prefix in UNH1.1 and 13 for the suffix in UNH1.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7abae-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7abae-120">User Action</span></span>  
 <span data-ttu-id="7abae-121">Para resolver este error, restablezca el campo de número de referencia (UNH1.2) del número de control del conjunto de transacciones, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7abae-121">To resolve this error, reset the reference number field (UNH1.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="7abae-122">En el cuadro de diálogo Propiedades de EDI para la entidad resuelta para el intercambio, abra la página Definición de segmentos UNG y UNH.</span><span class="sxs-lookup"><span data-stu-id="7abae-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNG and UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="7abae-123">Haga clic en el campo Editar asociado con el campo UNH1.</span><span class="sxs-lookup"><span data-stu-id="7abae-123">Click the Edit field associated with the UNH1 field.</span></span>  
  
3.  <span data-ttu-id="7abae-124">Defina el campo del centro del número de control del conjunto de transacciones (el número de referencia en UNH1.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="7abae-124">Set the middle field of the transaction set control number (the reference number in UNH1.2) to a new value such that the field has an acceptable number of digits.</span></span>