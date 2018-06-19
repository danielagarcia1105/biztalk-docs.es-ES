---
title: Ha alcanzado el límite máximo del número de control de grupo funcional Edifact aceptable para la entidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fde516b-59f1-49a1-8456-127469df0e02
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d4a47e0866c78e692f8c992afbd6b24cde95632
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241508"
---
# <a name="max-limit-of-acceptable-edifact-functional-group-control-number-has-reached-for-party"></a><span data-ttu-id="f6a06-102">Se ha alcanzado el límite máximo permitido del número de control de grupo funcional Edifact para la entidad</span><span class="sxs-lookup"><span data-stu-id="f6a06-102">Max limit of acceptable Edifact functional group control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="f6a06-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f6a06-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6a06-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f6a06-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f6a06-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f6a06-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f6a06-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f6a06-106">Event ID</span></span>|-|  
|<span data-ttu-id="f6a06-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f6a06-107">Event Source</span></span>|<span data-ttu-id="f6a06-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6a06-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="f6a06-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f6a06-109">Component</span></span>|<span data-ttu-id="f6a06-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f6a06-110">EDI Engine</span></span>|  
|<span data-ttu-id="f6a06-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f6a06-111">Symbolic Name</span></span>|<span data-ttu-id="f6a06-112">PartyEdifactUngNumberError</span><span class="sxs-lookup"><span data-stu-id="f6a06-112">PartyEdifactUngNumberError</span></span>|  
|<span data-ttu-id="f6a06-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f6a06-113">Message Text</span></span>|<span data-ttu-id="f6a06-114">Se ha alcanzado el límite máximo permitido del número de control de grupo funcional Edifact para la entidad {0}.</span><span class="sxs-lookup"><span data-stu-id="f6a06-114">Max limit of acceptable Edifact functional group control number has reached for party {0}.</span></span> <span data-ttu-id="f6a06-115">Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo UNG 5, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="f6a06-115">Reset counter by navigating to Party in receiver role screen, field UNG 5 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6a06-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="f6a06-116">Explanation</span></span>  
 <span data-ttu-id="f6a06-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio EDIFACT saliente porque el número de control de grupo del campo UNG5 especificado en la configuración de la entidad, específicamente el número de referencia en el campo UNG5.2, era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="f6a06-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing EDIFACT interchange because the group control number in the UNG5 field specified in the party settings, specifically the reference number in field UNG5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="f6a06-118">El valor máximo permitido para el número de control de grupo depende de los valores de los tres campos en UNG5.</span><span class="sxs-lookup"><span data-stu-id="f6a06-118">The maximum allowable value for the group control number depends upon the values of the three fields in UNG5.</span></span> <span data-ttu-id="f6a06-119">El número máximo de caracteres es 14 para el número de referencia en el campo UNG5.2, 13 para el prefijo en UNG5.1, 13 para el sufijo en UNG5.3 y 14 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="f6a06-119">The maximum number of characters is 14 for the reference number in field UNG5.2, 13 for the prefix in UNG5.1 and 13 for the suffix in UNG5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6a06-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f6a06-120">User Action</span></span>  
 <span data-ttu-id="f6a06-121">Para resolver este error, restablezca el campo de número de referencia (UNG5.2) del número de control de grupo, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="f6a06-121">To resolve this error, reset the reference number field (UNG5.2) of the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="f6a06-122">En el cuadro de diálogo Propiedades de EDI de la entidad resuelta para el intercambio, abra la página Definición de segmentos UNG y UNH para la entidad como receptor de intercambio.</span><span class="sxs-lookup"><span data-stu-id="f6a06-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNG and UNH Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="f6a06-123">Haga clic en el campo Editar asociado con el campo UNG5.</span><span class="sxs-lookup"><span data-stu-id="f6a06-123">Click the Edit field associated with the UNG5 field.</span></span>  
  
3.  <span data-ttu-id="f6a06-124">Defina el campo del centro del número de control de grupo (el número de referencia en UNG5.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="f6a06-124">Set the middle field of the group control number (the reference number in UNG5.2) to a new value such that the field has an acceptable number of digits.</span></span>