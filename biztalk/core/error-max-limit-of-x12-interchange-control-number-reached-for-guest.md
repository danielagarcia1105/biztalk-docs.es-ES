---
title: El límite máximo de X12 aceptable alcanzó el número de control de intercambio para la configuración de invitado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9737053d-6065-4c88-8dfa-5f69b48e0e82
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72fc565367477d9dbd09f3c0d4c4f9d6ab686a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241676"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="9310c-102">Se ha alcanzado el límite máximo permitido para el número de control de intercambio X12 en la configuración de Invitado</span><span class="sxs-lookup"><span data-stu-id="9310c-102">Max limit of acceptable X12 interchange control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="9310c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9310c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9310c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9310c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9310c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9310c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9310c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9310c-106">Event ID</span></span>|-|  
|<span data-ttu-id="9310c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9310c-107">Event Source</span></span>|<span data-ttu-id="9310c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9310c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="9310c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="9310c-109">Component</span></span>|<span data-ttu-id="9310c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="9310c-110">EDI Engine</span></span>|  
|<span data-ttu-id="9310c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9310c-111">Symbolic Name</span></span>|<span data-ttu-id="9310c-112">GlobalX12IsaNumberError</span><span class="sxs-lookup"><span data-stu-id="9310c-112">GlobalX12IsaNumberError</span></span>|  
|<span data-ttu-id="9310c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9310c-113">Message Text</span></span>|<span data-ttu-id="9310c-114">Se ha alcanzado el límite máximo permitido para el número de control de intercambio X12 en la configuración de Invitado.</span><span class="sxs-lookup"><span data-stu-id="9310c-114">Max limit of acceptable X12 interchange control number has reached for Guest settings.</span></span> <span data-ttu-id="9310c-115">Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo ISA 13, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="9310c-115">Reset counter by navigating to Global configuration receiver role screen, field ISA 13 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9310c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="9310c-116">Explanation</span></span>  
 <span data-ttu-id="9310c-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control de intercambio del campo ISA13 especificado en la configuración global era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="9310c-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the interchange control number in the ISA13 field specified in the global settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="9310c-118">El número máximo de caracteres es nueve para el número de control de intercambio.</span><span class="sxs-lookup"><span data-stu-id="9310c-118">The maximum number of characters for the interchange control number is nine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9310c-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9310c-119">User Action</span></span>  
 <span data-ttu-id="9310c-120">Para resolver este error, restablezca el número de control de intercambio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="9310c-120">To resolve this error, reset the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="9310c-121">En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmento ISA.</span><span class="sxs-lookup"><span data-stu-id="9310c-121">In the EDI Global Properties dialog box, open the ISA Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="9310c-122">Haga clic en el campo Editar asociado con el campo ISA13.</span><span class="sxs-lookup"><span data-stu-id="9310c-122">Click the Edit field associated with the ISA13 field.</span></span>  
  
3.  <span data-ttu-id="9310c-123">Defina el número de control de intercambio en un valor nuevo, de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="9310c-123">Set the interchange control number to a new value such that the field has an acceptable number of digits.</span></span>