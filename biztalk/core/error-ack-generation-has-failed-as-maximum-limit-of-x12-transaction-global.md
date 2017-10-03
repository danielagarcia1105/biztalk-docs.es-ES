---
title: "Generación de confirmación de error error el límite máximo de transacción global X12 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bbcae14-6e5c-4f79-87c6-311b4b54c7ff
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e648a40b11d94ce97b5c327f392585e313de06f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-ack-generation-has-failed-as-maximum-limit-of-x12-transaction-global"></a><span data-ttu-id="2bb84-102">Generación de confirmación de error error el límite máximo de transacción global X12</span><span class="sxs-lookup"><span data-stu-id="2bb84-102">Error-Ack generation has failed as maximum limit of X12 transaction-global</span></span>
## <a name="details"></a><span data-ttu-id="2bb84-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2bb84-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2bb84-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2bb84-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2bb84-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2bb84-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2bb84-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2bb84-106">Event ID</span></span>|-|  
|<span data-ttu-id="2bb84-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2bb84-107">Event Source</span></span>|<span data-ttu-id="2bb84-108">EDI de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bb84-108">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI</span></span>|  
|<span data-ttu-id="2bb84-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2bb84-109">Component</span></span>|<span data-ttu-id="2bb84-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="2bb84-110">EDI Engine</span></span>|  
|<span data-ttu-id="2bb84-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2bb84-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="2bb84-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2bb84-112">Message Text</span></span>|<span data-ttu-id="2bb84-113">Error en la generación de confirmación; se ha alcanzado el límite máximo del número aceptable de control de grupo de transacciones de X12 para la configuración de invitado.</span><span class="sxs-lookup"><span data-stu-id="2bb84-113">Acknowledgement generation has failed as max limit of acceptable X12 transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="2bb84-114">Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo ST 2, del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="2bb84-114">Reset counter by navigating to Global configuration sender role screen, field ST 2 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2bb84-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="2bb84-115">Explanation</span></span>  
 <span data-ttu-id="2bb84-116">Este evento de error,  indica que BizTalk Server no pudo generar una confirmación para el intercambio X12 porque el número de control que especificó en el número de control del conjunto de transacciones (ST2) de la confirmación es mayor que el valor máximo permitido para ST2.</span><span class="sxs-lookup"><span data-stu-id="2bb84-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the X12 interchange because the control number that it entered in the Transaction set control number (ST2) of the acknowledgment is greater than the maximum value allowed for ST2.</span></span> <span data-ttu-id="2bb84-117">En esta instancia, BizTalk Server usó las propiedades globales de EDI para crear la confirmación.</span><span class="sxs-lookup"><span data-stu-id="2bb84-117">In this instance, BizTalk Server used the EDI global properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="2bb84-118">El valor máximo del número de control del conjunto de transacciones depende del número de dígitos usado para el número de control.</span><span class="sxs-lookup"><span data-stu-id="2bb84-118">The maximum value of the transaction set control number depends upon the number of digits used for the control number.</span></span> <span data-ttu-id="2bb84-119">La longitud máxima de los tres campos es 9; la longitud máxima de los campos prefijo y sufijo es 8.</span><span class="sxs-lookup"><span data-stu-id="2bb84-119">The maximum length of all three fields is 9; the maximum length of the prefix and suffix fields is 8.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2bb84-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2bb84-120">User Action</span></span>  
 <span data-ttu-id="2bb84-121">Para resolver este error, restablezca el campo de número de control (ST2.2) del número de referencia del conjunto de transacciones (ST2) en la página Definición de segmentos GS y ST en un valor inferior al límite máximo.</span><span class="sxs-lookup"><span data-stu-id="2bb84-121">To resolve this error, reset the control number field (ST2.2) of the Transaction set control number (ST2) in the GS and ST Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="2bb84-122">Configure esta propiedad en el cuadro de diálogo Propiedades globales de EDI de la consola de administración de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bb84-122">Set this property in the EDI Global Properties dialog box in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration Console.</span></span>