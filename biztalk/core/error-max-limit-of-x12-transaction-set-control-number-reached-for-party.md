---
title: El límite máximo de aceptable X12 ha alcanzado el número de control de conjunto de transacciones para la entidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a402f6d0-4399-47c9-a39a-56d7fa1efa86
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c46a221e0e69d159ee1f5d8cdeee0e0c31389e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241180"
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-party"></a><span data-ttu-id="dea17-102">Se ha alcanzado el límite máximo permitido del número de control de conjunto de transacciones X12 para la entidad</span><span class="sxs-lookup"><span data-stu-id="dea17-102">Max limit of acceptable X12 transaction set control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="dea17-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="dea17-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dea17-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="dea17-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="dea17-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="dea17-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="dea17-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="dea17-106">Event ID</span></span>|-|  
|<span data-ttu-id="dea17-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="dea17-107">Event Source</span></span>|<span data-ttu-id="dea17-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dea17-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="dea17-109">Componente</span><span class="sxs-lookup"><span data-stu-id="dea17-109">Component</span></span>|<span data-ttu-id="dea17-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="dea17-110">EDI Engine</span></span>|  
|<span data-ttu-id="dea17-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="dea17-111">Symbolic Name</span></span>|<span data-ttu-id="dea17-112">PartyX12TsNumberError</span><span class="sxs-lookup"><span data-stu-id="dea17-112">PartyX12TsNumberError</span></span>|  
|<span data-ttu-id="dea17-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="dea17-113">Message Text</span></span>|<span data-ttu-id="dea17-114">Se ha alcanzado el límite máximo permitido del número de control de conjunto de transacciones X12 para la entidad {0}.</span><span class="sxs-lookup"><span data-stu-id="dea17-114">Max limit of acceptable X12 transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="dea17-115">Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo ST 2, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="dea17-115">Reset counter by navigating to Party in receiver role screen, field ST 2 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dea17-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="dea17-116">Explanation</span></span>  
 <span data-ttu-id="dea17-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control del conjunto de transacciones en el campo ST02 especificado en la configuración de la entidad, específicamente el número de referencia en el campo ST02.2, era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="dea17-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the transaction set control number in the ST02 field specified in the party settings, specifically the reference number in field ST02.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="dea17-118">El valor máximo permitido para el número de control del conjunto de transacciones depende de los valores de los tres campos en ST02.</span><span class="sxs-lookup"><span data-stu-id="dea17-118">The maximum allowable value for the transaction set control number depends upon the values of the three fields in ST02.</span></span> <span data-ttu-id="dea17-119">El número máximo de caracteres es 9 para el número de referencia en el campo ST02.2, 8 para el prefijo en ST02.1, 8 para el sufijo en ST02.3 y 9 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="dea17-119">The maximum number of characters is 9 for the reference number in field ST02.2, 8 for the prefix in ST02.1 and 8 for the suffix in ST02.3, and 9 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dea17-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="dea17-120">User Action</span></span>  
 <span data-ttu-id="dea17-121">Para resolver este error, restablezca el campo de número de referencia (UNH1.2) del número de control del conjunto de transacciones, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dea17-121">To resolve this error, reset the reference number field (UNH1.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="dea17-122">En el cuadro de diálogo Propiedades de EDI para la entidad resuelta para el intercambio, abra la página Definición de segmentos UNG y UNH.</span><span class="sxs-lookup"><span data-stu-id="dea17-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNG and UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="dea17-123">Haga clic en el campo Editar asociado con el campo UNH1.</span><span class="sxs-lookup"><span data-stu-id="dea17-123">Click the Edit field associated with the UNH1 field.</span></span>  
  
3.  <span data-ttu-id="dea17-124">Defina el campo del centro del número de control del conjunto de transacciones (el número de referencia en UNH1.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="dea17-124">Set the middle field of the transaction set control number (the reference number in UNH1.2) to a new value such that the field has an acceptable number of digits.</span></span>