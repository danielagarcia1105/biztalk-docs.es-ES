---
title: El límite máximo de X12 aceptable alcanzó el número de control de grupo funcional para la configuración de invitado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05cba774-fa35-4694-aa34-d7151f8cd75c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3210fb773b7093c2e28f98e0cf1aa223e1a63936
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241636"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="1334a-102">Se ha alcanzado el límite máximo permitido para el número de control de grupo funcional X12 en la configuración de Invitado</span><span class="sxs-lookup"><span data-stu-id="1334a-102">Max limit of acceptable X12 functional group control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="1334a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1334a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1334a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1334a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1334a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1334a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1334a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1334a-106">Event ID</span></span>|-|  
|<span data-ttu-id="1334a-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1334a-107">Event Source</span></span>|<span data-ttu-id="1334a-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1334a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="1334a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="1334a-109">Component</span></span>|<span data-ttu-id="1334a-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="1334a-110">EDI Engine</span></span>|  
|<span data-ttu-id="1334a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1334a-111">Symbolic Name</span></span>|<span data-ttu-id="1334a-112">GlobalEdifactUnhNumberError</span><span class="sxs-lookup"><span data-stu-id="1334a-112">GlobalEdifactUnhNumberError</span></span>|  
|<span data-ttu-id="1334a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1334a-113">Message Text</span></span>|<span data-ttu-id="1334a-114">Se ha alcanzado el límite máximo permitido para el número de control de grupo funcional X12 en la configuración de Invitado.</span><span class="sxs-lookup"><span data-stu-id="1334a-114">Max limit of acceptable X12 functional group control number has reached for Guest settings.</span></span> <span data-ttu-id="1334a-115">Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo GS 6, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="1334a-115">Reset counter by navigating to Global configuration receiver role screen, field GS 6 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1334a-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1334a-116">Explanation</span></span>  
 <span data-ttu-id="1334a-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control de grupo del campo GS06 especificado en la configuración global era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="1334a-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the group control number in the GS06 field specified in the global settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="1334a-118">El número máximo de caracteres es 9 para el número de control de grupo.</span><span class="sxs-lookup"><span data-stu-id="1334a-118">The maximum number of characters for the group control number is 9.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1334a-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1334a-119">User Action</span></span>  
 <span data-ttu-id="1334a-120">Para resolver este error, restablezca el número de control de grupo tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1334a-120">To resolve this error, reset the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="1334a-121">En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmentos GS y ST.</span><span class="sxs-lookup"><span data-stu-id="1334a-121">In the EDI Global Properties dialog box, open the GS and ST Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="1334a-122">Haga clic en el campo Editar asociado con el campo GS06.</span><span class="sxs-lookup"><span data-stu-id="1334a-122">Click the Edit field associated with the GS06 field.</span></span>  
  
3.  <span data-ttu-id="1334a-123">Defina el número de control de grupo en un valor nuevo, de modo que el campo tenga nueve dígitos o menos.</span><span class="sxs-lookup"><span data-stu-id="1334a-123">Set the group control number to a new value such that the field has nine or fewer digits.</span></span>