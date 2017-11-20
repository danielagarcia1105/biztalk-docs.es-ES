---
title: "Generación de confirmación; error porque se ha alcanzado el límite máximo del número de control de conjunto de transacciones de Edifact para la configuración global | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6adc02d7-ebc4-4da0-a19a-3a423d63499d
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 252f0fd6dbe77eb83018e2bb34d4a6cd07cdbdf2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-global-settings"></a><span data-ttu-id="53279-102">Error en la generación de confirmación; se ha alcanzado el límite máximo del número de control de conjunto de transacciones de Edifact para la configuración global</span><span class="sxs-lookup"><span data-stu-id="53279-102">Acknowledgement generation has failed as maximum limit of Edifact transaction set control number has been reached for global settings</span></span>
## <a name="details"></a><span data-ttu-id="53279-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="53279-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53279-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="53279-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="53279-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="53279-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="53279-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="53279-106">Event ID</span></span>|-|  
|<span data-ttu-id="53279-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="53279-107">Event Source</span></span>|<span data-ttu-id="53279-108">EDI de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53279-108">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI</span></span>|  
|<span data-ttu-id="53279-109">Componente</span><span class="sxs-lookup"><span data-stu-id="53279-109">Component</span></span>|<span data-ttu-id="53279-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="53279-110">EDI Engine</span></span>|  
|<span data-ttu-id="53279-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="53279-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="53279-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="53279-112">Message Text</span></span>|<span data-ttu-id="53279-113">Error en la generación de confirmación; se ha alcanzado el límite máximo del número aceptable de control de grupo de transacciones de Edifact para la configuración de invitado.</span><span class="sxs-lookup"><span data-stu-id="53279-113">Acknowledgement generation has failed as max limit of acceptable Edifact transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="53279-114">Para restablecer el contador, vaya a la pantalla de función de remitente de configuración global, al campo UNH 1 del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="53279-114">Reset counter by navigating to Global configuration sender role screen, field UNH 1 in Partner Agreement manager.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53279-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="53279-115">Explanation</span></span>  
 <span data-ttu-id="53279-116">Este evento de error,  indica que BizTalk Server no pudo generar una confirmación para el intercambio EDIFACT porque el número de control que especificó en el número de referencia del conjunto de transacciones (UNH1) de la confirmación es mayor que el valor máximo permitido para UNH1.</span><span class="sxs-lookup"><span data-stu-id="53279-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the EDIFACT interchange because the control number that it entered in the Transaction set reference number (UNH1) of the acknowledgment is greater than the maximum value allowed for UNH1.</span></span> <span data-ttu-id="53279-117">En esta instancia, BizTalk Server usó las propiedades globales de EDI para crear la confirmación.</span><span class="sxs-lookup"><span data-stu-id="53279-117">In this instance, BizTalk Server used the EDI global properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="53279-118">El valor máximo del número de referencia del conjunto de transacciones depende del número de dígitos usado para el número de referencia.</span><span class="sxs-lookup"><span data-stu-id="53279-118">The maximum value of the transaction set reference number depends upon the number of digits used for the reference number.</span></span> <span data-ttu-id="53279-119">El número máximo de caracteres es 14 para el número de referencia, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="53279-119">The maximum number of characters is 14 for the reference number, 13 for the prefix and suffix, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53279-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="53279-120">User Action</span></span>  
 <span data-ttu-id="53279-121">Para resolver este error, restablezca el campo de número de referencia (UNH1.2) del número de referencia del conjunto de transacciones (UNH1) en la página Definición de segmentos UNG y UNH en un valor inferior al límite máximo.</span><span class="sxs-lookup"><span data-stu-id="53279-121">To resolve this error, reset the reference number field (UNH1.2) of the Transaction set reference number (UNH1) in the UNG and UNH Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="53279-122">Configure esta propiedad en el cuadro de diálogo Propiedades globales de EDI de la consola de administración de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53279-122">Set this property in the EDI Global Properties dialog box in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration Console.</span></span>