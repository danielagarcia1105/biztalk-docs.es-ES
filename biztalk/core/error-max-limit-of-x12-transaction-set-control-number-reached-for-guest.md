---
title: El límite máximo aceptable X12 ha alcanzado el número de control de conjunto de transacciones para la configuración de invitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5a4aa5c-13a7-4234-916e-562b52644c51
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b90021a672b3aec71198d8fd6533a2037772346
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014085"
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="96b89-102">Se ha alcanzado el límite máximo permitido para el número de control de conjunto de transacciones X12 en la configuración de Invitado</span><span class="sxs-lookup"><span data-stu-id="96b89-102">Max limit of acceptable X12 transaction set control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="96b89-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="96b89-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="96b89-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="96b89-104">Product Name</span></span>   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| <span data-ttu-id="96b89-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="96b89-105">Product Version</span></span> |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    <span data-ttu-id="96b89-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="96b89-106">Event ID</span></span>     |                                                                                                     -                                                                                                      |
|  <span data-ttu-id="96b89-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="96b89-107">Event Source</span></span>   |                                                           <span data-ttu-id="96b89-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96b89-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                           |
|    <span data-ttu-id="96b89-109">Componente</span><span class="sxs-lookup"><span data-stu-id="96b89-109">Component</span></span>    |                                                                                                 <span data-ttu-id="96b89-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="96b89-110">EDI Engine</span></span>                                                                                                 |
|  <span data-ttu-id="96b89-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="96b89-111">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="96b89-112">GlobalX12TsNumberError</span><span class="sxs-lookup"><span data-stu-id="96b89-112">GlobalX12TsNumberError</span></span>                                                                                           |
|  <span data-ttu-id="96b89-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="96b89-113">Message Text</span></span>   | <span data-ttu-id="96b89-114">Se ha alcanzado el límite máximo permitido para el número de control de conjunto de transacciones X12 en la configuración de Invitado.</span><span class="sxs-lookup"><span data-stu-id="96b89-114">Max limit of acceptable X12 transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="96b89-115">Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo ST 2, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="96b89-115">Reset counter by navigating to Global configuration sender role screen, field ST 2 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="96b89-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="96b89-116">Explanation</span></span>  
 <span data-ttu-id="96b89-117">Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control del conjunto de transacciones en el campo ST02 especificado en la configuración global, específicamente el número de referencia en el campo ST02.2, era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="96b89-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the transaction set control number in the ST02 field specified in the global settings, specifically the reference number in field ST02.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="96b89-118">El valor máximo permitido para el número de control del conjunto de transacciones depende de los valores de los tres campos en ST02.</span><span class="sxs-lookup"><span data-stu-id="96b89-118">The maximum allowable value for the transaction set control number depends upon the values of the three fields in ST02.</span></span> <span data-ttu-id="96b89-119">El número máximo de caracteres es 9 para el número de referencia en el campo UNH1.2, 8 para el prefijo en UNH1.1 y 8 para el sufijo en UNH1.3 y 9 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="96b89-119">The maximum number of characters is 9 for the reference number in field UNH1.2, 8 for the prefix in UNH1.1 and 8 for the suffix in UNH1.3, and 9 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96b89-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="96b89-120">User Action</span></span>  
 <span data-ttu-id="96b89-121">Para resolver este error, restablezca el campo de número de referencia (ST02.2) del número de control del conjunto de transacciones, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="96b89-121">To resolve this error, reset the reference number field (ST02.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="96b89-122">En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmentos GS y ST.</span><span class="sxs-lookup"><span data-stu-id="96b89-122">In the EDI Global Properties dialog box, open the GS and ST Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="96b89-123">Haga clic en el campo Editar asociado con el campo ST02.</span><span class="sxs-lookup"><span data-stu-id="96b89-123">Click the Edit field associated with the ST02 field.</span></span>  
  
3.  <span data-ttu-id="96b89-124">Defina el campo del centro del número de control de grupo (el número de referencia en ST02.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="96b89-124">Set the middle field of the group control number (the reference number in ST02.2) to a new value such that the field has an acceptable number of digits.</span></span>