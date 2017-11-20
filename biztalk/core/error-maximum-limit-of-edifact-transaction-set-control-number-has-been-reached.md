---
title: "Generación de confirmación; error porque se ha alcanzado el límite máximo del número de control de conjunto de transacciones de Edifact para la configuración de la entidad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcbb6374-0403-42b0-892b-b35157a2c74a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1879d55de163615d5a4fab19cd50839e7ab2b17f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-party-settings"></a><span data-ttu-id="fdeda-102">Error en la generación de confirmación; se ha alcanzado el límite máximo del número de control de conjunto de transacciones de Edifact para la configuración de la entidad</span><span class="sxs-lookup"><span data-stu-id="fdeda-102">Acknowledgement generation has failed as maximum limit of Edifact transaction set control number has been reached for party settings</span></span>
## <a name="details"></a><span data-ttu-id="fdeda-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fdeda-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fdeda-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fdeda-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="fdeda-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fdeda-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="fdeda-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fdeda-106">Event ID</span></span>|-|  
|<span data-ttu-id="fdeda-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fdeda-107">Event Source</span></span>|<span data-ttu-id="fdeda-108">EDI de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdeda-108">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI</span></span>|  
|<span data-ttu-id="fdeda-109">Componente</span><span class="sxs-lookup"><span data-stu-id="fdeda-109">Component</span></span>|<span data-ttu-id="fdeda-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="fdeda-110">EDI Engine</span></span>|  
|<span data-ttu-id="fdeda-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fdeda-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="fdeda-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fdeda-112">Message Text</span></span>|<span data-ttu-id="fdeda-113">Error en la generación de confirmación; se ha alcanzado el límite máximo del número aceptable de control de grupo de transacciones de Edifact para la entidad {0}.</span><span class="sxs-lookup"><span data-stu-id="fdeda-113">Acknowledgement generation has failed as max limit of acceptable Edifact transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="fdeda-114">Para restablecer el contador, vaya a Entidad, en la pantalla de función del remitente, en el campo UNH 1 del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="fdeda-114">Reset counter by navigating to Party in sender role screen, field UNH 1 in Partner Agreement manager.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fdeda-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="fdeda-115">Explanation</span></span>  
 <span data-ttu-id="fdeda-116">Este evento de error,  indica que BizTalk Server no pudo generar una confirmación para el intercambio EDIFACT porque el número de control que especificó en el número de referencia del conjunto de transacciones (UNH1) de la confirmación es mayor que el valor máximo permitido para UNH1.</span><span class="sxs-lookup"><span data-stu-id="fdeda-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the EDIFACT interchange because the control number that it entered in the Transaction set reference number (UNH1) of the acknowledgment is greater than the maximum value allowed for UNH1.</span></span> <span data-ttu-id="fdeda-117">En esta instancia, BizTalk Server usó las propiedades de entidad de EDI para crear la confirmación.</span><span class="sxs-lookup"><span data-stu-id="fdeda-117">In this instance, BizTalk Server used the EDI party properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="fdeda-118">El valor máximo del número de referencia del conjunto de transacciones depende del número de dígitos usado para el número de referencia.</span><span class="sxs-lookup"><span data-stu-id="fdeda-118">The maximum value of the transaction set reference number depends upon the number of digits used for the reference number.</span></span> <span data-ttu-id="fdeda-119">El número máximo de caracteres es 14 para el número de referencia, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.</span><span class="sxs-lookup"><span data-stu-id="fdeda-119">The maximum number of characters is 14 for the reference number, 13 for the prefix and suffix, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fdeda-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fdeda-120">User Action</span></span>  
 <span data-ttu-id="fdeda-121">Para resolver este error, restablezca el campo de número de referencia (UNH1.2) del número de referencia del conjunto de transacciones (UNH1) en la página Definición de segmentos UNG y UNH en un valor inferior al límite máximo.</span><span class="sxs-lookup"><span data-stu-id="fdeda-121">To resolve this error, reset the reference number field (UNH1.2) of the Transaction set reference number (UNH1) in the UNG and UNH Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="fdeda-122">Configure esta propiedad en el cuadro de diálogo Propiedades de EDI de la consola de administración de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdeda-122">Set this property in the EDI Properties dialog box in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration Console.</span></span>