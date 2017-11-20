---
title: "Ha alcanzado el límite máximo permitido del número aceptable de control de intercambio de Edifact para la configuración de invitado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5d2dcc0-61fd-47c9-9339-8a85319c5398
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dc8110f9aa9a48e098f970383b65266cc544c19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="3dbfb-102">Se ha alcanzado el límite máximo permitido para el número de control de intercambio Edifact en la configuración de Invitado</span><span class="sxs-lookup"><span data-stu-id="3dbfb-102">Max limit of acceptable Edifact interchange control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="3dbfb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3dbfb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3dbfb-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3dbfb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3dbfb-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3dbfb-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3dbfb-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3dbfb-106">Event ID</span></span>|-|  
|<span data-ttu-id="3dbfb-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3dbfb-107">Event Source</span></span>|<span data-ttu-id="3dbfb-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dbfb-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="3dbfb-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3dbfb-109">Component</span></span>|<span data-ttu-id="3dbfb-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="3dbfb-110">EDI Engine</span></span>|  
|<span data-ttu-id="3dbfb-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3dbfb-111">Symbolic Name</span></span>|<span data-ttu-id="3dbfb-112">GlobalEdifactUnbNumberError</span><span class="sxs-lookup"><span data-stu-id="3dbfb-112">GlobalEdifactUnbNumberError</span></span>|  
|<span data-ttu-id="3dbfb-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3dbfb-113">Message Text</span></span>|<span data-ttu-id="3dbfb-114">Se ha alcanzado el límite máximo permitido para el número de control de intercambio Edifact en la configuración de Invitado.</span><span class="sxs-lookup"><span data-stu-id="3dbfb-114">Max limit of acceptable Edifact interchange control number has reached for Guest settings.</span></span> <span data-ttu-id="3dbfb-115">Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo UNB, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="3dbfb-115">Reset counter by navigating to Global configuration receiver role screen, field UNB 5 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3dbfb-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="3dbfb-116">Explanation</span></span>  
 <span data-ttu-id="3dbfb-117">Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control de intercambio en el campo ISA13 especificado en la configuración global, específicamente el número de referencia en el campo UNB5.2, era mayor que el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="3dbfb-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the interchange control number in the ISA13 field specified in the global settings, specifically the reference number in field UNB5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="3dbfb-118">El valor máximo permitido para el número de control de intercambio depende de los valores de los tres campos en UNB5.</span><span class="sxs-lookup"><span data-stu-id="3dbfb-118">The maximum allowable value for the interchange control number depends upon the values of the three fields in UNB5.</span></span> <span data-ttu-id="3dbfb-119">El número máximo de caracteres es 14 para el número de referencia en el campo UNB5.2, 13 para el prefijo en UNB5.1, 13 para el sufijo en UNB5.3 y 14 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="3dbfb-119">The maximum number of characters is 14 for the reference number in field UNB5.2, 13 for the prefix in UNB5.1 and 13 for the suffix in UNB5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3dbfb-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3dbfb-120">User Action</span></span>  
 <span data-ttu-id="3dbfb-121">Para resolver este error, restablezca el campo de número de referencia (UNB5.2) del número de control de intercambio, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3dbfb-121">To resolve this error, reset the reference number field (UNB5.2) of the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="3dbfb-122">En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmento UNB.</span><span class="sxs-lookup"><span data-stu-id="3dbfb-122">In the EDI Global Properties dialog box, open the UNB Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="3dbfb-123">Haga clic en el campo Editar asociado con el campo UNB5.</span><span class="sxs-lookup"><span data-stu-id="3dbfb-123">Click the Edit field associated with the UNB5 field.</span></span>  
  
3.  <span data-ttu-id="3dbfb-124">Defina el campo del centro del número de control de intercambio (el número de referencia en UNB5.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.</span><span class="sxs-lookup"><span data-stu-id="3dbfb-124">Set the middle field of the interchange control number (the reference number in UNB5.2) to a new value such that the field has an acceptable number of digits.</span></span>