---
title: El límite máximo aceptable Edifact que se ha alcanzado el número de control de conjunto de transacciones para la configuración de invitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3924a18c-87bc-4727-b7cd-598d3e5ade2a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0de9240d2fd5ea701f701e34698b645b272b904b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978965"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="45505-102">Se ha alcanzado el límite máximo permitido para el número de control de conjunto de transacciones Edifact en la configuración de Invitado</span><span class="sxs-lookup"><span data-stu-id="45505-102">Max limit of acceptable Edifact transaction set control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="45505-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="45505-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="45505-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="45505-104">Product Name</span></span>   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| <span data-ttu-id="45505-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="45505-105">Product Version</span></span> |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    <span data-ttu-id="45505-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="45505-106">Event ID</span></span>     |                                                                                                         -                                                                                                          |
|  <span data-ttu-id="45505-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="45505-107">Event Source</span></span>   |                                                               <span data-ttu-id="45505-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45505-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                               |
|    <span data-ttu-id="45505-109">Componente</span><span class="sxs-lookup"><span data-stu-id="45505-109">Component</span></span>    |                                                                                                     <span data-ttu-id="45505-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="45505-110">EDI Engine</span></span>                                                                                                     |
|  <span data-ttu-id="45505-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="45505-111">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="45505-112">GlobalEdifactUnhNumberError</span><span class="sxs-lookup"><span data-stu-id="45505-112">GlobalEdifactUnhNumberError</span></span>                                                                                             |
|  <span data-ttu-id="45505-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="45505-113">Message Text</span></span>   | <span data-ttu-id="45505-114">Se ha alcanzado el límite máximo permitido para el número de control de conjunto de transacciones Edifact en la configuración de Invitado.</span><span class="sxs-lookup"><span data-stu-id="45505-114">Max limit of acceptable Edifact transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="45505-115">Para restablecer el contador, vaya a la pantalla de función de destinatario de configuración global, al campo UNH 1 del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="45505-115">Reset counter by  navigating to Global configuration receiver role screen, field UNH 1 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="45505-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="45505-116">Explanation</span></span>  
 <span data-ttu-id="45505-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control del conjunto de transacciones en el campo UNH1 especificado en la configuración global, específicamente el número de referencia en el campo UNH1.2, era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="45505-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the transaction set control number in the UNH1 field specified in the global settings, specifically the reference number in field UNH1.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="45505-118">El valor máximo permitido para el número de control de grupo depende de los valores de los tres campos en UNH1.</span><span class="sxs-lookup"><span data-stu-id="45505-118">The maximum allowable value for the group control number depends upon the values of the three fields in UNH1.</span></span> <span data-ttu-id="45505-119">El número máximo de caracteres es 14 para el número de referencia en el campo UNH1.2, 13 para el prefijo en UNH1.1, 13 para el sufijo en UNH1.3 y 14 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="45505-119">The maximum number of characters is 14 for the reference number in field UNH1.2, 13 for the prefix in UNH1.1 and 13 for the suffix in UNH1.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45505-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="45505-120">User Action</span></span>  
 <span data-ttu-id="45505-121">Para resolver este error, restablezca el campo de número de referencia (UNH1.2) del número de control del conjunto de transacciones, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="45505-121">To resolve this error, reset the reference number field (UNH1.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="45505-122">En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmento UNH.</span><span class="sxs-lookup"><span data-stu-id="45505-122">In the EDI Global Properties dialog box, open the UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="45505-123">Haga clic en el campo Editar asociado con el campo UNH1.</span><span class="sxs-lookup"><span data-stu-id="45505-123">Click the Edit field associated with the UNH1 field.</span></span>  
  
3.  <span data-ttu-id="45505-124">Defina el campo del centro del número de control de grupo (el número de referencia en UNH1.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="45505-124">Set the middle field of the group control number (the reference number in UNH1.2) to a new value such that the field has an acceptable number of digits.</span></span>